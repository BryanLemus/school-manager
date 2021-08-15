<template>
  <div class="Navbar">
    <div
      class="NavbarItem"
      v-for="(item, index) in items"
      :key="index"
      :class="{ 'NavbarItem--selected': selected.value === item.value }"
      @click="select(item)"
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
  value: string;
  isSelected: boolean;
}
import router from "@/router";
import { defineComponent } from "vue";

export default defineComponent({
  name: "Navbar",
  data() {
    return {
      selected: this.items?.find((x) => x.isSelected === true),
    };
  },
  props: {
    value: String,
    items: Array as () => NavbarItem[],
  },
  methods: {
    select(item: NavbarItem): void {
      this.selected = item;
      router.push({ name: item.value });
    },
  },
});
</script>