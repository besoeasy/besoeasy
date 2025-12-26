<template>
  <div class="p-5 m-auto max-w-7xl">
    <div class="flex sm:flex-row flex-col gap-10 items-center justify-center min-h-screen">
      <div class="w-full md:w-3/5">
        <div class="m-auto transform hover:-translate-y-2 hover:scale-105 hover:rotate-2 transition-all duration-500">
          <img class="rounded-2xl" src="/me.png" alt="" />
        </div>
      </div>
      <div class="w-full md:w-2/5">
        <div class="m-auto">
          <div
            class="text-2xl lg:text-5xl mb-2 text-pretty font-extrabold animate-pulse hover:animate-bounce hover:text-transparent hover:bg-clip-text hover:bg-linear-to-r hover:from-orange-500 hover:via-red-500 hover:to-pink-500 transition-all duration-500 cursor-pointer"
          >
            AMAN SINGH KATAL
          </div>
          <div class="text-xl mb-5 font-semibold animate-pulse">
            <ContactEmail />
          </div>

          <div class="mb-8 text-base sm:text-lg text-gray-800 relative" style="min-height: 160px;">
            <!-- Show hovered description when hovering over social buttons -->
            <transition 
              enter-active-class="transition-all duration-500 ease-out"
              enter-from-class="opacity-0"
              enter-to-class="opacity-100"
              leave-active-class="transition-all duration-300 ease-in"
              leave-from-class="opacity-100"
              leave-to-class="opacity-0"
            >
              <div 
                v-if="hoveredDescription" 
                class="absolute inset-0 text-xl sm:text-2xl md:text-3xl font-bold text-gray-600 leading-relaxed flex items-center"
              >
                {{ hoveredDescription }}
              </div>
            </transition>
            
            <!-- Default bio text -->
            <transition 
              enter-active-class="transition-all duration-500 ease-out"
              enter-from-class="opacity-0"
              enter-to-class="opacity-100"
              leave-active-class="transition-all duration-300 ease-in"
              leave-from-class="opacity-100"
              leave-to-class="opacity-0"
            >
              <div v-if="!hoveredDescription" class="absolute inset-0">
              I am a seasoned full-stack developer
              <span class="inline-flex items-center mx-1 cursor-pointer transform hover:scale-125 hover:rotate-12 transition-all duration-300">
                <Code2 :size="20" class="text-blue-600" />
              </span>
              with a primary focus on fintech
              <span class="inline-flex items-center mx-1 cursor-pointer transform hover:scale-125 hover:rotate-12 transition-all duration-300">
                <DollarSign :size="20" class="text-green-600" />
              </span>
              and automation
              <span class="inline-flex items-center mx-1 cursor-pointer transform hover:scale-125 hover:rotate-12 transition-all duration-300">
                <Zap :size="20" class="text-yellow-600" />
              </span>
              . Proficient in a wide range of programming languages
              <span class="inline-flex items-center mx-1 cursor-pointer transform hover:scale-125 hover:rotate-12 transition-all duration-300">
                <Layers :size="20" class="text-purple-600" />
              </span>
              , I have collaborated with 70+ organizations
              <span class="inline-flex items-center mx-1 cursor-pointer transform hover:scale-125 hover:rotate-12 transition-all duration-300">
                <Users :size="20" class="text-orange-600" />
              </span>
              , delivering mission-critical applications handling substantial financial and sensitive data
              <span class="inline-flex items-center mx-1 cursor-pointer transform hover:scale-125 hover:rotate-12 transition-all duration-300">
                <ShieldCheck :size="20" class="text-red-600" />
              </span>
              .
              </div>
            </transition>
          </div>

          <div class="space-y-3 leading-6 text-left xl:space-y-5 uppercase">
            <div 
              v-for="([name, data], idx) in socialLinks" 
              :key="name" 
              class="relative inline-block mr-3"
              @mouseenter="handleMouseEnter(data.description)"
              @mouseleave="handleMouseLeave()"
            >
              <Sbut :textinput="name" :SocialLinks="data.url" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import ContactEmail from "@/components/ContactEmail.vue";
import Sbut from "@/components/Sbut.vue";
import { Code2, DollarSign, Zap, Layers, Users, ShieldCheck } from "lucide-vue-next";

const socialLinksObj = {
  Github: {
    url: "https://github.com/besoeasy",
    description: "Understand my projects on GitHub and maybe find inspiration for coding?"
  },
  NOSTR: {
    url: "https://nosta.me/besoeasy@zaps.lol",
    description: "Connect with me on the decentralized social network"
  },
  Blog: {
    url: "https://tinyurl.com/soeasyblog",
    description: "Read my thoughts, tutorials, and tech insights"
  },
  steam: {
    url: "https://steamcommunity.com/id/besoeasy",
    description: "Check out my gaming profile and let's play together"
  }
};

function shuffle(array) {
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
  return array;
}

const hoveredDescription = ref("");
const hoverTimeout = ref(null);
const socialLinks = ref(shuffle(Object.entries(socialLinksObj)));

function handleMouseEnter(description) {
  // Clear any existing timeout
  if (hoverTimeout.value) {
    clearTimeout(hoverTimeout.value);
  }
  // Delay showing the description by 400ms
  hoverTimeout.value = setTimeout(() => {
    hoveredDescription.value = description;
  }, 400);
}

function handleMouseLeave() {
  // Clear timeout if mouse leaves before delay completes
  if (hoverTimeout.value) {
    clearTimeout(hoverTimeout.value);
    hoverTimeout.value = null;
  }
  // Clear description immediately
  hoveredDescription.value = "";
}
</script>
