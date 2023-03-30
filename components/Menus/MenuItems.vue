<template>
  <v-row align="" justify="center" style="justify-content: center">
    <v-tabs
      color="deep-purple accent-4"
      class="text-capitalize"
      style="justify-content: center"
    >
      <v-tab class="text-capitalize">Lunch</v-tab>
      <v-tab class="text-capitalize">Dinner</v-tab>

      <v-tab-item>
        <v-row>
          <v-col :cols="bp.mdAndUp ? '4' : '12'"  v-for="(item, i) in items"
                 :key="i">
            <v-card
              rounded
              :loading="loading"
              class="mx-auto my-12"
              max-width="374"
            >
              <template slot="progress">
                <v-progress-linear
                  color="deep-purple"
                  height="10"
                  indeterminate
                ></v-progress-linear>
              </template>

              <v-img
                height="250"
                :src="item.image"
              ></v-img>

              <v-card-title>{{ item.name }}</v-card-title>

              <v-card-text>
                <v-row
                  align="center"
                  class="mx-0"
                >
                  <v-rating
                    :value="4.5"
                    color="amber"
                    dense
                    half-increments
                    readonly
                    size="14"
                  ></v-rating>

                  <div class="grey--text ms-4">
                    {{ item.rating }}
                  </div>
                </v-row>

                <div class="my-4 text-subtitle-1">
                  {{item.info}}
                </div>

              </v-card-text>

              <v-divider class="mx-4"></v-divider>

              <v-card-actions>
                <v-card-text>
                  <v-chip-group
                    v-model="selection"
                    active-class="deep-purple accent-4 white--text"
                    column
                  >
                    <v-chip small class="deep-purple accent-4 white--text">{{item.availability}}</v-chip>
                    <v-chip small class="info darken-4 white--text">Price : {{item.price}}</v-chip>

                  </v-chip-group>
                </v-card-text>
              </v-card-actions>

            </v-card>
          </v-col>
        </v-row>
      </v-tab-item>
      <v-tab-item>
        <v-row>
          <v-col :cols="bp.mdAndUp ? '4' : '12'"  v-for="(item, i) in dinners"
                 :key="i">
            <v-card
              rounded
              :loading="loading"
              class="mx-auto my-12"
              max-width="374"
            >
              <template slot="progress">
                <v-progress-linear
                  color="deep-purple"
                  height="10"
                  indeterminate
                ></v-progress-linear>
              </template>

              <v-img
                height="250"
                :src="item.image"
              ></v-img>

              <v-card-title>{{ item.name }}</v-card-title>

              <v-card-text>
                <v-row
                  align="center"
                  class="mx-0"
                >
                  <v-rating
                    :value="4.5"
                    color="amber"
                    dense
                    half-increments
                    readonly
                    size="14"
                  ></v-rating>

                  <div class="grey--text ms-4">
                    {{ item.rating }}
                  </div>
                </v-row>

                <div class="my-4 text-subtitle-1">
                  {{item.info}}
                </div>

              </v-card-text>

              <v-divider class="mx-4"></v-divider>

              <v-card-actions>
                <v-card-text>
                  <v-chip-group
                    v-model="selection"
                    active-class="deep-purple accent-4 white--text"
                    column
                  >
                    <v-chip small class="deep-purple accent-4 white--text">{{item.availability}}</v-chip>
                    <v-chip small class="info darken-4 white--text">Price : {{item.price}}</v-chip>

                  </v-chip-group>
                </v-card-text>
              </v-card-actions>

            </v-card>
          </v-col>
        </v-row>
      </v-tab-item>

    </v-tabs>
  </v-row>

</template>


