<template>
  <div
    class="Tile"
    :class="[`Tile--${size}`, color ? `Tile--${color}` : '']"
    :style="{ backgroundImage: background ? `url(${background})` : '' }"
  >
    <div class="Tile-title" :style="{ color: color }">
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
    color: { type: String, default: "#000" },
  },
});
</script>

<style lang="scss">
.Tile {
  display: grid;
  grid-template-rows: auto 1fr auto;
  border-radius: 1rem;
  padding: 1rem;
  user-select: none;
  background-color: #e9e9e9; // testing
  background-origin: center;
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;

  /* elements */
  &-title {
    grid-row: 1/2;
    font-size: 1.2rem;
    font-weight: 600;
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
    background-color: #fffc;
    backdrop-filter: blur(8px);
    border-radius: 100%;
    padding: 0.5rem;
    text-align: center;
  }

  /* Sizes */
  &--small {
    grid-column: span 1;
    grid-row: span 1;
    aspect-ratio: 4/3;
  }
  &--medium {
    grid-column: span 2;
    grid-row: span 1;
    aspect-ratio: 16/5;
  }
  &--large {
    grid-column: span 2;
    grid-row: span 2;
    aspect-ratio: 13/12;
  }
}
</style>