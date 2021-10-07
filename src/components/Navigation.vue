<template>
  <nav class="Navigation">
    <navigation-item
      v-for="link in links"
      :key="link.value"
      :value="link.value"
      :label="link.label"
      :icon="link.icon"
      :selected="link.value === value"
      @click="select(link)"
    />
  </nav>
</template>

<script lang="ts">
interface NavbarLink {
  value: string;
  label: string;
  icon: string;
  selected: boolean;
}

import { defineComponent } from "vue";
import NavigationItem from "./NavigationItem.vue";

export default defineComponent({
  components: { NavigationItem },
  name: "Navigation",
  data() {
    return {
      value: (this.links?.find((x) => x.selected === true) as NavbarLink).value,
    };
  },

  props: {
    links: Array as () => NavbarLink[],
  },

  methods: {
    select(link: NavbarLink): void {
      this.value = link.value
    }
  }
});
</script>