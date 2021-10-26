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
        <datagrid-row
          v-for="item in items"
          :key="item.id"
          :selected="this.selection.includes(item)"
          @click="select(item)"
        >
          <datagrid-cell
            v-for="header in headers"
            :key="header.value"
            :value="item[header.value]"
            :editable="header.editable"
          />
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
  editable?: boolean;
}

import { defineComponent } from "vue";
import DatagridHeader from "./DatagridHeader.vue";
import DatagridRow from "./DatagridRow.vue";
import DatagridCell from "./DatagridCell.vue";

export default defineComponent({
  name: "Datagrid",
  components: { DatagridHeader, DatagridRow, DatagridCell },
  data() {
    return {
      selection: this.items.filter((item) => this.value?.includes(item)),
    };
  },
  props: {
    value: Array,
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
  methods: {
    // select a ListItem
    select(item: object): void {
      switch (this.selectMode) {
        case "single":
          this.selection.splice(0);
          this.selection.push(item);
          break;

        case "multiple":
          this.selection.includes(item)
            ? // if true, remove from selection
              this.selection.splice(this.selection.indexOf(item), 1)
            : // else, add to selection
              this.selection.push(item);
          break;

        default:
          break;
      }
    },
  },
});
</script>
