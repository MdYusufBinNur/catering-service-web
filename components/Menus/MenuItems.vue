<template>
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
              <v-chip small class="green darken-2 white--text">Price : {{item.price}}</v-chip>

            </v-chip-group>
          </v-card-text>
        </v-card-actions>

      </v-card>
    </v-col>

  </v-row>

</template>

<script>
export default {
  name: "MenuItems",
  data: () => ({
    loading: false,
    selection: 1,
    items: [
      {
        name : 'Sunday Special',
        rating: '4.5 (413)',
        availability: 'Sunday',
        image: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        info: 'Special Polaw, Chicken Roa ist, Beef Chilli, Chinese Veg, Jarda, Drinks',
        price: '$10'
      },
      {
        name : 'Chicken Biriyani',
        rating: '4.5 (413)',
        availability: 'Monday',
        image: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        info: 'Chicken Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Mutton Biriyani',
        rating: '4.5 (413)',
        availability: 'Tuesday',
        image: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        info: 'Mutton Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Beef Biriyani',
        rating: '4.5 (413)',
        availability: 'Wednesday',
        image: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        info: 'Beef Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Hydrabadi Chicken Biriyani',
        rating: '4.5 (413)',
        availability: 'Thursday',
        image: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        info: 'Hydrabadi Chicken Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Hydrabadi Mutton Biriyani',
        rating: '4.5 (413)',
        availability: 'Friday',
        image: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        info: 'Hydrabadi Mutton Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
      {
        name : 'Hydrabadi Beef Biriyani',
        rating: '4.5 (413)',
        availability: 'Saturday',
        image: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        info: 'Hydrabadi Beef Biriyani, Kabab, Egg, Salad, Sweet, Drinks',
        price: '$10'
      },
    ]
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
