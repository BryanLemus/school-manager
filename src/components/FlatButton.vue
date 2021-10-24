<template>
  <button class="FlatButton">
    <font-awesome-icon v-if="icon !== undefined" :icon="icon" />
    <label v-if="label !== undefined">{{ label }}</label>
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "FlatButton",
  props: {
    icon: String,
    label: String,
  },
});
</script>
