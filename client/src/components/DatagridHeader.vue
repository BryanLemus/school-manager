<template>
  <th class="DatagridHeader">
    <label class="DatagridHeader-label">
      {{ text }}
    </label>
    <button v-if="sortDirection" class="DatagridHeader-sortBtn">
      <font-awesome-icon
        v-if="sortDirection === 'decendent'"
        icon="sort-down"
      />
      <font-awesome-icon v-if="sortDirection === 'ascendent'" icon="sort-up" />
    </button>
  </th>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "DatagridHeader",
  props: {
    text: String,
    sortDirection: {
      type: String,
      validator: (sortDirection: string) => {
        return ["ascendent", "decendent"].includes(sortDirection);
      },
    },
  },
});
</script>
