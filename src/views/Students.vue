<template>
  <div class="students">
    <staged-view>
      <stage id="students_list">
        <label class="headline3">Students</label>
        <input type="text" />
      </stage>
      <stage>
        <label class="headline1">stage1</label>
      </stage>
    </staged-view>
  </div>
</template>

<script lang="ts">
import Stage from "@/components/Stage.vue";
import StagedView from "@/components/StagedView.vue";
import { defineComponent } from "vue";

export default defineComponent({
  components: { StagedView, Stage },
  name: "Students",
});
</script>