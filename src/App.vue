<template>
	<div class="flex justify-center items-center h-screen bg-yellow-50">
		<div class="m-auto max-w-7xl p-10">
			<div class="grid grid-cols-1 lg:grid-cols-2">
				<div class="m-auto hidden md:block"><lottie-player src="https://assets5.lottiefiles.com/packages/lf20_rmizwv6a.json" background="transparent" speed="1" loop="" autoplay=""></lottie-player></div>

				<div class="m-auto">
					<div class="text-left">
						<div class="text-5xl font-bold my-2">AMAN SINGH KATAL</div>
						<div class="my-10"></div>
						<p>
							I am a versatile professional with expertise in computer hacking, web development, web3 development, and work automation. I am passionate about exploring the depths of technology and leveraging it to create innovative solutions. Alongside my work, I also engage in
							part-time angel investing, supporting promising ventures with my knowledge and resources.
						</p>
						<div class="my-10"></div>
						<SocialLinks />

						<div class="my-10"></div>

						<div class="text-xl">
							<p><ContactEmail /></p>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import ContactEmail from './components/ContactEmail.vue';
	import SocialLinks from './components/SocialLinks.vue';

	export default {
		components: {
			SocialLinks,
			ContactEmail,
		},
	};
</script>
