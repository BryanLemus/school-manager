<template>
  <tr class="DatagridRow" :class="{ 'DatagridRow--selected': selected }">
    <td v-if="selectable">
      <input type="checkbox" :checked="selected" />
    </td>
    <slot />
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
});
</script>
