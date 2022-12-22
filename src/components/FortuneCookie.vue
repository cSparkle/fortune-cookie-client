<template>
  <p v-show="fortune">{{ fortune }}</p>
  <button @click.prevent="getNewFortune">Click me</button>
</template>

<script>
export default {
  name: "fortune-cookie",
  components: {},
  data() {
    return {
      fortune: "",
    };
  },
  methods: {
    getNewFortune() {
      fetch("http://localhost:3000/getFortune")
        .then((response) => {
          return response.json();
        })
        .then((data) => {
          this.fortune = data.fortune;
          console.log(data);
        })
        .catch((error) => {
          console.error(error);
        });
    },
  },
};
</script>
