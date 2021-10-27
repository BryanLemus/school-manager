<template>
  <td class="DatagridCell" @dblclick="edit()">
    <!--Show State-->
    <div v-if="!editState" class="DatagridCell-showState">
      <slot :value="value" />
      <label v-if="!this.$slots.cellEdit">{{ value }}</label>
    </div>

    <!--Edit State-->
    <div v-if="editState" class="DatagridCell-editState">
      <slot name="cellEdit" :value="value" />
      <input
        class="DatagridCell-input"
        :type="typeof value"
        :value="value"
        v-if="!this.$slots.cellEdit"
        @blur="editState = false"
      />
    </div>
  </td>
</template>

<script lang="ts">
import { defineComponent, nextTick } from "vue";

export default defineComponent({
  name: "DatagridCell",
  data() {
    return {
      editState: false,
    };
  },
  props: {
    value: [String, Number, Object],
    editable: Boolean,
  },
  methods: {
    edit() {
      this.editState = true;
      this.$nextTick(() => {
        this.$el.querySelector(".DatagridCell-input").focus();
      });
    },
  },
});
</script>
