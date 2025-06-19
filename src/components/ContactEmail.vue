<template>
  <div>{{ email }}@besoeasy.com</div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return { email: "a" };
  },

  async mounted() {
    const { data } = await axios.get("https://ipapi.co/json/");

    console.log(data);

    const { city } = data;

    if (city) {
      this.email = city.toLowerCase().replace(/[^a-zA-Z0-9]/g, "");
    }
  },
};
</script>
