<template>
  <v-container>
    <v-layout>
      <v-flex class="text-center mb-1">
        <img src="/iTunes.png" width="500px" />
        <v-container class="center"
          ><input type="text" class="datee" v-model="keyword" />
          <button class="button" @click="searchData()">
            Search
          </button></v-container
        >
      </v-flex>
    </v-layout>
    <v-row>
      <v-col
        v-for="list in music"
        :key="list.trackId"
        class="d-flex child-flex"
        cols="4"
      >
        <nuxt-link :to="{ name: 'panglynn-id', params: { id: list } }">
          <v-hover v-slot:default="{ hover }">
            <v-card flat tile class="d-flex" :elevation="hover ? 12 : 2">
              <v-img
                :src="list.artworkUrl100"
                aspect-ratio="1"
                class="grey lighten-2 rounded"
              >
                <p class="font-weight-bold grey" style="color: white">
                  {{ list.trackName }}
                </p>
              </v-img>
            </v-card>
          </v-hover>
        </nuxt-link>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      music: null,
      keyword: '',
    }
  },

  methods: {
    searchData() {
      console.log(this.keyword)
      axios
        .get(
          'https://itunes.apple.com/search?term=' + this.keyword + '&limit=3'
        )

        .then((response) => {
          this.music = response.data.results
        })
        .catch((err) => {
          console.log(err)
        })
    },
  },
}
</script>

<style>
.button {
  background-color: rgb(151, 228, 252);
  border: none;
  color: rgb(17, 0, 255);
  padding: 5px 5px 5px 5px;
  text-align: center;
  display: inline-block;
  margin: 10px 5px;
  font-size: 2rem;
  cursor: pointer;
  border-radius: 12px;
  border: 0.5px solid rgb(151, 228, 252);
  width: 10rem;
}
button:hover {
  color: rgb(222, 140, 255);
  border: 0.5px solid rgba(0, 0, 0, 0.664);
  background-color: rgba(0, 0, 0, 0.664);
}
.button-a {
  background-color: rgb(125, 177, 255);
  border: none;
  padding: 5px 5px 5px 5px;
  text-align: center;
  display: inline-block;
  margin: 10px 10px;
  font-size: 2vw;
  cursor: pointer;
  border-radius: 15px;
  border: 0.5px solid rgb(42, 5, 250);
  width: 15rem;
}
button-a:hover {
  color: rgb(207, 124, 255);
  border: 0.5px solid rgba(255, 255, 255, 0.664);
  background-color: rgba(3, 3, 3, 0.664);
}
.bo {
  color: white;
  font-size: 50px;
}
.datee {
  border-radius: 8px;
  padding: 12px;
  border: 2px solid #000000;
  font-size: 20px;
  width: 30rem;
  background-color: white;
}
.h {
  font-size: 1.25rem;
}
</style>
