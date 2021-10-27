<template>
  <div class="Labeler">
    <label class="Labeler-label">{{ label }}</label>
    <div class="Labeler-content">
      <slot />
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "Labeler",
  props: {
    label: { type: String, required: true },
  },
});
</script>
