<template>
  <appbar>
    <template v-slot:left>
      <img src="./assets/images/logo.svg" />
    </template>
    <template v-slot:right>
      <button>Username</button>
    </template>
  </appbar>

  <router-view class="view" v-slot="{ Component, route }">
    <transition :name="route.meta.transition || 'fade'" mode="out-in">
      <component :is="Component" />
    </transition>
  </router-view>

  <navbar
    :links="[
      { route: '/', text: 'Dashboard', icon: 'home', selected: true },
      { route: 'messages', text: 'Messages', icon: 'comments' },
      { route: 'settings', text: 'Settings', icon: 'cog' },
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

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
