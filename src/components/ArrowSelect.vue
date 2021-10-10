<template>
  <div class="ArrowSelect">
    <button class="ArrowSelect-BackButton">
      <font-awesome-icon icon="chevron-left" />
    </button>
    <div class="ArrowSelect-Value body1">{{ selected }}</div>
    <button class="ArrowSelect-NextButton">
      <font-awesome-icon icon="chevron-right" />
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ArrowSelect",
  data() {
    return {
      selected: this.items.find(x => x === this.value),
    };
  },
  props: {
    items: { type: Array as () => any[], required: true },
    value: { type: Object as () => any, required: true },
  },
});
</script>
