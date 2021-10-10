<template>
  <div class="students">
    <div id="groups_list">
      <labeler label="School Year:">
        <arrow-select
          :items="[2022, 2023, 2024, 2025, 2026, 2027, 2028]"
          :value="2022"
        />
      </labeler>
      <list-view :items="groups">
        <template v-slot:model="slotProps">
          {{ slotProps.item.grade }}
          {{ slotProps.item.speciality }}
          {{ slotProps.item.section }}
        </template>
      </list-view>
    </div>

    <tiles-view id="student_options">
      <tile title="Payments" icon="money-check">
        Fees control and another transactions.
      </tile>
      <tile title="Degrees" icon="award">
        Subjects Degrees and report cards.
      </tile>
      <tile title="Personal Data" icon="address-card" size="medium">
        Student's Data.
      </tile>
    </tiles-view>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import InputBox from "@/components/InputBox.vue";
import FlatButton from "@/components/FlatButton.vue";
import Toolbar from "@/components/Toolbar.vue";
import ListView from "@/components/ListView.vue";
import StagedView from "@/components/StagedView.vue";
import Stage from "@/components/Stage.vue";
import TilesView from "@/components/TilesView.vue";
import Tile from "@/components/Tile.vue";
import ArrowSelect from "@/components/ArrowSelect.vue";
import Labeler from "@/components/Labeler.vue";

export default defineComponent({
  components: {
    InputBox,
    FlatButton,
    Toolbar,
    ListView,
    StagedView,
    Stage,
    TilesView,
    Tile,
    ArrowSelect,
    Labeler,
  },
  name: "Students",
  data() {
    return {
      students: [
        {
          id: 0,
          firstname: "firstname0",
          lastname: "lastname0",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 1,
          firstname: "firstname1",
          lastname: "lastname1",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 2,
          firstname: "firstname2",
          lastname: "lastname2",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 3,
          firstname: "firstname3",
          lastname: "lastname3",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 4,
          firstname: "firstname4",
          lastname: "lastname4",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 5,
          firstname: "firstname5",
          lastname: "lastname5",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 6,
          firstname: "firstname6",
          lastname: "lastname",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 7,
          firstname: "firstname7",
          lastname: "lastname7",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 8,
          firstname: "firstname8",
          lastname: "lastname8",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 9,
          firstname: "firstname9",
          lastname: "lastname9",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 10,
          firstname: "firstname10",
          lastname: "lastname10",
          birthday: new Date("2004-12-01"),
        },
      ],
      groups: [
        { grade: "1st Grade", speciality: "", section: "A" },
        { grade: "2nd Grade", speciality: "", section: "A" },
        { grade: "11th Grade", speciality: "Accountant", section: "A" },
        { grade: "3rd Grade", speciality: "", section: "A" },
        { grade: "1st Grade", speciality: "", section: "B" },
      ],
    };
  },
});
</script>
