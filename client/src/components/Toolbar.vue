<template>
  <div class="Toolbar">
    <slot />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Toolbar",
});
</script>