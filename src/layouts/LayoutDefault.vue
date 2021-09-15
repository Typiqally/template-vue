<template>
  <router-link to="/">Home</router-link>
  /
  <router-link to="/about">About</router-link>
  <slot />
</template>

<script>
import { Vue } from "vue-class-component";

export default class LayoutDefault extends Vue {}
</script>

<style lang="scss">
body {
  font-family: "Arial", sans-serif;
}

a {
  color: #42b883;
}
</style>
