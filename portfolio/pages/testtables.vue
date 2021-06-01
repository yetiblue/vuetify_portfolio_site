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
      <v-row class="mt-lg-n16 pb-lg-16 mb-lg-n16" justify="end" align="start">
        <v-col class="pt-11 pb-lg-n16 mt-sm-n16 mt-lg-0" cols="12" sm="12" lg="10">
          <v-col>
            <v-card flat class="text-center text-lg-left ml-lg-n6">
              <v-card-title :class="[forIpad ? 'justify-center' : 'none']">PIRATES OF THE CARRIBEAN</v-card-title>
              <v-card-subtitle>Date Posted</v-card-subtitle>

              <v-card-text class="pr-lg-10 text-center">
                fdhsiaudsoxjvdfsdfdsfds fdhsiaudsoxjvdfsdfdsfds
                fdhsiaudsoxjvdfsdfdsfds fdhsiaudsoxjvdfsdfdsfds
                fdhsiaudsoxjvdfsdfdsfds fdhsiaudsoxjvdfsdfdsfds
                fdhsiaudsoxjvdfsdfdsfds fdhsiaudsoxjvdfsdfdsfds
              </v-card-text>
            </v-card>
          </v-col>
        </v-col>
      </v-row>
      <fiveColGrid :displayGridCount="displayGridCount">
        <template #rowTitleOne>Testing Slot</template>
        <template #navButtonOne>
          <v-btn text>See All</v-btn>
        </template>
        <template #cardSlot>
          <v-card :height="gridHeight" outlined title>
            <v-img
              class="white--text align-end"
              :height="gridHeight"
              src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
            >
              <v-card-title class="mb-n5" align="end">Category Name</v-card-title>
              <v-card-text class="mb-n5">Timmy Zhou</v-card-text>
              <v-card-text class="mb-5">Date information</v-card-text>
              <v-row align="center" justify="end"></v-row>
            </v-img>
          </v-card>
        </template>
      </fiveColGrid>
      <fiveColGrid :displayGridCount="displayGridCount">
        <template #rowTitleTwo>Second Slot</template>
        <template #navButtonTwo>
          <v-btn text>See All</v-btn>
        </template>
        <template #cardSlotTwo>
          <v-card :height="gridHeight" outlined title>
            <v-img
              class="white--text align-end"
              :height="gridHeight"
              src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
            >
              <v-card-title class="mb-n5" align="end">Category Name</v-card-title>
              <v-card-text class="mb-n5">Timmy Zhou</v-card-text>
              <v-card-text class="mb-5">Date information</v-card-text>
              <v-row align="center" justify="end"></v-row>
            </v-img>
          </v-card>
        </template>
      </fiveColGrid>
      <fiveColGrid :displayGridCount="displayGridCount">
        <template #rowTitleThree>Third Slot</template>
        <template #navButtonThree>
          <v-btn text>See All</v-btn>
        </template>
        <template #cardSlotThree>
          <v-card :height="gridHeight" outlined title>
            <v-img
              class="white--text align-end"
              :height="gridHeight"
              src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
            >
              <v-card-title class="mb-n5" align="end">Category Name</v-card-title>
              <v-card-text class="mb-n5">Timmy Zhou</v-card-text>
              <v-card-text class="mb-5">Date information</v-card-text>
              <v-row align="center" justify="end"></v-row>
            </v-img>
          </v-card>
        </template>
      </fiveColGrid>
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
    return { sideHeight: `10vh`, isUser: true, isDirector: false };
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
