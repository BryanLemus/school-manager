<template>
  <div class="Tile" :class="[`Tile--${size}`, color ? `Tile--${color}` : '']">
    <div class="Tile-title">
      {{ title }}
    </div>
    <div class="Tile-content">
      <slot />
    </div>
    <div class="Tile-icon">
      <font-awesome-icon :icon="icon" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Tile",
  props: {
    title: { type: String, required: true },
    size: { type: String, default: "small" },
    background: { type: String, default: "" },
    icon: { type: String, default: "arrow-right" },
    color: { type: String },
  },
  computed: {
    bkgImage(): any {
      return require(this.background);
    },
  },
});
</script>

<style lang="scss">
.Tile {
  display: grid;
  grid-template-rows: auto 1fr auto;
  border-radius: 0.5rem;
  padding: 0.5rem;
  background-color: #e9e9e9; // testing
  /* elements */
  &-title {
    grid-row: 1/2;
    font-size: 1rem;
    font-weight: 500;
  }
  &-content {
    grid-row: 2/3;
  }
  &-icon {
    grid-row: 3/4;
    align-self: end;
    justify-self: end;
    width: 1rem;
    height: 1rem;
    background-color: #5a5a5a33;
    backdrop-filter: blur(8px);
    border-radius: 100%;
    padding: 0.5rem;
    text-align: center;
    vertical-align: center;
  }

  /* Sizes */
  &--small {
    grid-column: span 1;
    grid-row: span 1;
    aspect-ratio: 1/1;
  }
  &--medium {
    grid-column: span 2;
    grid-row: span 1;
    aspect-ratio: 2/1
  }
  &--large {
    grid-column: span 2;
    grid-row: span 2;
    aspect-ratio: 2/2
  }
}
</style>