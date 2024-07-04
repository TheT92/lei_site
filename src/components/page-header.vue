<template>
  <div class="page-header full-width d-flex justify-content-between align-items-center pl-4 pr-4">
    Lei
    <ul class="d-flex links list-style-none">
      <li
        v-for="(item, index) in HEADER_LINKS"
        :key="index"
        class="d-inline-flex"
      >
        <router-link
          :to="item.link"
          class="d-inline-flex align-items-center text-decoration-none text-white pl-8 pr-0 fs-3"
          >{{ item.name }}<img v-if="item.icon" :src="getIcon(item.icon)" /></router-link
        >
      </li>
    </ul>
  </div>
</template>
  
<script>
import { HEADER_LINKS } from "@/constant";
export default {
  name: "PageHeader",
  data() {
    return {
      HEADER_LINKS,
    };
  },
  computed: {
    getIcon() {
      return function (url) {
        return require(`@/assets/${url}`);
      };
    }
  },
};
</script>
  