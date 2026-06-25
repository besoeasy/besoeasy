<template>
  <div class="fixed bottom-0 left-0 w-full pointer-events-none -z-10 select-none">
    <svg
      viewBox="0 0 1000 500"
      class="w-full"
      style="height: 48vh"
      preserveAspectRatio="xMidYMax meet"
      xmlns="http://www.w3.org/2000/svg"
    >
      <defs>
        <!-- Sun radial glow -->
        <radialGradient id="sunGlow" cx="50%" cy="50%" r="50%">
          <stop offset="0%"   stop-color="#fbbf24" stop-opacity="0.55" />
          <stop offset="60%"  stop-color="#fbbf24" stop-opacity="0.15" />
          <stop offset="100%" stop-color="#fbbf24" stop-opacity="0" />
        </radialGradient>

        <!-- Moon radial glow -->
        <radialGradient id="moonGlow" cx="50%" cy="50%" r="50%">
          <stop offset="0%"   stop-color="#c7d2fe" stop-opacity="0.5" />
          <stop offset="60%"  stop-color="#c7d2fe" stop-opacity="0.12" />
          <stop offset="100%" stop-color="#c7d2fe" stop-opacity="0" />
        </radialGradient>

        <!-- Arc colour fades in from edges -->
        <linearGradient id="arcGrad" x1="0%" y1="0%" x2="100%" y2="0%">
          <stop offset="0%"   :stop-color="arcColor" stop-opacity="0" />
          <stop offset="15%"  :stop-color="arcColor" stop-opacity="0.35" />
          <stop offset="50%"  :stop-color="arcColor" stop-opacity="0.7" />
          <stop offset="85%"  :stop-color="arcColor" stop-opacity="0.35" />
          <stop offset="100%" :stop-color="arcColor" stop-opacity="0" />
        </linearGradient>

        <!-- Soft blur filter for glow -->
        <filter id="blur10" x="-60%" y="-60%" width="220%" height="220%">
          <feGaussianBlur stdDeviation="10" />
        </filter>
        <filter id="blur6" x="-40%" y="-40%" width="180%" height="180%">
          <feGaussianBlur stdDeviation="6" />
        </filter>
      </defs>

      <!-- ── Horizon line ─────────────────────────────────────── -->
      <line x1="0" y1="490" x2="1000" y2="490" stroke="#e5e7eb" stroke-width="1" />

      <!-- ── Dashed semi-circle arc ───────────────────────────── -->
      <!-- Arc: center (500,490), radius 450. Left=(50,490) Right=(950,490) -->
      <path
        d="M 50 490 A 450 450 0 0 1 950 490"
        fill="none"
        stroke="url(#arcGrad)"
        stroke-width="1.5"
        stroke-dasharray="6 5"
      />

      <!-- ── Hour tick marks (6, 9, 12, 15, 18) ─────────────── -->
      <g v-for="tick in ticks" :key="tick.label">
        <line
          :x1="tick.x" :y1="tick.y"
          :x2="tick.x + Math.cos(tick.angle + Math.PI/2) * 6"
          :y2="tick.y - Math.sin(tick.angle + Math.PI/2) * 6"
          stroke="#d1d5db"
          stroke-width="1"
          stroke-linecap="round"
        />
        <text
          :x="tick.lx" :y="tick.ly"
          text-anchor="middle"
          font-size="11"
          font-family="ui-sans-serif, system-ui, sans-serif"
          fill="#d1d5db"
        >{{ tick.label }}</text>
      </g>

      <!-- ── Sun or Moon ─────────────────────────────────────── -->
      <template v-if="bodyPos">
        <!-- Outer glow -->
        <circle
          :cx="bodyPos.x" :cy="bodyPos.y"
          r="70"
          :fill="isDay ? 'url(#sunGlow)' : 'url(#moonGlow)'"
          filter="url(#blur10)"
        />
        <!-- Inner soft ring -->
        <circle
          :cx="bodyPos.x" :cy="bodyPos.y"
          r="26"
          :fill="isDay ? '#fbbf24' : '#e0e7ff'"
          opacity="0.25"
          filter="url(#blur6)"
        />
        <!-- Body disc -->
        <circle
          :cx="bodyPos.x" :cy="bodyPos.y"
          :r="isDay ? 14 : 11"
          :fill="isDay ? '#f59e0b' : '#a5b4fc'"
          class="body-pulse"
        />

        <!-- Temperature above body -->
        <text
          v-if="temperature !== null"
          :x="bodyPos.x"
          :y="bodyPos.y - 26"
          text-anchor="middle"
          font-size="18"
          font-weight="700"
          font-family="ui-sans-serif, system-ui, sans-serif"
          :fill="isDay ? '#92400e' : '#6366f1'"
        >{{ temperature }}°C</text>
      </template>

      <!-- ── City · time label at horizon ───────────────────── -->
      <text
        v-if="label"
        x="500" y="482"
        text-anchor="middle"
        font-size="11"
        letter-spacing="1"
        font-family="ui-sans-serif, system-ui, sans-serif"
        fill="#9ca3af"
      >{{ label }}</text>
    </svg>
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from "vue";

