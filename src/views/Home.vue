<template>
  <div class="home">
    <tiles-view>
      <tile title="Users" color="white" />
      <tile title="Permissions" />
      <tile title="Grades" size="medium" color="white" />
      <tile title="Students" size="large" />
      <tile title="Degrees" size="medium" color="white" />
      <tile title="Degrees" size="medium" color="white" />
    </tiles-view>
  </div>
</template>

<script lang="ts">
import Tile from "@/components/Tile.vue";
import TilesView from "@/components/TilesView.vue";
import { defineComponent } from "vue";

export default defineComponent({
  components: { Tile, TilesView },
  name: "Home",
});
</script>
