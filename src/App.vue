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
            <a class="p-5 flex items-center bg-white hover:bg-gray-100 rounded-lg transition duration-200 focus:ring-4 focus:ring-indigo-300" href="#">
              <div class="inline-block mr-4">

              </div>
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
            <path fill-rule="evenodd" clip-rule="evenodd" d="M31.7708 8.39844e-08C34.1048 -0.00032041 36.3455 0.916653 38.0096 2.55319C39.6737 4.18974 40.628 6.41474 40.6667 8.74842C40.8954 10.947 40.8624 14.1876 39.3755 17.934C37.8581 21.7617 34.892 25.9352 29.4833 29.9917C29.2163 30.1919 28.9125 30.3376 28.5891 30.4205C28.2658 30.5033 27.9293 30.5217 27.5989 30.4745C26.9316 30.3791 26.3294 30.0226 25.925 29.4833C25.5205 28.9441 25.3469 28.2662 25.4422 27.5989C25.5375 26.9316 25.8941 26.3295 26.4333 25.925C30.4085 22.9436 32.6884 20.0436 33.9897 17.5121C32.6754 17.8491 31.3014 17.8812 29.9727 17.606C28.6441 17.3308 27.3959 16.7556 26.3235 15.9243C25.2511 15.093 24.383 14.0276 23.7853 12.8094C23.1876 11.5913 22.8763 10.2527 22.875 8.89583C22.875 6.53651 23.8122 4.27382 25.4805 2.60553C27.1488 0.937237 29.4115 8.39844e-08 31.7708 8.39844e-08ZM8.89583 8.39844e-08C11.2298 -0.00032041 13.4705 0.916653 15.1346 2.55319C16.7987 4.18974 17.753 6.41474 17.7917 8.74842C18.0204 10.947 17.9874 14.1876 16.5005 17.934C14.9831 21.7617 12.017 25.9352 6.60833 29.9917C6.34131 30.1919 6.03746 30.3376 5.71413 30.4205C5.39079 30.5033 5.05431 30.5217 4.72389 30.4745C4.05657 30.3791 3.45445 30.0226 3.05 29.4833C2.64554 28.9441 2.47188 28.2662 2.56721 27.5989C2.66254 26.9316 3.01906 26.3295 3.55833 25.925C7.5335 22.9436 9.81337 20.0436 11.1147 17.5121C9.8004 17.8485 8.42659 17.8803 7.09815 17.6049C5.76971 17.3295 4.52174 16.7542 3.4495 15.923C2.37726 15.0918 1.50909 14.0266 0.911267 12.8088C0.31344 11.5909 0.00175485 10.2525 0 8.89583C0 6.53651 0.937237 4.27382 2.60553 2.60553C4.27382 0.937237 6.53651 8.39844e-08 8.89583 8.39844e-08ZM31.7708 5.08333C31.0332 5.0832 30.3114 5.29702 29.6929 5.6989C29.0744 6.10077 28.5858 6.67343 28.2862 7.34746C27.9866 8.02149 27.889 8.76795 28.0052 9.49634C28.1214 10.2247 28.4464 10.9038 28.9407 11.4512C29.4351 11.9986 30.0777 12.3908 30.7905 12.5803C31.5033 12.7699 32.2558 12.7485 32.9568 12.5189C33.6578 12.2894 34.2771 11.8614 34.7397 11.2868C35.2022 10.7123 35.4883 10.016 35.563 9.28217L35.5833 8.87042C35.5766 7.86369 35.172 6.90048 34.4577 6.19099C33.7435 5.48149 32.7776 5.08331 31.7708 5.08333ZM8.89583 5.08333C8.15823 5.0832 7.43643 5.29702 6.81792 5.6989C6.19942 6.10077 5.71076 6.67343 5.4112 7.34746C5.11164 8.02149 5.01403 8.76795 5.13021 9.49634C5.24639 10.2247 5.57137 10.9038 6.06575 11.4512C6.56013 11.9986 7.20268 12.3908 7.91551 12.5803C8.62835 12.7699 9.38086 12.7485 10.0818 12.5189C10.7828 12.2894 11.4021 11.8614 11.8647 11.2868C12.3273 10.7123 12.6133 10.016 12.688 9.28217L12.7083 8.87042C12.7016 7.86369 12.297 6.90048 11.5827 6.19099C10.8685 5.48149 9.90258 5.08331 8.89583 5.08333Z" fill="black"></path>
          </svg>
          <p class="mb-8 text-3xl font-semibold" style="letter-spacing: -0.5px;">


            <span>I am a seasoned full-stack developer with a primary focus on fintech and automation. Proficient in a wide range of programming languages, I have collaborated with 70+ organizations, delivering mission-critical applications handling substantial financial and sensitive data. </span>
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
