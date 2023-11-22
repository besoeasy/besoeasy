<script setup>
  import ContactEmail from './components/ContactEmail.vue';
  import Sbut from './components/Sbut.vue';
</script>

<template>
  <section class="relative py-24 lg:pb-32 bg-white overflow-hidden">
    <div class="container px-4 mx-auto">
      <div class="flex flex-wrap lg:items-center -m-8">
        <div class="w-full md:w-1/2 p-8">
          <div class="relative max-w-max mx-auto transform hover:-translate-y-1 transition duration-500">
            <div class="absolute bottom-0 left-0 p-5">
              <a class="p-5 flex items-center bg-white hover:bg-gray-100 rounded-lg transition duration-200 focus:ring-4 focus:ring-indigo-300" href="https://t.me/besoeasy">
                 <span class="mr-2 font-semibold tracking-tight">Telegram Me</span>
                <div class="inline-block mr-2">
                  <svg width="5" height="6" viewBox="0 0 5 6" fill="none" xmlns="http://www.w3.org/2000/svg"><circle cx="2.5" cy="3" r="2.5" fill="#B8C1CC"></circle></svg>
                </div>
              </a>
            </div>
            <img class="rounded-2xl transition duration-500" src="https://besoeasy.com/aman.jpg" alt="">
          </div>
        </div>
        <div class="w-full md:w-1/2 p-8">
          <div class="md:max-w-lg">
            <svg class="mb-8" width="41" height="31" viewBox="0 0 41 31" fill="none" xmlns="http://www.w3.org/2000/svg">
              <!-- SVG Path -->
            </svg>
            <p class="mb-8 text-3xl font-semibold" style="letter-spacing: -0.5px;">
              <span>I am a seasoned full-stack developer with a primary focus on fintech and automation. Proficient in a wide range of programming languages, I have collaborated with 70+ organizations, delivering mission-critical applications handling substantial financial and sensitive data.</span>
            </p>
            <p class="font-semibold tracking-tight" contenteditable="false">Aman Singh Katal</p>
            <p class="text-sm tracking-tight" contenteditable="false"><ContactEmail /></p>
            
            <div class="space-y-3 space-y-4 leading-6 text-left xl:space-y-5 uppercase mt-8">
              <div class="relative inline-block mr-3">
                <Sbut textinput="Telegram" SocialLinks="https://t.me/besoeasy" />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut textinput="Github" SocialLinks="https://github.com/besoeasy" />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut textinput="Instagram" SocialLinks="https://instagram.com/besoeasy" />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut textinput="Linkedin" SocialLinks="https://www.linkedin.com/in/besoeasy" />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut textinput="Steam" SocialLinks="https://steamcommunity.com/id/besoeasy" />
              </div>
              <div class="relative inline-block mr-3">
                <Sbut textinput="Medium" SocialLinks="https://besoeasy.medium.com/" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
