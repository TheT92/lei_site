<template>
  <div class="home page-container">
    <div class="banner overflow-hidden">
      <img :src="getBg('banner.png')" />
    </div>
    <div class="clear-float mt-5">
      <div
        v-for="(item, index) in MY_PROJECTS"
        :key="index"
        :class="item.classes"
      >
        <div class="content-card-body">
          <img v-if="item.img" class="logo mr-4" :src="getBg(item.img)" />
          <div>
            <h2 v-if="item.name" class="fs-2">{{ item.name }}</h2>
            <p v-if="item.desc" class="fs-1">{{ item.desc }}</p>
            <img class="card-plate" v-if="item.plate" :src="getBg(item.plate)" />
          </div>
        </div>
      </div>
    </div>
    <footer class="text-secondary text-center mt-8">Copyright © 2024 Designed by Lei Ke</footer>
  </div>
</template>
  
  <script>
import { INTRODUCTION, MY_PROJECTS } from "@/constant";
export default {
  name: "HomePage",
  components: {},
  data() {
    return {
      INTRODUCTION,
      MY_PROJECTS,
    };
  },
  computed: {
    getBg() {
      return function (url) {
        return require(`@/assets/${url}`);
      };
    }
  },
  methods: {},
};
</script>
  
  <style>
@import "../style/home.scss";
</style>
  