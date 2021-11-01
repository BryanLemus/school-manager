<template>
  <div class="PagesView">
    <slot />
  </div>
</template>

<script lang="ts">
import { defineComponent, VNode } from "vue";

export default defineComponent({
  name: "PagesView",
  props: {
    value: String,
  },
  computed: {
    items(): any[] {
      const values: any[] = [];
      // Get pages
      const items = (this.$slots as any).default();

      // If not there pages, return an void array
      if (!items) return [];

      // Extract Pages Values
      items.forEach((item: VNode): void => {
        if (item.props) values.push(item.props);
      });
      return values;
    },
  },
});
</script>
