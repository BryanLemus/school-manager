<template>
  <div
    class="Tile"
    :class="[`Tile--${size}`, `Tile--${color}`]"
    :style="{ backgroundImage: background ? `url(${background})` : '' }"
  >
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
    color: { type: String, default: "blue" },
  },
});
</script>