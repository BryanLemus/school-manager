<template>
  <div class="home">
    <label class="headline3">Hi Bryan!</label>

    <label class="headline6">Manage</label>
    <tiles-view>
      <tile title="Users" icon="users" background="#EEF9BF">
        Manage, create, delete app users.
      </tile>
      <tile title="School" icon="school" background="#CDF0EA">
        Amenities, classrooms and another resources.
      </tile>
      <tile title="Finances" icon="coins" background="#F9D89C">
        Incomes, expenses, and student's payments.
      </tile>
    </tiles-view>

    <label class="headline6">Acedemic</label>
    <tiles-view>
      <tile title="Students" background="#F1ECC3" />
      <tile title="Teachers" background="#F6DFEB" size="medium" />
      <tile title="Classes" background="#FCDEC0" />
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
