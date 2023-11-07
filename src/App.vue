<script setup>
	import ContactEmail from './components/ContactEmail.vue';
	import Sbut from './components/Sbut.vue';
</script>

<template>
	<div class="flex justify-center items-center h-screen">
		<div class="m-auto max-w-5xl p-10">
			<div class="grid grid-cols-1 lg:grid-cols-2">
				<div class="hidden md:block m-auto">
					<div class="hover:transform hover:scale-110 hover:transition-transform hover:duration-800">
						<lottie-player
							src="https://besoeasy.com/ani.json"
							background="transparent"
							loop
							autoplay
							class="w-full h-full"
						></lottie-player>
					</div>
				</div>

				<div class="text-left m-auto">
					<div class="text-3xl font-medium my-2">AMAN SINGH KATAL</div>
					<div class="border-t border-dotted border-gray-400 my-5"></div>
					<p>
						I am a seasoned full-stack developer with a primary focus on fintech and automation.
						Proficient in a wide range of programming languages, I have collaborated with 70+
						organizations, delivering mission-critical applications handling substantial financial and
						sensitive data. With a career spanning since 2013, my expertise in coding is exemplary.
					</p>

					<div class="border-t border-dotted border-gray-400 my-5"></div>

					<div class="space-y-3 space-y-4 leading-6 text-left xl:space-y-5 uppercase">
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

					<div class="border-t border-dotted border-gray-400 my-5"></div>

					<ContactEmail />
				</div>
			</div>
		</div>
	</div>
</template>