// ── Constants ────────────────────────────────────────────────────────────────
const CX = 500;   // arc center x
const CY = 490;   // arc center y (sits on horizon)
const R  = 450;   // arc radius

const SUNRISE = 6;
const SUNSET  = 18;

// ── State ────────────────────────────────────────────────────────────────────
const localHour   = ref(new Date().getHours() + new Date().getMinutes() / 60);
const temperature = ref(null);
const city        = ref("");
const label       = ref("");

// ── Derived ──────────────────────────────────────────────────────────────────
const isDay = computed(() => localHour.value >= SUNRISE && localHour.value <= SUNSET);

const arcColor = computed(() => isDay.value ? "#f59e0b" : "#818cf8");

// Position on the arc for a given hour (SUNRISE=left, noon=top, SUNSET=right)
function arcPos(hour) {
  const clamped = Math.max(SUNRISE, Math.min(SUNSET, hour));
  const fraction = (clamped - SUNRISE) / (SUNSET - SUNRISE); // 0→1
  const theta = (1 - fraction) * Math.PI;                     // π→0
  return {
    x: CX + R * Math.cos(theta),
    y: CY - R * Math.sin(theta),
  };
}

const bodyPos = computed(() => {
  if (isDay.value) return arcPos(localHour.value);
  // Night: show moon drifting along top of arc space (use mirrored hour)
  const h = localHour.value;
  // Map 18–24 / 0–6 to a 0→1 fraction across the top
  const nightFrac = h >= SUNSET ? (h - SUNSET) / (24 - SUNSET + SUNRISE) : (h + (24 - SUNSET)) / (24 - SUNSET + SUNRISE);
  const theta = (1 - nightFrac) * Math.PI;
  return {
    x: CX + R * 0.65 * Math.cos(theta),
    y: CY - R * 0.65 * Math.sin(theta),
  };
});

// Hour tick marks at 6, 9, 12, 15, 18
const ticks = computed(() => {
  return [6, 9, 12, 15, 18].map((h) => {
    const pos = arcPos(h);
    const fraction = (h - SUNRISE) / (SUNSET - SUNRISE);
    const theta = (1 - fraction) * Math.PI;
    return {
      label: `${h}:00`,
      x: pos.x,
      y: pos.y,
      angle: theta,
      lx: CX + (R + 22) * Math.cos(theta),
      ly: CY - (R + 22) * Math.sin(theta) + 4,
    };
  });
});

// ── Data fetching ────────────────────────────────────────────────────────────
onMounted(async () => {
  try {
    // 1. IP → timezone + coords + city
    const ipRes  = await fetch("https://ipapi.co/json/", { signal: AbortSignal.timeout(5000) });
    const ipData = await ipRes.json();

    const tz  = ipData.timezone;
    const lat = ipData.latitude;
    const lon = ipData.longitude;
    const cityName = ipData.city || ipData.country_name || "";

    // 2. Local hour from timezone
    if (tz) {
      const parts = new Intl.DateTimeFormat("en-US", {
        timeZone: tz,
        hour:   "numeric",
        minute: "numeric",
        hour12: false,
      }).formatToParts(new Date());

      const h = parseInt(parts.find(p => p.type === "hour").value, 10);
      const m = parseInt(parts.find(p => p.type === "minute").value, 10);
      localHour.value = h + m / 60;

      const displayTime = new Intl.DateTimeFormat("en-US", {
        timeZone: tz,
        hour:   "2-digit",
        minute: "2-digit",
        hour12: false,
      }).format(new Date());

      label.value = cityName ? `${cityName.toUpperCase()} · ${displayTime}` : displayTime;
    } else {
      const now = new Date();
      localHour.value = now.getHours() + now.getMinutes() / 60;
      label.value = cityName.toUpperCase();
    }

    city.value = cityName;

    // 3. Temperature from Open-Meteo (free, no API key)
    if (lat && lon) {
      const wxRes  = await fetch(
        `https://api.open-meteo.com/v1/forecast?latitude=${lat}&longitude=${lon}&current_weather=true`,
        { signal: AbortSignal.timeout(5000) }
      );
      const wxData = await wxRes.json();
      if (wxData.current_weather?.temperature !== undefined) {
        temperature.value = Math.round(wxData.current_weather.temperature);
      }
    }
  } catch (_) {
    // Fallback: use browser local time, no temperature
    const now = new Date();
    localHour.value = now.getHours() + now.getMinutes() / 60;
    label.value = "";
  }
});
</script>

<style scoped>
.body-pulse {
  animation: pulse 3s ease-in-out infinite;
  transform-origin: center;
  transform-box: fill-box;
}
@keyframes pulse {
  0%, 100% { opacity: 1;    r: 14px; }
  50%       { opacity: 0.8; r: 16px; }
}
</style>
