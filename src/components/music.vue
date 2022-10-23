<template>
	<div class="py-5 lg:py-10">
		<div class="grid grid-cols-1 md:grid-cols-2 gap-2">
			<div class="m-auto">
				<lottie-player src="ani/music.json" background="transparent" speed="1" loop autoplay></lottie-player>
			</div>
			<div class="m-auto">
				<p class="text-4xl my-6 text-left uppercase">
					<span class="text-yellow-500">Listening </span> 🎵<br /><br />
					{{ song }}
				</p>
			</div>
		</div>
	</div>
</template>

<script>
	import axios from 'axios';

	export default {
		data() {
			return {
				song: '....',
			};
		},

		async mounted() {
			const { data } = await axios.get('https://ws.audioscrobbler.com/2.0/?method=user.getrecenttracks&user=besoeasy&api_key=9b6009eca365ded3a03c2b9673d54eb9&format=json');
			const { name, artist } = data.recenttracks.track[0];

			console.log(name, artist);

			this.song = name + ' by ' + artist['#text'];
		},
	};
</script>
