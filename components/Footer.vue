<template>
  <v-container fluid class="px-0" style="padding: 0">
    <v-card flat class="pa-0">
      <v-card-text class="secondary">
        <v-container grid-list-lg class="px-0 pt-0">
          <v-layout row wrap justify-center align-start>
            <v-flex align-self-start xs12 sm12 md3 lg3 class="white--text mt-6">
              <!--            <Services />-->
            </v-flex>

            <v-flex align-self-start xs12 sm12 md3 lg3 class="white--text mt-6">
              <h2>COMPANY</h2>
              <v-divider class="my-3" color="orange"></v-divider>
              <nuxt-link to="about-us" class="text-decoration-none white--text">
                <h3 class="mb-3 font-weight-light">About Us</h3>
              </nuxt-link>
              <nuxt-link to="portfolio" class="text-decoration-none white--text">
                <h3 class="mb-3 font-weight-light">Products</h3>
              </nuxt-link>
            </v-flex>

            <v-flex align-self-start xs12 sm12 md3 lg3 class="white--text mt-6">
              <!--            <Address />-->
            </v-flex>
            <v-flex
              align-self-center
              xs12
              sm12
              md3
              lg3
              class="text-center order-lg-first order-last pt-0"
            >
              <v-img class="mx-4 mb-0" :src="logo" contain alt="Soft Array" :aspect-ratio="16/9"></v-img>

              <v-btn
                v-for="icon in icons"
                :key="icon.icon"
                class="mx-4 white--text"
                target="__blank"
                icon
                :href="`//${icon.link}`"
              >
                <v-hover v-slot:default="{ hover }">
                  <v-icon :color="`${hover ? '#FF6600' : 'white'}`" class size="24px">{{ icon.icon }}</v-icon>
                </v-hover>
              </v-btn>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card-text>

      <v-card-text class="primary darken-1 white--text text-center subtitle py-1">
        <v-icon small center color="white">mdi-alpha-c-circle-outline</v-icon>
        {{ new Date().getFullYear() }} —
        <strong class>thegreatspoon.xyz</strong>
      </v-card-text>
    </v-card>
  </v-container>

</template>

<script>
import logo from "@/static/logo.png";
export default {
  components: {

  },
  data: () => ({
    logo,
    icons: [
      {
        icon: "mdi-facebook",
        link: "",
      },
      {
        icon: "mdi-twitter",
        link: "",
      },
      {
        icon: "mdi-linkedin",
        link: "",
      },
      {
        icon: "mdi-instagram",
        link: "",
      },
    ],
  }),
};
</script>
<style scoped>
</style>
