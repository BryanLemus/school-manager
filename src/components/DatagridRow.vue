<template>
  <tr class="DatagridRow" :class="{ 'DatagridRow--selected': selected }">
    <td v-if="selectable">
      <input type="checkbox" :checked="selected" />
    </td>
    <slot />
  </tr>
  <tr v-if="selected" class="DatagridRow-Details">
    <td :colspan="columnSpan">
      <slot name="details" />
    </td>
  </tr>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "DatagridRow",
  props: {
    selectable: Boolean,
    selected: Boolean,
  },
  computed: {
    columnSpan(): number | undefined {
      console.log(this.$slots.default?.length);
      return this.$slots.default?.length;
    },
  },
});
</script>
