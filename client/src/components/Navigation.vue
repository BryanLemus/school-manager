<template>
  <nav class="Navigation" :class="{ 'Navigation-compact': mode === 'compact' }">
    <navigation-item
      v-for="link in links"
      :key="link.value"
      :value="link.value"
      :selected="link.value === selected"
      :label="link.label"
      :icon="link.icon"
      @click="select(link)"
    />
  </nav>
</template>

<script lang="ts">
interface NavigationItem {
  value: string;
  label: string;
  icon: string;
}

import router from "@/router";
import { defineComponent } from "vue";
import NavigationItem from "./NavigationItem.vue";

export default defineComponent({
  components: { NavigationItem },
  name: "Navigation",
  computed: {
    selected(): string {
      return this.$route.path;
    },
  },
  props: {
    links: {
      type: Array as () => NavigationItem[],
      required: true,
      default: () => [],
    },
    mode: {
      type: String,
      default: "normal",
      validator(mode: string): boolean {
        return ["normal", "compact"].includes(mode);
      },
    },
  },
  methods: {
    select(link: NavigationItem): void {
      router.push(link.value);
    },
  },
});
</script>
