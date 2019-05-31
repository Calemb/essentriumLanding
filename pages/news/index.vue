<template>
  <div>
    NEWS
    <p
      v-for="entry in news"
      :key="entry._id"
    >
      {{ entry.title }}
      <br>
      {{ entry.content }}
    </p>
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
    }
  },
  computed: {
    news: function(){
      return this.newsData
    }
  },
  mounted: function() {
    this.loadNews();
  },
  methods: {
    loadNews: function() {
      var thi = this
      Axios.get(this.ip + "news").then(response => {
        console.log(response.data);
        
        thi.newsData = response.data;
      });
    }
  }
};
</script>

<style>
</style>
