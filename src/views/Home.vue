<template>
  <div class="home">
    <label class="headline3">Welcome to dashboard</label>

    <label class="headline6">Acedemic</label>
    <tiles-view>
      <tile
        title="Students"
        icon="user-graduate"
        background="#F1ECC3"
        @click="this.$router.push('/students')"
      >
        Create, delete and manage students.
      </tile>
      <tile title="Teachers" icon="chalkboard-teacher" background="#F6DFEB">
        Hire and manage teachers.
      </tile>
      <tile
        title="Courses and study plans"
        icon="book-reader"
        background="#FCDEC0"
        size="medium"
      >
        Create and edit study plans and subjects content.
      </tile>
      <tile title="Groups" icon="school" background="#CDBBA7" size="medium">
        Create and manage students groups and schedules.
      </tile>
    </tiles-view>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TilesView from "@/components/TilesView.vue";
import Tile from "@/components/Tile.vue";

export default defineComponent({
  name: "Home",
  components: { TilesView, Tile },
});
</script>
