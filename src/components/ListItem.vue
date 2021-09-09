<template>
  <li class="ListItem" :aria-selected="selected">
    <slot />
  </li>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ListItem",
  props: {
    value: Object,
    selected: Boolean,
  },
});
</script>