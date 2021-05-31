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
            <v-btn class="mb-2" elevation="0" block>Applications</v-btn>
            <v-btn class="pr-2 mb-1" elevation="0" block>Edit Profile</v-btn>
          </template>

          <template #userMobileSlot>
            <v-card-title>Name</v-card-title>
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
      <div>
        <v-row class="pb-lg-16 mb-lg-16" justify="end" align="start">
          <v-col cols="8" sm="10" lg="9" class="pl-8 pl-sm-14 pl-lg-4">Applicants</v-col>
          <v-col class="pr-16 pr-lg-0" cols="4" sm="2" lg="1">
            <v-btn text>View All</v-btn>
          </v-col>
          <v-col class="pb-lg-16" cols="12" sm="12" md="12" lg="10" justify="end">
            <v-row class="mb-lg-n16 pl-4 pr-4 pl-sm-10 pl-lg-0 pr-sm-10 pr-lg-8" justify="start">
              <v-col
                justify="end"
                v-for="n in displayGridCount"
                :key="n"
                cols="6"
                sm="4"
                md="3"
                lg="3"
                xl="2"
                :class="{
                  custom5cols: $vuetify.breakpoint.lgAndUp
                }"
              >
                <!-- slot -->
                <v-card :height="gridHeight" outlined title>
                  <v-img
                    class="white--text align-end"
                    :height="gridHeight"
                    src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                  >
                    <v-card-title class="mb-n5" align="end">Sound Wrangler</v-card-title>
                    <v-card-text class="mb-n5">Timmy Zhou</v-card-text>
                    <v-card-text class="mb-4">Date information</v-card-text>
                    <v-row align="center" justify="end"></v-row>
                  </v-img>
                </v-card>
                <!-- slot -->
              </v-col>
            </v-row>
          </v-col>

          <v-col cols="8" sm="10" lg="9" class="pl-8 pl-sm-14 pl-lg-4">Sent Applicants</v-col>
          <v-col class="pr-16 pr-lg-0" cols="4" sm="2" lg="1">
            <v-btn text>View All</v-btn>
          </v-col>
          <v-col class="pb-lg-16" cols="12" sm="12" md="12" lg="10" justify="end">
            <v-row class="mb-lg-n16 pl-4 pr-4 pl-sm-10 pl-lg-0 pr-sm-10 pr-lg-8" justify="start">
              <v-col
                justify="end"
                v-for="n in displayGridCount"
                :key="n"
                cols="6"
                sm="4"
                md="3"
                lg="3"
              >
                <!-- slot -->
                <v-card :height="gridHeight" outlined title>
                  <v-img
                    class="white--text align-end"
                    :height="gridHeight"
                    src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                  >
                    <v-card-title class="mb-n5" align="end">Category Name</v-card-title>
                    <v-card-text class="mb-n5">Description of gallery</v-card-text>
                    <v-card-text class="mb-4">Date information</v-card-text>
                    <v-row align="center" justify="end"></v-row>
                  </v-img>
                </v-card>
                <!-- slot -->
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </div>
    </v-app>
    <BottomFooterComponent />
  </div>
</template>
<script>
import SideBarComponent from "~/components/SideBarComponent";
import TopNavbar from "~/components/TopNavbar";
import BottomFooterComponent from "~/components/BottomFooterComponent";
import fiveColGrid from "~/components/fiveColGrid";
export default {
  components: {
    SideBarComponent,
    TopNavbar,
    BottomFooterComponent,
    fiveColGrid
  },
  data() {
    return { sideHeight: `20vh`, isUser: true, isDirector: false };
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
          return 10;
        case "sm":
          return 8;
        case "xs":
          return 4;
        case "lg":
          return 10;
        case "xl":
          return 10;
      }
    },
    positionsGridCount() {
      switch (this.$vuetify.breakpoint.name) {
        case "md":
          return 2;
        case "sm":
          return 2;
        case "xs":
          return 1;
        case "lg":
          return 3;
        case "xl":
          return 3;
      }
    },
    gridHeight() {
      switch (this.$vuetify.breakpoint.name) {
        case "md":
          return "200px";
        case "sm":
          return "200px";
        case "xs":
          return "25vh";
        case "lg":
          return "230px";
        case "xl":
          return "280px";
      }
    }
  }
};
</script>
<style>
.custom5cols {
  width: 20%;
  max-width: 20%;
  flex-basis: 20%;
}
</style>
