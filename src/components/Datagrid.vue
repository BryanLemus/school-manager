<template>
  <div
    class="Datagrid"
    :class="{
      'Datagrid-selectable':
        selectMode === 'single' || selectMode === 'multiple',
    }"
  >
    <table>
      <thead>
        <tr class="Datagrid-row">
          <datagrid-header
            v-for="header in headers"
            :key="header.value"
            :text="header.text"
          />
        </tr>
      </thead>
      <tbody>
        <datagrid-row v-for="item in items" :key="item.id">
          <datagrid-cell v-for="header in headers" :key="header.value" :value="item[header.value]"/>
        </datagrid-row>
      </tbody>
      <tfoot></tfoot>
    </table>
  </div>
</template>

<script lang="ts">
interface DatagridHeader {
  text: string;
  value: string;
  sorteable?: boolean;
}

import { defineComponent } from "vue";
import DatagridHeader from "./DatagridHeader.vue";
import DatagridRow from "./DatagridRow.vue";
import DatagridCell from "./DatagridCell.vue";

export default defineComponent({
  components: { DatagridHeader, DatagridRow, DatagridCell },
  name: "Datagrid",
  props: {
    value: { type: Array },
    headers: {
      type: Array as () => DatagridHeader[],
      required: true,
      default: [],
    },
    items: {
      type: Array,
      required: true,
      default: [],
    },
    propKey: { type: String, default: "id" },
    selectMode: {
      type: String,
      default: "none",
      validator: (selectMode: string) =>
        ["single", "multiple", "none"].includes(selectMode),
    },
    sortBy: { type: Array as () => string[], default: ["id"] },
    groupBy: String,
    itemsPerPage: { type: Number },
    page: { type: Number, default: 1 },
  },
});
</script>
