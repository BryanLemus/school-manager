<template>
  <router-view/>
  <navigation-bar
    :items="[
      { title: 'Home', icon: 'home' },
      { title: 'Users', icon: 'users' },
      { title: 'Students', icon: 'user-graduate' },
      { title: 'Inventory', icon: 'boxes' },
      { title: 'Expenses', icon: 'receipt' },
    ]"
  />
</template>


<script lang="ts">
import { defineComponent } from "vue";
import NavigationBar from "./components/NavigationBar.vue";

export default defineComponent({
  components: { NavigationBar },
});
</script>

<style lang="scss">
@import "./assets/scss";

#app {
  display: grid;
  grid-template-rows: calc(100% + 50px) auto;
  row-gap: 0.5rem;
  .NavigationBar {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
  }
}
</style>
