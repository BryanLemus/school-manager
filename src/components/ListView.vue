<template>
  <ul class="ListView">
    <list-item
      v-for="item in items"
      :key="item[dataKey]"
      :selected="selection.includes(item)"
      @click="select(item)"
    >
      <slot name="data" :item="item" />
    </list-item>
  </ul>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ListItem from "./ListItem.vue";

export default defineComponent({
  name: "ListView",
  components: { ListItem },
  data() {
    return {
      selection: [this.value] as object[],
    };
  },
  props: {
    value: Array as () => object[],
    dataKey: String,
    items: Array,
    selectMode: {
      type: String,
      default: "single",
      validator: (selectionMode: string): boolean =>
        ["single", "multiple"].indexOf(selectionMode) !== -1,
    },
  },
  methods: {
    // select a ListItem
    select(item: object): void {
      // get current selected items
      let selectedItems = this.selection;
      switch (this.selectMode) {
        case "single":
          // clear selected items
          selectedItems.splice(0).push(item);
          // set value
          this.selection = selectedItems;
          break;

        case "multiple":
          // verify if item exists
          selectedItems.includes(item)
            ? // if true, remove it
              selectedItems.splice(selectedItems.indexOf(item), 1)
            : // else, add it
              selectedItems.push(item);
          // set value
          this.selection = selectedItems;
          break;

        default:
          // return an Error
          throw new Error("Invalid selection mode");
          break;
      }
    },
  },
});
</script>