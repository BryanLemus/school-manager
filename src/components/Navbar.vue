<template>
  <div class="Navbar">
    <div
      class="NavbarItem"
      v-for="(item, index) in items"
      :key="index"
      :class="{ 'NavbarItem--selected': (selected === index) }"
      @click="select(index)"
    >
      <div class="NavbarItem-icon">
        <font-awesome-icon :icon="item.icon" />
      </div>
      <label class="NavbarItem-title">
        {{ item.title }}
      </label>
    </div>
  </div>
</template>

<script lang="ts">
interface NavbarItem {
  title: string;
  icon: string;
  isSelected: boolean;
}
import { defineComponent } from "vue";

export default defineComponent({
  name: "Navbar",
  data() {
    return {
      selected: this.items?.findIndex((x) => x.isSelected === true),
    };
  },
  props: {
    items: Array as () => NavbarItem[],
  },
  methods: {
    select(index: number): void {
      this.selected = index;
    },
  },
});
</script>