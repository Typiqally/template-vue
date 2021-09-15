<template>
  <layout-view>
    <router-view />
  </layout-view>
</template>

<script lang="ts">
import LayoutView from "@/layouts/LayoutView.vue";
import { Options, Vue } from "vue-class-component";

@Options({
  components: {
    LayoutView,
  },
})
export default class App extends Vue {}
</script>
