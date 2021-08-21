<template>
  <div class="home">
    <h3>Hi Bryan!</h3>

    <tiles-view>
      <tile title="Users" size="large" background="#D5ECC2"/>
      <tile title="Payroll" background="#F6DFEB"/>
      <tile title="Roles" background="#F1ECC3"/>
    </tiles-view>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TilesView from "@/components/TilesView.vue"
import Tile from "@/components/Tile.vue"

export default defineComponent({
  name: "Home",
  components: {TilesView, Tile}
});
</script>
