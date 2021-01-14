<template>
  <div>
    <h1>{{ info }}</h1>
  </div>
</template>
<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";
Vue.use(VueAxios, axios);
export default {
  name: "List",
  data() {
    return {
      info: null
    };
  },
  mounted() {
    Vue.axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then(response => {
        console.warn((this.info = response.data.bpi));
      });
  }
};
</script>
