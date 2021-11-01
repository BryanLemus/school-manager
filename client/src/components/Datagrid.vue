<template>
  <div class="Datagrid" :class="{ 'Datagrid-select': mode === 'select' }">
    <table>
      <thead>
        <datagrid-row>
          <th class="DatagridHeader">
            <input type="checkbox" />
          </th>
          <datagrid-header
            v-for="header in headers"
            :key="header.value"
            :text="header.text"
          />
        </datagrid-row>
      </thead>
      <tbody>
        <datagrid-row
          v-for="item in paginate"
          :key="item.id"
          :selected="this.selection.includes(item)"
          @click="select(item)"
        >
          <datagrid-cell>
            <input :checked="this.selection.includes(item)" type="checkbox" />
          </datagrid-cell>
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
      currentPage: this.page,
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
    mode: {
      type: String,
      default: "none",
      validator: (mode: string) => ["select", "edit", "none"].includes(mode),
    },
    selectMode: {
      type: String,
      default: "none",
      validator: (selectMode: string) =>
        ["single", "multiple"].includes(selectMode),
    },
    sortBy: { type: Array as () => string[], default: ["id"] },
    groupBy: String,
    itemsPerPage: { type: Number, default: 0, required: false },
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
      }
    },
  },
  computed: {
    paginate(): unknown[] | undefined {
      let itemsPerPage = this.itemsPerPage;
      let startItem = this.currentPage * itemsPerPage - itemsPerPage;
      return (itemsPerPage = 0) && (startItem = 0)
        ? this.items.slice(startItem, startItem + itemsPerPage)
        : this.items;
    },
  },
});
</script>
