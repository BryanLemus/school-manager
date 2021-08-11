<template>
  <div class="NavigationBar">
    <div class="NavigationBarItem" v-for="(item, index) in items" :key="index">
      <div class="NavigationBarItem-icon">
        <font-awesome-icon :icon="item.icon" />
      </div>
      <label class="NavigationBarItem-title">
        {{ item.title }}
      </label>
    </div>
  </div>
</template>

<script lang="ts">
interface NavigationBarItem {
  title: string;
  icon: string;
}
import { defineComponent } from "vue";

export default defineComponent({
  name: "NavigationBar",
  props: {
    items: Array as () => NavigationBarItem[],
  },
});
</script>

<style lang="scss">
.NavigationBar {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(60px,100%), 1fr));
  justify-items: center;
  background: white;
  overflow: hidden;
}

.NavigationBarItem {
  display: grid;
  grid-template-rows: auto auto;
  overflow: hidden;
  justify-items: center;
  &-icon {
    padding: 0.5rem;
  }
  &-title {
    display: -webkit-box;
    -webkit-line-clamp: 1;
    -webkit-box-orient: vertical;
    overflow: hidden;
    font-size: 12px;
    text-align: center;
    grid-row: 2;
  }
}
</style>