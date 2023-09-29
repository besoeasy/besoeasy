<template>
	<div class="hover:transform hover:scale-110 hover:transition-transform hover:duration-800">
		<lottie-player :src="'https://besoeasy.com/' + loc" background="transparent" loop autoplay class="w-full h-full"></lottie-player>
	</div>
</template>

<script>
	export default {
		name: 'Animation',
		props: {
			loc: {
				type: String,
				required: true,
			},
		},
	};
</script>
