<template>
  <div class="students">
    <staged-view>
      <stage>
        <label class="headline3">Students</label>
        <input-box type="search" placeholder="Find students" />
        <list-view :items="students">
          <template v-slot:model="slotProps">
            <div class="studentItem">
              <label>{{ slotProps.item.firstname }}</label>
              <label>{{ slotProps.item.lastname }}</label>
            </div>
          </template>
        </list-view>
        <flat-button icon="plus" text="Add student" />
      </stage>
      <stage>
        <label class="headline3">student name</label>
        <input-box label="First Name:"/>
        <input-box label="Last Name:"/>
      </stage>
    </staged-view>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ListView from "@/components/ListView.vue";
import Stage from "@/components/Stage.vue";
import StagedView from "@/components/StagedView.vue";
import InputBox from "@/components/InputBox.vue";
import FlatButton from "@/components/FlatButton.vue";

export default defineComponent({
  components: { StagedView, Stage, ListView, InputBox, FlatButton },
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
    };
  },
});
</script>