<script>
import special from 'static/special.jpg'
import beef_2 from 'static/beef_2.jpg'
import beef_bri from 'static/beef.jpg'
import beef_hydra from 'static/beef-hydrabadi.jpg'
import chik_bri from 'static/chicken-bri.jpg'
import hydra_bri from 'static/hydrabadi.jpg'
import mutton from 'static/mutton-biryani.jpeg'
import broast from 'static/broast.jpg'
import fried from 'static/fried-rice.jpg'
import prawn from 'static/prawn-polaw.jpg'
import ps from 'static/ps.jpg'
import ss from 'static/ss.jpg'
import veg from 'static/veg_polaw.jpg'
import sp from 'static/special_sunday.jpg'
export default {
  name: "MenuItems",
  data: () => ({
    loading: false,
    selection: 1,
    items: [
      {
        name : 'Sunday Special',
        rating: '4.5 (223)',
        availability: 'Sunday',
        image: special,
        info: 'Special Polaw, Chicken Roa ist, Beef Chilli, Chinese Veg, Jarda, Drinks',
        price: '$10'
      },
      {
        name : 'Chicken Biriyani',
        rating: '4.5 (445)',
        availability: 'Monday',
        image: chik_bri,
        info: 'Chicken Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Mutton Biriyani',
        rating: '4.5 (564)',
        availability: 'Tuesday',
        image: hydra_bri,
        info: 'Mutton Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Beef Biriyani',
        rating: '4.5 (332)',
        availability: 'Wednesday',
        image: beef_2,
        info: 'Beef Biriyani , Kabab , Egg , Salad, Sweet,  Drinks',
        price: '$10'
      },
      {
        name : 'Hydrabadi Chicken Biriyani',
        rating: '4.5 (123)',
        availability: 'Thursday',
        image: beef_bri,
        info: 'Hydrabadi Chicken Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Hydrabadi Mutton Biriyani',
        rating: '4.5 (433)',
        availability: 'Friday',
        image: mutton,
        info: 'Hydrabadi Mutton Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Hydrabadi Beef Biriyani',
        rating: '4.5 (413)',
        availability: 'Saturday',
        image: beef_hydra,
        info: 'Hydrabadi Beef Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
    ],
    dinners: [
      {
        name : 'Sunday Special',
        rating: '4.5 (455)',
        availability: 'Sunday',
        image: sp,
        info: 'Special Polaw, Chicken Roast, Beef Chilli, Chinese Veg, Jarda, Drinks',
        price: '$10'
      },
      {
        name : 'Veg Polaw',
        rating: '4.5 (123)',
        availability: 'Monday',
        image: veg,
        info: 'Veg Polaw, Fish Finger, Mutton Regela, Salad, Firnni, Drinks',
        price: '$10'
      },
      {
        name : 'Fried Kichuri',
        rating: '4.5 (232)',
        availability: 'Tuesday',
        image: ss,
        info: 'Fried Kichuri, Beef Regela, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Veg Polaw with Broast Chicken',
        rating: '4.5 (119)',
        availability: 'Wednesday',
        image: broast,
        info: 'Veg Polaw, Broast Chicken, Mutton Regela, Fish Chili, Salad, Firnni,  Drinks',
        price: '$10'
      },
      {
        name : 'Prawn Polaw with Chicken Masala',
        rating: '4.5 (390)',
        availability: 'Thursday',
        image: ps,
        info: 'Prawn Polaw, Chicken Masala, Egg Curry, Kabab, Salad, Firnni, Drinks',
        price: '$10'
      },
      {
        name : 'Prawn Polaw',
        rating: '4.5 (200)',
        availability: 'Friday',
        image: prawn,
        info: 'Prawn Polaw, Roast Chicken, Prawn Masala, Kabab, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Fried Rice',
        rating: '4.5 (100)',
        availability: 'Saturday',
        image: fried,
        info: 'Fried Rice, Broast Chicken, Salted veg, Prawn Chili, Salad, Sweet, Drinks',
        price: '$10'
      },
    ],
  }),

  methods: {
    reserve () {
      this.loading = true

      setTimeout(() => (this.loading = false), 2000)
    },
  },
}
</script>

<style scoped>

</style>
