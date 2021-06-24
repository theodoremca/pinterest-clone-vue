<template>
  <div id="app"
     >
    <stack
            :column-min-width="200"
            :gutter-width="15"
            :gutter-height="20"
            monitor-images-loaded

    >
      <stack-item
              v-for="(image, i) in images"
              :key="i"
      >
        <Card :details="image.user.portfolio_url" :description="image.description == null ? image.alt_description : image.description " :link="image.links.html" :img="image.urls.small"/>
      </stack-item>
    </stack>

  </div>
</template>

<script>
import Card from './components/Card.vue'
import axios from "axios";
import { Stack, StackItem } from "vue-stack-grid";

export default {
  name: 'App',
  components: {
    Card,
    Stack,    StackItem
  },
  data: () => ({
    images: []
  }),
  mounted() {
    this.searchUnsplash('car');
  },
  methods: {
    searchUnsplash(topic) {
      this.images = [];
      axios
              .get(
                      `https://api.unsplash.com/search/photos?query=${topic}&per_page=20`,
                      {
                        headers: {
                          Authorization:
                                  "Client-ID bzSaThVGDPDGEUUhSkp194vZzb4gnOnLhdx--pez2J4>",
                          "Accept-Version": "v1"
                        }
                      }
              )
              .then(response => {
                this.images = response.data.results;
              })
              .catch(() => {
                this.images = [];
              });
    }
  }


}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
