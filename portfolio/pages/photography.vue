<template>
  <div>
    <TopNavbar />
    <v-app id="bigGrid">
      <div>
        <!-- <v-container -->
        <v-row justify="center" style="class: 10vh"
          ><h1 :justify="$vuetify.breakpoint.mobiles ? 'center' : 'start'">
            PROJECTS
          </h1>
        </v-row>

        <!-- </v-container> -->
        <!-- <v-container> -->
        <v-row style="z-index: 1000" align="center" justify="end">
          <v-col cols="12" sm="12" md="12" lg="2" xl="2">
            <v-card class="pa-8" style="height: 40vh" flat>
              <v-img src="https://cdn.vuetifyjs.com/images/cards/halcyon.png">
              </v-img>
              <v-card-title>
                Name
              </v-card-title>
              <v-card-text>
                I am a very cool kid who likes to fill out their information
                like a good kid i dont know why you would ever have it this
                small but ok whatever i hope that this is ok and that it fits
              </v-card-text>
              <v-card-actions>
                <v-icon>mdi-instagram</v-icon
                ><v-icon class="ml-4">mdi-youtube</v-icon>

                <v-icon class="ml-4">mdi-vimeo</v-icon>
                <v-icon class="ml-4">mdi-linkedin</v-icon></v-card-actions
              >
            </v-card>
          </v-col>
          <v-col
            justify="end"
            v-for="n in 8"
            :key="n"
            cols="12"
            md="5"
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
        <!-- </v-container> -->
      </div></v-app
    >
  </div>
</template>
<script>
import TopNavbar from "~/components/TopNavbar";
export default {
  data() {
    return {};
  },
  components: { TopNavbar }
};
</script>
