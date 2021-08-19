<template>
  <div class="home">
    <h3>Hi Bryan!</h3>

    <tiles-view>
      <tile title="Users" size="large"/>
      <tile title="Payroll"/>
      <tile title="Permissions"/>
      <tile title="Users" size="large"/>
      <tile title="Payroll" size="medium"/>
      <tile title="Users" size="large"/>
      <tile title="Payroll"/>
      <tile title="Permissions"/>
      <tile title="Users" size="large"/>
      <tile title="Payroll"/>
      <tile title="Permissions"/>
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
