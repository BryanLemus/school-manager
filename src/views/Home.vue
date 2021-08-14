<template>
  <div class="home">
    <tiles-view>
      <tile
        title="Users"
        color="mint"
        background="https://image.freepik.com/free-photo/stack-random-rectangles-hovering-space-flat-surface_23-2148319016.jpg"
      />
      <tile title="Permissions"/>
      <tile title="Grades" size="medium" color="orange" />
      <tile title="Students" size="large" />
      <tile title="Degrees" size="medium" color="red" />
      <tile title="Degrees" size="medium" color="yellow" />
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
