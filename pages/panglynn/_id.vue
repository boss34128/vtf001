<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <v-container class="center"
          ><v-card class="mx-auto center" max-width="344" outlined>
            <v-list-item three-line>
              <v-list-item-content>
                <v-list-item-title class="headline mb-1">
                  {{ music }}
                </v-list-item-title>
                <v-list-item-subtitle>{{ music }}</v-list-item-subtitle>
              </v-list-item-content>

              <v-img :src="lup" max-width="100"></v-img>
            </v-list-item> </v-card
        ></v-container>
      </v-col>
      <v-col cols="12">
        <v-container class="mx-auto center"
          ><audio controls>
            <source :src="sound" type="audio/mpeg" /></audio
        ></v-container>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      lup: this.$route.params.id.artworkUrl30,
      music: this.$route.params.id.artistName,
      sound: this.$route.params.id.previewUrl,
    }
  },
}
</script>
