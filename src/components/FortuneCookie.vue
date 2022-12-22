<template>
  <p>{{ fortune }}</p>
  <button @click.prevent="getNewFortune">Click me</button>
</template>

<script>
export default {
  name: "fortune-cookie",
  components: {},
  data() {
    return {};
  },
  methods: {
    getNewFortune() {
      fetch("http://localhost:3000/get")
        .then((response) => {
          return response.json();
        })
        .then((data) => {
          console.log(data);
        })
        .catch((error) => {
          console.error(error);
        });
    },
  },
};
</script>
