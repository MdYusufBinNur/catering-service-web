<template>
  <v-row justify="center" align="center">
    <v-carousel hide-delimiters hide-delimiter-background>
      <v-carousel-item
        v-for="(item,i) in items"
        :key="i"
        :src="item.src"
        reverse-transition="fade-transition"
        transition="fade-transition"
        hide-delimiters
      ></v-carousel-item>
    </v-carousel>
    <v-container  class="mt-5">
      <v-layout justify-center align-center row wrap>
        <v-flex xs12 class="my-5 text-center">
          <span class="text-lg-h4 text-sm-h3 font-weight-bold"
          >Our Menus</span
          >
        </v-flex>
      </v-layout>
      <v-layout justify-center align-center row wrap>
        <v-flex xs12 class="mb-10">
          <MenuItems />
        </v-flex>
      </v-layout>
    </v-container>

  </v-row>
</template>

<script>

import food1 from "static/food1.jpg";
import food2 from "static/food2.jpg";
import food3 from "static/food3.jpg";
import food4 from "static/food4.jpg";
import MenuItems from "~/components/Menus/MenuItems.vue";
export default {
  name: 'IndexPage',
  components: {MenuItems},

  data() {
    return {
      items: [
        {
          src: food1,
        },
        {
          src: food2,
        },
        {
          src: food3,
        },
        {
          src: food4,
        },
      ],
    }
  },
  computed: {

  },
  watch: {
  },
  methods: {

  }
}
</script>
<style scoped>
.large_title {
  font-size: 30px;
  font-family: 'Roboto', sans-serif;
  font-weight: bold;
  color: #000000;
  text-align: center;
}

.small_text {
  font-size: 15px;
  font-family: 'Roboto', sans-serif;
  font-weight: bold;
  color: #000000;
  text-align: center;
}
</style>
