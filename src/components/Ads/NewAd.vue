<template>
  <v-container>
    <v-layout row>
      <v-flex xs12 sm6 offset-sm3>
        <h1 class="text--secondary mb-3">create new ad</h1>
        <v-form v-model="valid" ref="form" validation mb-3>
          <v-text-field
            name="title"
            label="ad title"
            type="text"
            v-model="title"
            required
            :rules="[v => !!v || 'title is required']"
          ></v-text-field>
          <v-textarea
            name="description"
            label="Ad description"
            type="text"
            v-model="description"
            :rules="[v => !!v || 'description is required']"
          ></v-textarea>
        </v-form>
        <v-layout row mb-3>
          <v-flex xs12>
            <v-btn class="warning">
              загрузить
              <v-icon right dark>cloud_upload</v-icon>
            </v-btn>
          </v-flex>
        </v-layout>
        <v-layout row>
          <v-flex xs12>
            <img src="https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg" alt height="100">
          </v-flex>
        </v-layout>
        <v-layout row>
          <v-flex xs12>
            <v-switch label="add to promo" v-model="promo"></v-switch>
          </v-flex>
        </v-layout>
        <v-layout row>
          <v-flex xs12>
            <v-spacer></v-spacer>
            <v-btn :disabled="!valid" class="succes" @click="createAd">Create ad</v-btn>
          </v-flex>
        </v-layout>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      title: '',
      description: '',
      promo: false,
      valid: false
    }
  },
  methods: {
    createAd () {
      if (this.$refs.form.validate()) {
        const ad = {
          title: this.title,
          description: this.description,
          promo: this.promo
        }
        console.log(ad)
      }
    }
  }
}
</script>

<style>
</style>
