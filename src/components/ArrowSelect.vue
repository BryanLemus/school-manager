<template>
  <div class="ArrowSelect">
    <button class="ArrowSelect-BackButton" @click="back">
      <font-awesome-icon icon="chevron-left" />
    </button>
    <div class="ArrowSelect-Value body1">{{ selected }}</div>
    <button class="ArrowSelect-NextButton" @click="next">
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
      selected: this.items.find((item) => (item = this.value)),
    };
  },
  props: {
    value: { type: [String, Number, Object], required: true },
    items: { type: Array, required: true },
  },
  methods: {
    next(): void {
      let current = this.items.findIndex((item) => item === this.selected);
      if (current + 1 < this.items.length) {
        this.selected = this.items[current + 1];
        this.$emit("input", this.selected);
      }
    },
    back(): void {
      let current = this.items.findIndex((item) => item === this.selected);
      if (current - 1 > 0) {
        this.selected = this.items[current - 1];
        this.$emit("input", this.selected);
      }
    },
  },
});
</script>
