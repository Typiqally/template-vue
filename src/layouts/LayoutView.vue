<template>
  <component :is="context.layout">
    <slot />
  </component>
</template>

<script lang="ts">
import LayoutDefault from "@/layouts/LayoutDefault.vue";
import { shallowRef, watch } from "vue";
import { useRoute } from "vue-router";
import { Vue, setup } from "vue-class-component";

export default class LayoutView extends Vue {
  context = setup(() => {
    const layout = shallowRef(LayoutDefault);
    const route = useRoute();

    watch(
      () => route.meta,
      async (meta) => {
        try {
          const component = await require(`@/layouts/${meta.layout}.vue`);
          layout.value = component?.default || LayoutDefault;
        } catch (e) {
          layout.value = LayoutDefault;
        }
      }
    );

    return { layout };
  });
}
</script>
