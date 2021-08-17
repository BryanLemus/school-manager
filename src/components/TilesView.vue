<template>
  <div class="TilesView">
    <slot />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "TilesView",
});
</script>