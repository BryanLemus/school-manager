<template>
  <router-view style="grid-row: 2" />
  <navbar
    :items="[
      { value: 'Home', title: 'Home', icon: 'home', isSelected: true },
      { value: 'users', title: 'Users', icon: 'users' },
      { value: 'students', title: 'Students', icon: 'user-graduate' },
      { value: 'inventory', title: 'Inventory', icon: 'boxes' },
      { value: 'expenses', title: 'Expenses', icon: 'receipt' },
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
</style>
