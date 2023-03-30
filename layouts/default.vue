<template>
  <v-app dark>
    <v-app-bar
      fixed
      app
      flat
    >
      <v-container>
        <v-row>
          <v-col cols="6" md="6" sm="3" lg="6" style="text-align: start; justify-content: center; align-self: center">
            <v-btn text class="text-capitalize px-0" @click="$router.push('/')"  :ripple="false" depressed>
              The Great Spoon
            </v-btn>
          </v-col>
          <!--        <v-col cols="12" v-if="bp.mdAndUp" md="2" sm="6" lg="2" class="" style="text-align: end; justify-content: center; align-self: center">-->
          <!--         <v-card-actions class=" text-center" style="">-->
          <!--              <v-img :src="logo" :class="bp.mdAndUp ? 'justify-center mb-4' : 'justify-center mb-3'" class="" :aspect-ratio="bp.mdAndUp ? 7 : 3" contain position="relative"-->
          <!--                     align="center"></v-img>-->
          <!--            </v-card-actions>-->

          <!--        </v-col>-->
          <v-col v-show="bp.mdAndUp" cols="12" md="6" sm="2" lg="6" style="text-align: end; justify-content: center; align-self: center">
            <v-btn text  :ripple="false" class="text-capitalize" @click="$router.push('/')">
              Menu
            </v-btn>
            <v-btn text  :ripple="false" class="text-capitalize" @click="$router.push('/about-us')">
              About
            </v-btn>
            <v-btn text   :ripple="false" class="text-capitalize" @click="$router.push('/privacy-policy')">
              Privacy Policy
            </v-btn>
            <v-btn text :ripple="false" class="text-capitalize" @click="$router.push('/terms-and-condition')">
              Terms & Conditions
            </v-btn>

          </v-col>
          <v-col cols="6" md="6" v-show="bp.smAndDown" sm="5" lg="6" style="text-align: right; justify-content: center; align-self: center">
            <v-icon   @click.stop="drawer = !drawer" v-if="bp.smAndDown">mdi-sort-variant</v-icon>
          </v-col>

        </v-row>
      </v-container>
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

      class="px-0 transparent"
      style="padding: 0"
    >
      <Footer />
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

<style scoped>
.center-img{
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 3px solid #dbe4ed;
}
</style>
