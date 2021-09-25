<template>
  <button class="FlatButton">
    <font-awesome-icon :icon="icon" />
    <label>{{ text }}</label>
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
