<template>
  <div class="InputBox">
    <label v-if="label !== undefined">{{ label }}</label>
    <input :type="type" :placeholder="placeholder" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "InputBox",
  props: {
    label: String,
    placeholder: String,
    type: { type: String, default: "text" },
  },
});
</script>