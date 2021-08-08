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

<style lang="scss">
.TilesView {
  display: grid;
  grid-auto-flow: dense;
  grid-template-columns: repeat(auto-fill, minmax(9rem, 1fr));
  grid-auto-rows: 1fr;
  grid-gap: 1rem;
}
</style>