<template>
  <v-container class="grey lighten-5">
    <v-row no-gutters>
      <v-col
          v-for="item in items"
          :key="item.id"
          cols="15"
          sm="4"
      >
        <v-card
            class="pa-2"
            outlined
            tile
        >
            <span>
              <v-img class="list-complete-img" :src="getImgUrl(item.src)" @click="modalHandler(item.src)"/>
            </span>
        </v-card>
      </v-col>
    </v-row>
    <div>
      <v-dialog
          v-model="dialog"
          width="800"
      >
        <v-card>
          <v-card-title class="text-h5 grey lighten-2">
            Privacy Policy
          </v-card-title>

          <v-card-text>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
          </v-card-text>

          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
                color="primary"
                text
                @click="dialog = false"
            >
              I accept
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
  </v-container>
</template>

<script>

export default {
  name: "Property",
  data:function() {
    return {
      items: [
        { id: "1", src: "barn1.jpg", tags: ["all", "tag1"] },
        { id: "2", src: "barn2.jpg", tags: ["all", "tag2"] },
        { id: "3", src: "barn3.jpg", tags: ["all", "tag3"] },
        { id: "4", src: "barn4.jpg", tags: ["all", "tag4"] },
        { id: "5", src: "barn5.jpg", tags: ["all", "tag5"] },
        { id: "6", src: "barn6.jpg", tags: ["all", "tag6"] },
        { id: "7", src: "barn7.jpg", tags: ["all", "tag7"] },
        { id: "8", src: "barn8.jpg", tags: ["all", "tag8"] },
        { id: "9", src: "barn9.jpg", tags: ["all", "tag9"] },
        { id: "11", src: "barn11.jpg", tags: ["all", "tag11"] },
        { id: "15", src: "barn15.jpg", tags: ["all", "tag15"] },
        { id: "16", src: "barn16.jpg", tags: ["all", "tag16"] },
      ],
      dialog: false,
    };
  },
  methods: {
    getImgUrl: function (imagePath) {

      return require('@/assets/img/' + imagePath);
    },
    modalHandler: function (id) {
      console.log(id);
      this.dialog = true;
      console.log(this.dialog);
    },
  }
};

</script>

<style scoped>
.pa-2 :hover{
  border: 3px solid lightgreen;
}
</style>