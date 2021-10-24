<template>
  <div class="Sidebar" mode="compact">
    <div class="Sidebar-logo">
      <img alt="logo" src="../assets/images/logo.svg" />
    </div>
    <div class="Sidebar-navigation">
      <navigation :mode="mode" :links="links" />
    </div>
    <div class="Sidebar-footer">
      <flat-button icon="user" />
    </div>
  </div>
</template>

<script lang="ts">
interface NavigationItem {
  value: string;
  label: string;
  icon: string;
}

import { defineComponent } from "vue";
import Navigation from "./Navigation.vue";
import NavigationItem from "./NavigationItem.vue";
import FlatButton from "./FlatButton.vue";

export default defineComponent({
  components: { Navigation, NavigationItem, FlatButton },
  name: "Sidebar",
  props: {
    links: { type: Array as () => NavigationItem[] },
    mode: {
      type: String,
      default: "normal",
      validator(mode: string): boolean {
        return ["normal", "compact"].includes(mode);
      },
    },
  },
});
</script>
