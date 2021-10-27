<template>
  <sidebar
    mode="compact"
    :links="[
      { value: '/', icon: 'home', label: 'Home' },
      { value: '/students', icon: 'user-graduate', label: 'Students' },
    ]"
  />

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
import Sidebar from "./components/Sidebar.vue";

export default defineComponent({
  components: { Navigation, Appbar, FlatButton, Sidebar },
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
