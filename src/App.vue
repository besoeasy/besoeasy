<template>
	<div class="m-auto container px-10">
		<div class="grid grid-cols-1 md:grid-cols-2 min-h-screen">
			<div class="m-auto transform hover:scale-150 transition duration-1000">
				<name class="my-3" />
				<social class="my-2" />

				<contact class="my-3" />
			</div>
			<div class="my-auto"><lottie-player src="index.json" background="transparent" speed="1" loop autoplay></lottie-player></div>
		</div>
	</div>
</template>

<script>
	import name from './components/name.vue';

	import contact from './components/contact.vue';

	import social from './components/social.vue';

	export default {
		components: { name, contact, social },
	};
</script>
