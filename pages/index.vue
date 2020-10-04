<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center">
        <vuetify-logo />
      </div>
      <v-card>
        <v-card-title class="headline"> Apple Music </v-card-title>
        <v-card-text>
          <p>
            Stream 70 million songs ad‑free. Download your favorite tracks. Play
            them offline. Get exclusive playlists and live radio. Listen across
            all of your devices.
          </p>
          <p>
            Apple Music is better than ever with all‑new features designed to
            make your music come alive.
          </p>
          <p>
            Listen Now is the easiest way to play what you love and discover
            something new.
          </p>
          <p>
            Tune in to three live radio stations hosted by artists playing
            today’s hits, classics, and country.
          </p>
          <p>
            Get the full Apple Music experience online.
            <a
              href="https://music.apple.com/us/browse"
              target="_blank"
              rel="noopener noreferrer"
              title="Apple Music"
            >
              Go to music.apple.com </a
            >.
          </p>
          <div class="text-xs-right">
            <em><small>&mdash; Nuttapong Pakdee 6104101323</small></em>
          </div>
          <hr class="my-3" />
          <a
            href="https://github.com/boss34128/vtf001"
            target="_blank"
            rel="noopener noreferrer"
          >
            GitHub
          </a>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn color="primary" nuxt to="/inspire"> Continue </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    VuetifyLogo,
  },
}
</script>
