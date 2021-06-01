<template>
  <div>
    <TopNavbar />
    <v-app>
      <v-row flat justify="end">
        <SideBarComponent :sideHeight="sideHeight">
          <template #userDesktopSlot>
            <v-card-title>Name</v-card-title>
            <v-card-subtitle>User</v-card-subtitle>
            <v-btn class="mb-2" elevation="0" block>Dashboard</v-btn>
            <v-btn class="mb-2 pr-2" elevation="0" block>Applications</v-btn>
            <v-btn class="pr-2 mb-1" elevation="0" block>Edit Profile</v-btn>
          </template>

          <template #userMobileSlot>
            <v-card-title>Name Name</v-card-title>
            <v-card-subtitle>User</v-card-subtitle>
            <v-row>
              <v-col cols="12" sm="4">
                <v-btn class="grey" elevation="0" block :to="'google.com'">Dashboard</v-btn>
              </v-col>
              <v-col cols="12" sm="4">
                <v-btn elevation="0" block :to="'google.com'">Applications</v-btn>
              </v-col>
              <v-col cols="12" sm="4">
                <v-btn elevation="0" block :to="'google.com'">Edit Profile</v-btn>
              </v-col>
            </v-row>
          </template>
        </SideBarComponent>

        <v-spacer></v-spacer>
      </v-row>
      <v-row class="mt-lg-n16 pb-lg-16 mb-lg-n16" justify="end" align="start">
        <v-col class="pt-11 pb-lg-n16 mt-sm-n16 mt-lg-0" cols="12" sm="12" lg="10">
          <v-col>
            <v-card flat class="text-center text-lg-left ml-lg-n6">
              <v-card-title :class="[forIpad ? 'justify-center' : 'none']">
                <h3 class="mb-n8">Actor</h3>
              </v-card-title>
              <v-card-title :class="[forIpad ? 'justify-center' : 'none']">
                <h1 class="mb-2">Name Last</h1>
              </v-card-title>
              <v-card-subtitle>Ethnicity | Location | Member Since</v-card-subtitle>
              <v-card-text>io: Doggo ipsum shoob long water shoob porgo you are doing me the shock doing me a frighten, long water shoob shoober. Smol borking doggo with a long snoot for pats you are doing me the shock porgo doge adorable doggo, fluffer long water shoob I am bekom fat you are doin me a concern</v-card-text>
            </v-card>
          </v-col>
        </v-col>
      </v-row>
      <threeColGrid :displayGridCount="displayGridCount" :gridWidth="gridWidth">
        <template #cardSlot>
          <v-card :height="gridHeight" outlined title>
            <v-img
              class="white--text align-end"
              :height="gridHeight"
              @click="navigateToPage()"
              src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
            >
              <v-card-title class="mb-n5" align="end">Category Name</v-card-title>
              <v-card-text class="mb-n5">Timmy Zhou</v-card-text>
              <v-card-text class="mb-5">Date information</v-card-text>
              <v-row align="center" justify="end"></v-row>
            </v-img>
          </v-card>
        </template>
      </threeColGrid>
    </v-app>
    <BottomFooterComponent />
  </div>
</template>
<script>
import SideBarComponent from "~/components/SideBarComponent";
import TopNavbar from "~/components/TopNavbar";
import BottomFooterComponent from "~/components/BottomFooterComponent";
import threeColGrid from "~/components/threeColGrid";
export default {
  components: {
    SideBarComponent,
    TopNavbar,
    BottomFooterComponent,
    threeColGrid
  },
  data() {
    return { sideHeight: `10vh`, gridWidth: "10" };
  },
  methods: {
    navigateToPage() {
      console.log("click");
      this.$router.push("/fourcols");
    }
  },
  computed: {
    forIpad() {
      switch (this.$vuetify.breakpoint.name) {
        case "md":
          return true;

        case "sm":
          return true;
        case "xs":
          return true;
      }
    },
    displayGridCount() {
      switch (this.$vuetify.breakpoint.name) {
        case "md":
          return 9;
        case "sm":
          return 6;
        case "xs":
          return 4;
        case "lg":
          return 9;
      }
    },

    gridHeight() {
      switch (this.$vuetify.breakpoint.name) {
        case "md":
          return "240px";
        case "sm":
          return "190px";
        case "xs":
          return "25vh";
        case "lg":
          return "280px";
      }
    }
  }
};
</script>
<style>
</style>
