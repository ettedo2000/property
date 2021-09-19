
<template>
  <v-container class="grey lighten-5">
    <template>
      <v-card-text>
        <v-list-item three-line>
          <v-list-item-content>
            <v-list-item-title>Butler Barn</v-list-item-title>
            <v-list-item-subtitle>
              Property lays on 1.88 Acres of flat, undeveloped land. There is an old wooden barn on the property.
            </v-list-item-subtitle>
            <v-list-item-subtitle>
              Comes with city water hookup, septic and Electric.<br/>
              It is about 1.8 miles from Watauga Lake and downtown Butler, 14.4 miles from Mountain City, and 50 miles from Boone, NC.
            </v-list-item-subtitle>
            <v-list-item-subtitle>
              Right on Hwy 67 W, the main road between Mountain City and Johnson City.
            </v-list-item-subtitle>
            <v-list-item-subtitle>
              This property is excellent for camping, family home, farming, or commercial opportunity.
            </v-list-item-subtitle>
            <v-list-item-subtitle>
              <span style="font-weight: bold">Property sold as-is. Asking Price starting at $65'000.00</span>
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-card-text>
    </template>
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
            Larger Image
          </v-card-title>
          <v-img class="list-complete-img" :src="getImgUrl(this.dialogURLImage)" />
          <v-card-text>

          </v-card-text>

          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
                color="primary"
                text
                @click="dialog = false"
            >
              Close
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
      dialogURLImage: 'barn1.jpg'
    };
  },
  methods: {
    getImgUrl: function (imagePath) {

      return require('@/assets/img/' + imagePath);
    },
    modalHandler: function (id) {
      //console.log(id);
      this.dialogURLImage = id;
      this.dialog = true;
    },
  }
};

</script>

<style scoped>
.pa-2 :hover{
  border: 3px solid lightgreen;
}
</style>