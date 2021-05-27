<template>
  <v-col cols="12" sm="12" md="12" lg="2" xl="2">
    <div v-if="mobile">
      <v-container justify="center">
        <v-card class="pa-8" flat>
          <div v-if="extraSmallMobile">
            <v-img
              justify="center"
              height="300px"
              width="300px"
              src="https://cdn.vuetifyjs.com/images/cards/halcyon.png"
            ></v-img>
          </div>
          <div v-else>
            <v-img
              class="mx-auto"
              justify="center"
              height="300px"
              width="300px"
              src="https://cdn.vuetifyjs.com/images/cards/halcyon.png"
            ></v-img>
          </div>

          <v-card-title>Name</v-card-title>
          <v-card-text>
            I am a very cool kid who likes to fill out their information like a
            good kid i dont know why you would ever have it this small but ok
            whatever i hope that this is ok and that it fits
          </v-card-text>
          <v-card-actions>
            <v-icon class="ml-9 ml-sm-2 ml-lg-0">mdi-instagram</v-icon>
            <v-icon class="ml-4">mdi-youtube</v-icon>

            <v-icon class="ml-4">mdi-vimeo</v-icon>
            <v-icon class="ml-4">mdi-linkedin</v-icon>
          </v-card-actions>
        </v-card>
      </v-container>
    </div>

    <div v-else>
      <div :style="{ height: sideHeight }">
        <!-- <div v-if="!mobile" > -->
        <v-card class="pa-8" flat>
          <v-img src="https://cdn.vuetifyjs.com/images/cards/halcyon.png"></v-img>
          <v-card-title>Name</v-card-title>
          <v-card-text>
            I am a very cool kid who likes to fill out their information like a
            good kid i dont know why you would ever have it this small but ok
            whatever i hope that this is ok and that it fits
          </v-card-text>
          <v-card-actions>
            <v-icon class="ml-2 ml-lg-0">mdi-instagram</v-icon>
            <v-icon class="ml-4">mdi-youtube</v-icon>

            <v-icon class="ml-4">mdi-vimeo</v-icon>
            <v-icon class="ml-4">mdi-linkedin</v-icon>
          </v-card-actions>
        </v-card>
      </div>
    </div>
    <!-- </div> -->
  </v-col>
</template>
<script>
export default {
  props: ["sideHeight"],
  computed: {
    height() {
      switch (this.$vuetify.breakpoint.name) {
        case "md":
          return 500;
      }
    },
    mobile() {
      switch (this.$vuetify.breakpoint.name) {
        case "md":
          return true;

        case "sm":
          return true;
        case "xs":
          return true;
      }
    },
    extraSmallMobile() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return true;
          console.log("is small");
      }
    }
  }
};
</script>
