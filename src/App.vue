<template>
  <appbar>
    <template v-slot:left>
      <label class="subtitle1">Logo</label>
    </template>
    <template v-slot:right>
      <button>Sign Up</button>
      <button>Sing In</button>
    </template>
  </appbar>
  <div class="view">
    <router-view style="grid-row: 2" />
  </div>
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
import Appbar from "./components/Appbar.vue";
import Navbar from "./components/Navbar.vue";

export default defineComponent({
  components: { Navbar, Appbar },
});
</script>

<style lang="scss">
@import "./assets/scss/main.scss";
</style>
