<template>
  <div class="home">
    <tiles-view>
      <tile
        title="users"
        :background="require('@/assets/images/test4.jpg')"
        color="white"
      />
      <tile
        title="permissions"
        background="https://cdn.pixabay.com/photo/2018/08/04/06/22/patterns-3583249_960_720.jpg"
        color="white"
      />
      <tile
        title="degrees"
        size="medium"
        :background="require('@/assets/images/test2.jpg')"
        color="white"
      />
      <tile
        title="students"
        size="large"
        :background="require('@/assets/images/test1.jpg')"
      />
      <tile
        title="degrees"
        size="medium"
        :background="require('@/assets/images/test2.jpg')"
        color="white"
      />
      <tile
        title="degrees"
        size="medium"
        :background="require('@/assets/images/test2.jpg')"
        color="white"
      />
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
