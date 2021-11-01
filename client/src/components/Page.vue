<template>
  <div class="Page">
    <slot />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Page",
  props: {
    value: { type: String, required: true },
    header: { type: String, required: true },
  },
});
</script>
