<template>
	<div :style="{ backgroundImage: `url(${wave1})`, backgroundSize: 'cover' }">
		<div class="p-4 m-auto container">
			<div class="flex flex-col sm:flex-row gap-10 lg:items-center min-h-screen">
				<div class="w-full md:w-1/2">
					<div class="m-auto transform hover:-translate-y-1 transition duration-500">
						<img class="rounded-2xl border-solid border-8 border-white" src="/me.png" alt="" />
					</div>
				</div>
				<div class="w-full md:w-1/2">
					<div class="m-auto">
						<div class="font-bold text-3xl lg:text-5xl mb-2 text-pretty">AMAN SINGH KATAL</div>
						<div class="text-xl mb-8">
							<ContactEmail />
						</div>

						<div class="mb-8 text-lg lg:text-2xl text-gray-800">
							I am a seasoned full-stack developer with a primary focus on fintech and
							automation. Proficient in a wide range of programming languages, I have
							collaborated with 70+ organizations, delivering mission-critical applications
							handling substantial financial and sensitive data.
						</div>

						<div class="space-y-3 leading-6 text-left xl:space-y-5 uppercase mt-8">
							<div class="relative inline-block mr-3">
								<Sbut textinput="Telegram" SocialLinks="https://t.me/besoeasy" />
							</div>
							<div class="relative inline-block mr-3">
								<Sbut textinput="Github" SocialLinks="https://github.com/besoeasy" />
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
								<Sbut textinput="Medium" SocialLinks="https://besoeasy.medium.com/" />
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
	import ContactEmail from './components/ContactEmail.vue';
	import Sbut from './components/Sbut.vue';

	import wave1 from './assets/blob-haikei.svg';
</script>
