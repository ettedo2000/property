<template>
  <v-app>
    <v-app-bar
      app
      color="gray"
      dark
    >
      <h1 class="mr-2">BARN PROPERTY <span style="font-size: medium;font-style: italic;">RTE-167 Butler TN</span></h1>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Map</span>
        <v-icon>mdi-map-marker</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <Prperty/>
    </v-main>
    <v-bottom-navigation
        :value="value"
        color="primary"
        horizontal
    >
      <v-btn>
        <span>Email</span>

        <v-icon large>mdi-email</v-icon>
      </v-btn>

      <v-btn>
        <span>Phone</span>

        <v-icon large>mdi-phone</v-icon>
      </v-btn>

      <v-btn>
        <span>Info</span>

        <v-icon large>fas fa-info-circle</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
import Prperty from './components/property';

export default {
  name: 'App',
  components: {
    Prperty,
  },
  data () {
    return {
      dialog: false,
    };
  },
}
</script>
