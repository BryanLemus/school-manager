<template>
  <div class="Appbar">
    <div class="Appbar-left">
      <slot name="left" />
    </div>
    <div class="Appbar-middle">
      <slot name="middle" />
    </div>
    <div class="Appbar-right">
      <slot name="right" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Appbar",
});
</script>