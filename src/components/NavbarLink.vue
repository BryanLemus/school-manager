<template>
  <router-link class="NavbarLink" :to="to" :aria-selected="selected">
    <font-awesome-icon :icon="icon" />
    <label>{{ text }}</label>
  </router-link>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "NavbarLink",
  props: {
    to: String,
    text: String,
    icon: String,
    selected: { type: Boolean, default: false },
  },
});
</script>
