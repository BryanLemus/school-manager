<template>
  <div class="students">
    <toolbar>
      <flat-button icon="plus" label="New student" />
      <input-box placeholder="find students" type="search" />
    </toolbar>

    <div id="groups_list">
      <label class="headline6">Academic Log</label>
      <labeler label="School Year:">
        <arrow-select
          value="2022"
          :items="[
            2016,
            2017,
            2018,
            2019,
            2020,
            2021,
            2022,
            2023,
            2024,
            2025,
            2026,
            2027,
            2028,
          ]"
        />
      </labeler>

      <list-view :items="groups">
        <template v-slot:model="slotProps">
          <labeler :label="slotProps.item.grade">
            <label v-if="slotProps.item.speciality">{{
              slotProps.item.speciality + " · "
            }}</label>
            <label> {{ "Section " + slotProps.item.section }}</label>
          </labeler>
        </template>
      </list-view>
    </div>

    <datagrid
      :items="students"
      :headers="[
        { text: 'NIE', value: 'nie' },
        { text: 'First Name', value: 'firstname' },
        { text: 'Last Name', value: 'lastname' },
      ]"
      selectMode="multiple"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import InputBox from "@/components/InputBox.vue";
import FlatButton from "@/components/FlatButton.vue";
import Toolbar from "@/components/Toolbar.vue";
import ListView from "@/components/ListView.vue";
import ArrowSelect from "@/components/ArrowSelect.vue";
import Labeler from "@/components/Labeler.vue";
import Datagrid from "@/components/Datagrid.vue";

export default defineComponent({
  components: {
    InputBox,
    FlatButton,
    Toolbar,
    ListView,
    ArrowSelect,
    Labeler,
    Datagrid,
  },
  name: "Students",
  data() {
    return {
      students: [
        {
          id: 0,
          nie: 5465465886,
          firstname: "firstname0",
          lastname: "lastname0",
          genre: "male",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 1,
          nie: 5465465886,
          firstname: "firstname1",
          lastname: "lastname1",
          genre: "female",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 2,
          nie: 5465465886,
          firstname: "firstname2",
          lastname: "lastname2",
          genre: "female",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 3,
          nie: 5465465886,
          firstname: "firstname3",
          lastname: "lastname3",
          genre: "male",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 4,
          nie: 5465465886,
          firstname: "firstname4",
          lastname: "lastname4",
          genre: "female",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 5,
          nie: 5465465886,
          firstname: "firstname5",
          lastname: "lastname5",
          genre: "female",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 6,
          nie: 5465465886,
          firstname: "firstname6",
          lastname: "lastname",
          genre: "male",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 7,
          nie: 5465465886,
          firstname: "firstname7",
          lastname: "lastname7",
          genre: "female",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 8,
          nie: 5465465886,
          firstname: "firstname8",
          lastname: "lastname8",
          genre: "male",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 9,
          nie: 5465465886,
          firstname: "firstname9",
          lastname: "lastname9",
          genre: "male",
          birthday: new Date("2004-12-01"),
        },
        {
          id: 10,
          nie: 5465465886,
          firstname: "firstname10",
          lastname: "lastname10",
          genre: "female",
          birthday: new Date("2004-12-01"),
        },
      ],
      groups: [
        { grade: "1st Grade", section: "A" },
        { grade: "1st Grade", section: "B" },
        { grade: "2nd Grade", section: "A" },
        { grade: "3rd Grade", section: "A" },
        { grade: "3rd Grade", section: "B" },
        { grade: "4th Grade", section: "A" },
        { grade: "5th Grade", section: "A" },
        { grade: "6th Grade", section: "A" },
        { grade: "7th Grade", section: "A" },
        { grade: "8th Grade", section: "A" },
        { grade: "9th Grade", section: "A" },
        { grade: "10th Grade", speciality: "Accountant", section: "A" },
        { grade: "10th Grade", speciality: "Electric", section: "B" },
        { grade: "10th Grade", speciality: "Nursery", section: "C" },
        { grade: "11th Grade", speciality: "Accountant", section: "A" },
        { grade: "11th Grade", speciality: "Electric", section: "B" },
        { grade: "11th Grade", speciality: "Nursery", section: "C" },
      ],
    };
  },
});
</script>
