<template>
  <div class="NavigationItem" :class="{ 'NavigationItem--selected': selected }">
    <font-awesome-icon :icon="icon" />
    <label>{{ label }}</label>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "NavigationItem",
  props: {
    value: { type: String, required: true },
    label: String,
    icon: String,
    selected: { type: Boolean, default: false },
  },
});
</script>
