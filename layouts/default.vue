<template>
  <v-app dark>
    <v-app-bar
      fixed
      app
      flat
    >
      <v-row>
        <v-col cols="12" md="4" sm="6" lg="4" >
          <v-card-title v-show="bp.mdAndUp" class="pa-3">
            <v-btn text class="text-capitalize"  :ripple="false" depressed>
              The Great Spoon
            </v-btn>
          </v-card-title>
        </v-col>
        <v-col cols="12" md="4" sm="6" lg="4" >
          <v-img :src="logo" :class="bp.mdAndUp ? 'justify-center mb-4' : 'justify-center mb-3'" :aspect-ratio="bp.mdAndUp ? 7 : 3" contain position="relative"
                 align="center"></v-img>
        </v-col>
        <v-col cols="12" md="4" sm="6" lg="4" >
          <v-btn text v-show="bp.mdAndUp" :ripple="false" class="text-capitalize">
            Menu
          </v-btn>
          <v-btn text v-show="bp.mdAndUp"  :ripple="false" class="text-capitalize">
            Privacy Policy
          </v-btn>
          <v-btn text v-show="bp.mdAndUp"  :ripple="false" class="text-capitalize">
            Terms & Conditions
          </v-btn>
          <v-spacer v-if="bp.mdAndUp"/>
          <v-icon @click.stop="drawer = !drawer" v-if="bp.smAndDown">mdi-sort-variant</v-icon>
        </v-col>
      </v-row>

    </v-app-bar>
    <v-navigation-drawer
      v-if="bp.smAndDown"
      v-model="drawer"
      light
      app
      right
    >
      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          :to="item.to"
        >
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
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
          title: 'Privacy Policy',
          to: '/privacy-policy'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Terms & Condition',
          to: '/terms-and-condition'
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
