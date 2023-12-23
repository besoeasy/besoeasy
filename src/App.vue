<template>
	<div class="px-4 m-auto max-w-7xl">
		<div class="flex flex-wrap lg:items-center min-h-screen">
			<div class="w-full md:w-2/3 p-8">
				<div class="m-auto transform hover:-translate-y-1 transition duration-500">
					<img class="rounded-2xl" src="/me.png" alt="" />
				</div>
			</div>
			<div class="w-full md:w-1/3 p-8">
				<div class="m-auto">
					<div class="font-bold text-3xl mb-2">AMAN SINGH KATAL</div>
					<div class="text-sm mb-8 rounded-2xl font-extralight">
						<ContactEmail />
					</div>

					<div class="mb-8 text-lg font-mono">
						I am a seasoned full-stack developer with a primary focus on fintech and automation.
						Proficient in a wide range of programming languages, I have collaborated with 70+
						organizations, delivering mission-critical applications handling substantial financial and
						sensitive data.
					</div>

					<div class="space-y-3 leading-6 text-left xl:space-y-5 uppercase mt-8">
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
</template>

<script setup>
	import ContactEmail from './components/ContactEmail.vue';
	import Sbut from './components/Sbut.vue';
</script>
