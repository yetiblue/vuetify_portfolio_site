<template>
  <div>
    <TopNavbar />
    <v-app id="bigGrid">
      <div>
        <!-- <v-container> -->
        <h1 class="text-center text-md-left ml-md-8 mt-md-2">
          PROJECTS
        </h1>
        <!-- </v-container> -->

        <v-row style="z-index: 1000" align="center" justify="end">
          <SideBarComponent :sideHeight="sideHeight" />
          <v-col
            justify="end"
            v-for="n in 8"
            :key="n"
            cols="12"
            md="6"
            lg="5"
            xl="5"
          >
            <v-card style="height:40vh" class="pa-4" outlined title>
              <v-img
                class="white--text align-end"
                height="35vh"
                src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
              >
                <v-card-title align="end"> Category Name</v-card-title>
                <v-card-subtitle> Description of gallery</v-card-subtitle
                ><v-card-text> Date information</v-card-text>
                <v-row align="center" justify="end">
                  <v-card-actions>
                    <v-btn class="mr-3 mb-3" style="margin-bottom: 10px">
                      Press me
                    </v-btn>
                  </v-card-actions>
                </v-row>
              </v-img>
            </v-card>
          </v-col>
        </v-row>
      </div></v-app
    >
  </div>
</template>
<script>
import TopNavbar from "~/components/TopNavbar";
import SideBarComponent from "~/components/SideBarComponent";
export default {
  data() {
    return {
      sideHeight: `40vh`
    };
  },
  components: { TopNavbar, SideBarComponent },
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
<style>
.sticky-top {
  width: 15vw;
  position: fixed;
  /* position: sticky; */
  top: 0;
}
</style>
