<template>
  <nav class="Navbar">
    <navbar-link
      v-for="link in links"
      :key="link.route"
      :to="link.route"
      :text="link.text"
      :icon="link.icon"
      :selected="link.selected"
      @click="select(link)"
    />
  </nav>
</template>

<script lang="ts">
interface NavbarLink {
  route: string;
  text: string;
  icon: string;
  selected: boolean;
}
import router from "@/router";
import { defineComponent } from "vue";
import NavbarLink from "./NavbarLink.vue";

export default defineComponent({
  components: { NavbarLink },
  name: "Navbar",
  data() {
    return {
      selected: this.links?.find((x) => x.selected === true) as NavbarLink,
    };
  },

  props: {
    value: Object as () => NavbarLink,
    links: Array as () => NavbarLink[],
  },

  methods: {
    select(link: NavbarLink): void {
      this.selected = link;
      console.log(link.route === this.selected.route);
    },
  },
});
</script>