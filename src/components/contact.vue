<template>
	<div class="py-5 lg:py-10">
		<div class="grid grid-cols-1 md:grid-cols-2 gap-2">
			<div class="m-auto">
				<lottie-player src="ani/contact.json" background="transparent" speed="1" loop autoplay></lottie-player>
			</div>
			<div class="m-auto">
				<p class="text-4xl my-6 text-left uppercase">
					<span class="text-yellow-500">Email</span> Me 👇<br /><br />
					<span class="text-yellow-500">{{ email }}</span
					>@besoeasy.com
				</p>
			</div>
		</div>
	</div>
</template>

<script>
	import axios from 'axios';

	export default {
		data() {
			return { email: 'a@besoeasy.com' };
		},

		async mounted() {
			const { data } = await axios.get('https://ipapi.co/json/');

			console.log(data);

			const { city, country } = data;

			if (city) {
				this.email = city + '-' + country;
			}
		},
	};
</script>
