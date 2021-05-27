<template>
  <div>
    <TopNavbar />
    <v-app>
      <v-row flat justify="end">
        <SideBarComponent :sideHeight="sideHeight" />

        <v-col class="pt-11 mt-sm-n16 mt-lg-0" cols="12" sm="12" lg="9">
          <v-col>
            <v-card flat class="text-center text-lg-left">
              <v-card-title :class="[forIpad ? 'justify-center' : 'none']">PIRATES OF THE CARRIBEAN</v-card-title>
              <v-card-subtitle>Date Posted</v-card-subtitle>
              <v-container>
                <v-card-text class="ml-lg-n4 mt-lg-n6">
                  fdhsiaudsoxjvdfsdfdsfds fdhsiaudsoxjvdfsdfdsfds
                  fdhsiaudsoxjvdfsdfdsfds fdhsiaudsoxjvdfsdfdsfds
                  fdhsiaudsoxjvdfsdfdsfds fdhsiaudsoxjvdfsdfdsfds
                  fdhsiaudsoxjvdfsdfdsfds fdhsiaudsoxjvdfsdfdsfds
                </v-card-text>
              </v-container>
            </v-card>
          </v-col>
        </v-col>
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
                sm="3"
                md="3"
                lg="3"
                xl="2"
                :class="{
                  custom5cols: $vuetify.breakpoint.mdAndUp
                }"
              >
                <v-card :height="gridHeight" outlined title>
                  <v-img
                    class="white--text align-end"
                    :height="gridHeight"
                    src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                  >
                    <v-card-title align="end">Category Name</v-card-title>
                    <v-card-subtitle>Description of gallery</v-card-subtitle>
                    <v-card-text>Date information</v-card-text>
                    <v-row align="center" justify="end"></v-row>
                  </v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="8" sm="10" lg="9" class="pl-8 pl-sm-14 pl-lg-4">Applicants</v-col>
          <v-col class="pr-16 pr-lg-0" cols="4" sm="2" lg="1">
            <v-btn text>View All</v-btn>
          </v-col>
          <v-col class="pb-lg-16" cols="12" lg="10" justify="end">
            <v-row class="mb-lg-n16 pl-4 pl-sm-10 pl-lg-0 pr-4 pr-sm-10 pr-lg-8" justify="start">
              <v-col justify="end" v-for="n in positionsGridCount" :key="n" cols="12" sm="6" lg="4">
                <v-card :height="gridHeight" outlined title>
                  <v-img
                    class="white--text align-end"
                    :height="gridHeight"
                    src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                  >
                    <v-card-title align="end">Category Name</v-card-title>
                    <v-card-subtitle>Description of gallery</v-card-subtitle>
                    <v-card-text>Date information</v-card-text>
                    <v-row align="center" justify="end"></v-row>
                  </v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="8" sm="10" lg="9" class="pl-8 pl-sm-14 pl-lg-4">Applicants</v-col>
          <v-col class="pr-16 pr-lg-0" cols="4" sm="2" lg="1">
            <v-btn text>View All</v-btn>
          </v-col>
          <v-col class="pb-lg-16" cols="12" sm="12" lg="10" justify="end">
            <v-row class="mb-lg-n16 pl-4 pl-sm-10 pl-lg-0 pr-4 pr-sm-10 pr-lg-8" justify="start">
              <v-col
                justify="end"
                v-for="n in (displayGridCount/2)"
                :key="n"
                cols="6"
                sm="3"
                md="3"
                lg="3"
                xl="2"
                :class="{
                  custom5cols: $vuetify.breakpoint.mdAndUp
                }"
              >
                <v-card :height="gridHeight" outlined title>
                  <v-img
                    class="white--text align-end"
                    :height="gridHeight"
                    src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                  >
                    <v-card-title align="end">Category Name</v-card-title>
                    <v-card-subtitle>Description of gallery</v-card-subtitle>
                    <v-card-text>Date information</v-card-text>
                    <v-row align="center" justify="end"></v-row>
                  </v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="8" sm="10" lg="9" class="pl-8 pl-sm-14 pl-lg-4">Applicants</v-col>
          <v-col class="pr-16 pr-lg-0" cols="4" sm="2" lg="1">
            <v-btn text>View All</v-btn>
          </v-col>
          <v-col class="pb-lg-16" cols="12" sm="12" lg="10" justify="end">
            <v-row class="mb-lg-n16 pl-4 pl-sm-10 pr-sm-10 pl-lg-0 pr-4 pr-lg-8" justify="start">
              <v-col
                justify="end"
                v-for="n in (displayGridCount/2)"
                :key="n"
                cols="6"
                sm="3"
                md="3"
                lg="3"
                xl="2"
                :class="{
                  custom5cols: $vuetify.breakpoint.mdAndUp
                }"
              >
                <v-card :height="gridHeight" outlined title>
                  <v-img
                    class="white--text align-end"
                    :height="gridHeight"
                    src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                  >
                    <v-card-title align="end">Category Name</v-card-title>
                    <v-card-subtitle>Description of gallery</v-card-subtitle>
                    <v-card-text>Date information</v-card-text>
                    <v-row align="center" justify="end"></v-row>
                  </v-img>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </div>
    </v-app>
  </div>
</template>
<script>
import SideBarComponent from "~/components/SideBarComponent";
import TopNavbar from "~/components/TopNavbar";
export default {
  components: { SideBarComponent, TopNavbar },
  data() {
    return { sideHeight: `20vh` };
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
          return "20vh";
        case "sm":
          return "15vh";
        case "xs":
          return "25vh";
        case "lg":
          return "25vh";
        case "xl":
          return "25vh";
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
