<template>
  <div
    class="Tile"
    :class="`Tile--${size}`"
    :style="{ background: background, color: color }"
  >
    <div class="Tile-icon" :style="{color: background}">
      <font-awesome-icon :icon="icon" />
    </div>
    <div class="Tile-title">
      {{ title }}
    </div>
    <div class="Tile-content">
      <slot />
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
    icon: { type: String, default: "arrow-right" },
    background: { type: String, default: "whitesmoke" },
    color: { type: String, default: "black" },
  },
});
</script>