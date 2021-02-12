<template>
  <div>
    <img src="../assets/logo.png" alt="Vue Logo" />
    <p>{{ bienvenue || "Ho la con de tes morts tu te casse ou bien" }}</p>
    <button @click="sendBounce">Bounces with parents : {{ bounces }}</button>
  </div>
</template>

<script>
export default {
  name: "logo",
  props: ["bienvenue", "bounces"],

  data() {
    return {};
  },

  methods: {
    sendBounce() {
      this.$emit("sendBounce");
    },
  },
};
</script>

<style scoped>
img {
  height: 200px;
}
</style>
