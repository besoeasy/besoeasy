<template>
  <div class="p-5 m-auto max-w-7xl">
    <div
      class="flex sm:flex-row flex-col gap-10 items-center justify-center min-h-screen"
    >
      <div class="w-full md:w-3/5">
        <div
          class="m-auto transform hover:-translate-y-1 transition duration-500"
        >
          <img class="rounded-2xl" src="/me.png" alt="" />
        </div>
      </div>
      <div class="w-full md:w-2/5">
        <div class="m-auto">
          <div class="text-2xl lg:text-4xl mb-2 text-pretty">
            AMAN SINGH KATAL
          </div>
          <div class="text-xl mb-5 font-semibold">
            <ContactEmail />
          </div>

          <div class="mb-5 text-lg text-gray-800">
            I am a seasoned full-stack developer with a primary focus on fintech
            and automation. Proficient in a wide range of programming languages,
            I have collaborated with 70+ organizations, delivering
            mission-critical applications handling substantial financial and
            sensitive data.
          </div>

          <div class="space-y-3 leading-6 text-left xl:space-y-5 uppercase">
            <div
              v-for="(url, name) in socialLinks"
              :key="name"
              class="relative inline-block mr-3"
            >
              <Sbut :textinput="name" :SocialLinks="url" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive } from "vue";
import ContactEmail from "./components/ContactEmail.vue";
import Sbut from "./components/Sbut.vue";

const socialLinks = reactive({
  NOSTR: "https://nosta.me/besoeasy@zaps.lol",
  Telegram: "https://t.me/besoeasy",
  Github: "https://github.com/besoeasy",
  Instagram: "https://instagram.com/besoeasy",
  Linkedin: "https://www.linkedin.com/in/besoeasy",
  Steam: "https://steamcommunity.com/id/besoeasy",
});
</script>
