<template>
  <button class="FlatButton">
    <font-awesome-icon v-if="icon !== undefined" :icon="icon" />
    <label v-if="text !== undefined">{{ text }}</label>
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "FlatButton",
  props: {
    icon: String,
    text: String,
  },
});
</script>
