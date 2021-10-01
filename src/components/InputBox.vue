<template>
  <div class="InputBox">
    <label class="InputBox-label" v-if="label !== undefined"
      >{{ label }}
      <input :name="name" :type="type" :placeholder="placeholder" />
    </label>
    <div class="InputBox-hint" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "InputBox",
  props: {
    name: String,
    type: { type: String, default: "text" },
    label: String,
    placeholder: String,
  },
});
</script>