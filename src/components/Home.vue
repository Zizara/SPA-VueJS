<template>
  <div>
    <v-container fluid>
      <v-layout row>
        <v-flex xs12>
          <v-carousel>
            <v-carousel-item v-for="(item,i) in ads" :key="i" :src="item.imageSrc">
              <div class="carItem">
                <v-btn class="error" :to="'/ad/' + item.id">{{item.title}}</v-btn>
              </div>
            </v-carousel-item>
          </v-carousel>
        </v-flex>
      </v-layout>
    </v-container>

    <v-container grid-list-lg>
      <v-layout row wrap>
        <v-flex xs12 sm6 md4 v-for="ad of ads" :key="ad.id">
          <v-card>
            <v-img :src="ad.imageSrc" aspect-ratio="2.75"></v-img>

            <v-card-title primary-title>
              <div>
                <h3 class="headline mb-0">{{ad.title}}i</h3>
                <div>{{ ad.description }}</div>
              </div>
            </v-card-title>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn flat :to="'/ad/'+ ad.id">Open</v-btn>
              <v-btn flat raised class="primari">Buy</v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  data () {
    return {
      ads: [
        {
          title: 'firstAd',
          description: 'hello',
          promo: false,
          imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
          id: 123
        },
        {
          title: 'secondAd',
          description: 'hello',
          promo: true,
          imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
          id: 1023
        },
        {
          title: 'firstAd',
          description: 'hello',
          promo: true,
          imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
          id: 1233
        },
        {
          title: 'firstAd',
          description: 'hello',
          promo: true,
          imageSrc: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
          id: 1235
        }
      ]
    }
  }
}
</script>

<style scope>
.carItem {
  position: absolute;
  bottom: 50px;
  left: 50%;
  background: rgba(0, 0, 0, 0.5);
  transform: translate(-50%, 0);
  border-radius: 5px;
  padding: 5px 15px;
}
</style>
