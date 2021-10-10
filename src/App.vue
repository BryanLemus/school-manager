<template>
  <appbar>
    <template v-slot:left>
      <img id="logo" src="./assets/images/logo.svg" />
    </template>
    <template v-slot:right>
      <flat-button icon="user" text="@username"/>
    </template>
  </appbar>

  <router-view class="view" v-slot="{ Component, route }">
    <transition :name="route.meta.transition || 'fade'" mode="out-in">
      <component :is="Component" />
    </transition>
  </router-view>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Appbar from "./components/Appbar.vue";
import Navigation from "./components/Navigation.vue";
import FlatButton from "./components/FlatButton.vue";

export default defineComponent({
  components: { Navigation, Appbar, FlatButton },
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
