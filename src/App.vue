<template>
	<div class="bg-yellow-50">
		<div class="container max-w-7xl mx-auto px-10 py-40">
			<mainx />

			<music />

			<social />

			<contact />
		</div>
	</div>
</template>

<script>
	import mainx from './components/main.vue';

	import music from './components/music.vue';

	import contact from './components/contact.vue';

	import social from './components/social.vue';

	export default {
		name: 'App',
		components: { mainx, music, contact, social },
	};
</script>
