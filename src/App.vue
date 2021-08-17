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
  <router-view style="grid-row: 2" />
  <navbar
    :items="[
      { value: 'Home', title: 'Home', icon: 'home', isSelected: true },
      { value: 'messages', title: 'Messages', icon: 'comments' },
      { value: 'settings', title: 'Settings', icon: 'cog' },
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
