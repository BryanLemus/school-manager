<template>
  <div class="home">
    <tiles-group>
      <tile title="users" :background="require('@/assets/images/test4.jpg')" />
      <tile
        title="permissions"
        background="https://cdn.pixabay.com/photo/2018/08/04/06/22/patterns-3583249_960_720.jpg"
      />
      <tile title="settings" :background="require('@/assets/images/test3.jpg')"/>
      <tile title="payments" />
      <tile
        title="degrees"
        size="medium"
        :background="require('@/assets/images/test2.jpg')"
      />
      <tile title="students" size="large" :background="require('@/assets/images/test1.jpg')"/>
    </tiles-group>
  </div>
</template>

<script lang="ts">
import Tile from "@/components/Tile.vue";
import TilesGroup from "@/components/TilesGroup.vue";
import { defineComponent } from "vue";

export default defineComponent({
  components: { Tile, TilesGroup },
  name: "Home",
});
</script>
