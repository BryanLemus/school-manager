<template>
  <div class="home">
    <tiles-group>
      <tile title="users"/>
      <tile title="permissions"/>
      <tile title="settings"/>
      <tile title="payments"/>
      <tile title="students" size="large"/>
    </tiles-group>
  </div>
</template>

<script lang="ts">
import Tile from '@/components/Tile.vue';
import TilesGroup from '@/components/TilesGroup.vue';
import { defineComponent } from 'vue';

export default defineComponent({
  components: { Tile, TilesGroup },
  name: 'Home',
});
</script>
