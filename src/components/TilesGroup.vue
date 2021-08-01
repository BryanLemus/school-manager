<template>
  <div class="TilesGroup">
    <slot />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "TilesGroup",
});
</script>

<style lang="scss">
.TilesGroup {
  display: grid;
  grid-auto-flow: dense;
  grid-template-columns: repeat(auto-fit, minmax(8rem, 1fr));
  grid-auto-rows: minmax(10rem, 1fr);
  grid-gap: 1rem;
}
</style>