<template>
  <div>
    <h1>NEWS</h1>
    <div
      v-for="entry in news"
      :key="entry._id"
    >
      <h3> {{ entry.title }}</h3>
      <p>{{ entry.content }}</p>
    </div>
  </div>
</template>

<script>
import Axios from "axios";

import config from "~/local_modules/config";

export default {
  data() {
    return {
      newsData: [],
      ip: config.ip
    };
  },
  computed: {
    news: function() {
      return this.newsData;
    }
  },
  mounted: function() {
    //this.loadNews();
  },
  methods: {
    // loadNews: function() {
    //   var that = this;
    //   Axios.get(this.ip + "news").then(response => {
    //     console.log(response.data);
    //     that.newsData = response.data;
    //   });
  }
};
</script>

<style scoped>
h1 {
  border-top: 1px solid gray;
  margin-top: 3vh;
  padding-top: 2vh;
  /* border: 1px solid red; */
  /* border-left:0px; */
  /*
  border-width: 1px;
  border-color: red; */
}
</style>
