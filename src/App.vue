<template>
  <router-view />
  <navbar
    :items="[
      { title: 'Home', icon: 'home', isSelected: true },
      { title: 'Users', icon: 'users' },
      { title: 'Students', icon: 'user-graduate' },
      { title: 'Inventory', icon: 'boxes' },
      { title: 'Expenses', icon: 'receipt' },
    ]"
  />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Navbar from "./components/Navbar.vue";

export default defineComponent({
  components: { Navbar },
});
</script>

<style lang="scss">
@import "./assets/scss/main.scss";

#app {
  display: grid;
  grid-template-rows: calc(100% + 51px) auto;
  row-gap: 0.5rem;
  .Navbar {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
  }
}
</style>
