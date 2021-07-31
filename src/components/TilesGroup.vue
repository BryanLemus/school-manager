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
  padding: 1rem;
  display: grid;
  grid-auto-flow: dense;
  grid-template-columns: repeat(auto-fill, minmax(128px, 1fr));
  grid-auto-rows: 128px;
  grid-gap: 1rem;
  margin-top: 1rem;
}
</style>