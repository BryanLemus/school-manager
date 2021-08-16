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
  grid-template-columns: repeat(auto-fit, 9rem);
  grid-auto-rows: minmax(9rem, auto);
  grid-gap: 1rem;
  justify-content: center;
}
</style>