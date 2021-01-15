<template>
  <div>
    <blockquote class="blockquote text-center">
      <p class="mb-0">
        {{ quote }}
      </p>
      <footer class="blockquote-footer mb-3">
        {{ author }}
      </footer>
      <button v-on:click="loadQuote" class="btn btn-success btn-sm">
        Quote me
      </button>
    </blockquote>
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
      quote: null,
      author: null
    };
  },
  created: function() {
    this.loadQuote;
  },
  methods: {
    loadQuote: function() {
      Vue.axios
        .get("https://goquotes-api.herokuapp.com/api/v1/random?count=1")
        .then(response => {
          this.quote = response.data.quotes[0].text;
          this.author = response.data.quotes[0].author;
        });
    }
  }
};
</script>
<style scoped></style>
