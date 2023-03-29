<template>
  <v-app dark>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      flat
    >
      <v-list-item @click="$router.push('/')" :ripple="false" style="max-width: 280px" class="py-0">
<!--        <v-img :src="logo" class="justify-center mb-4" :aspect-ratio="bp.mdAndUp ? 3 : 4" contain position="relative"-->
<!--               align="center"></v-img>-->
      </v-list-item>
      <v-spacer />
      <v-spacer />
      <v-btn text :ripple="false" class="text-capitalize">
        Menu
      </v-btn>
      <v-btn text :ripple="false" class="text-capitalize">
        Privacy Policy
      </v-btn>
      <v-btn text :ripple="false" class="text-capitalize">
        Terms & Conditions
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>

import logo from "static/logo.png";
export default {

  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      logo,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>
