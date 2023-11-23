<template>
  <section
    class="py-24 lg:pb-32 overflow-hidden transition-colors"
    @click="changeBackgroundColor"
    :style="{ backgroundColor: backgroundColor }"
  >
    <div class="container px-4 mx-auto">
      <div class="flex flex-wrap lg:items-center -m-8">
        <div class="w-full md:w-1/2 p-8">
          <div
            class="max-w-max mx-auto transform hover:-translate-y-1 transition duration-500"
          >
            <img
              class="rounded-2xl transition duration-500"
              src="/aman.jpg"
              alt=""
            />
          </div>
        </div>
        <div class="w-full md:w-1/2 p-8">
          <div class="md:max-w-lg">
            <svg
              class="mb-8"
              width="41"
              height="31"
              viewBox="0 0 41 31"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            ></svg>
            <p
              class="mb-8 text-2xl font-semibold tracking-tight leading-7 text-gray-700 sm:leading-10"
            >
              <span
                >I am a seasoned full-stack developer with a primary focus on
                fintech and automation. Proficient in a wide range of
                programming languages, I have collaborated with 70+
                organizations, delivering mission-critical applications handling
                substantial financial and sensitive data.</span
              >
            </p>
            <p
              class="font-semibold tracking-tight text-2xl"
              contenteditable="false"
            >
              Aman Singh Katal
            </p>
            <p class="text-sm tracking-tight" contenteditable="false">
              <ContactEmail />
            </p>

            <div
              class="space-y-3 space-y-4 leading-6 text-left xl:space-y-5 uppercase mt-8"
            >
              <div class="relative inline-block mr-3">
                <Sbut
                  textinput="Telegram"
                  SocialLinks="https://t.me/besoeasy"
                />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut
                  textinput="Github"
                  SocialLinks="https://github.com/besoeasy"
                />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut
                  textinput="Instagram"
                  SocialLinks="https://instagram.com/besoeasy"
                />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut
                  textinput="Linkedin"
                  SocialLinks="https://www.linkedin.com/in/besoeasy"
                />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut
                  textinput="Steam"
                  SocialLinks="https://steamcommunity.com/id/besoeasy"
                />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut
                  textinput="Medium"
                  SocialLinks="https://besoeasy.medium.com/"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import ContactEmail from "./components/ContactEmail.vue";
import Sbut from "./components/Sbut.vue";
import { ref, computed } from "vue";

const targetColor = ref("#ffffff");
const currentColor = ref("#ffffff");

const changeBackgroundColor = () => {
  const randomColor = "#" + Math.floor(Math.random() * 16777215).toString(16);
  targetColor.value = randomColor;

  setTimeout(() => {
    targetColor.value = "#ffffff";
    console.log("reset");
  }, 6 * 1000);
};

const backgroundColor = computed(() => {
  return currentColor.value;
});

setInterval(() => {
  if (currentColor.value !== targetColor.value) {
    currentColor.value = targetColor.value;
  }
}, 500); 
</script>

<style>
.transition-colors {
  transition: background-color 6s ease; 
}
</style>
