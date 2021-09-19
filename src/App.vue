<template>
  <v-app>
    <v-app-bar
      app
      color="gray"
      dark
    >
      <h1 class="mr-2">BARN PROPERTY <span style="font-size: medium;font-style: italic;">Hwy 67 W Butler TN</span></h1>

      <v-spacer></v-spacer>

      <v-btn
        href="https://goo.gl/maps/6dkr8Up7CEi6HGHcA"
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
    <v-dialog
        v-model="dialog"
        width="300"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-bottom-navigation
            :value="value"
            color="primary"
            horizontal
        >
          <v-btn
              v-on="on"
              v-bind="attrs"
              value="info"
          >
            <span>Contact Information</span>

            <v-icon large>fas fa-info-circle</v-icon>
          </v-btn>
      </v-bottom-navigation>
      </template>
        <v-card>
          <v-card-title class="text-h5 grey lighten-2">
            Contact Information
          </v-card-title>

          <v-card-text>
            <v-list-item three-line>
              <v-list-item-content>
                <v-list-item-title>You can reach me by</v-list-item-title>
                <v-list-item-subtitle>
                  Email: odettesimons@live.com
                </v-list-item-subtitle>
                <v-list-item-subtitle>
                  Phone: 423-291-0549
                </v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-card-text>

          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
                color="primary"
                text
                @click="dialog = false"
            >
              Thank You
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
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
