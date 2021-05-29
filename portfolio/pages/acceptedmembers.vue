<template>
  <div>
    <TopNavbar />
    <v-app>
      <v-row flat justify="end">
        <SideBarComponent :sideHeight="sideHeight" />
        <v-col cols="12" lg="10">
          <v-list class="px-10" subheader two-line>
            <v-subheader inset>Applicants</v-subheader>
            <v-row class="mb-5">
              <v-col cols="3">
                <v-btn elevation="0" block :to="'google.com'" v-text="'Accepted'">Accepted</v-btn>
              </v-col>
              <v-col cols="3">
                <v-btn elevation="0" block :to="'google.com'" v-text="'Accepted'">Accepted</v-btn>
              </v-col>
              <v-col cols="3">
                <v-btn elevation="0" block :to="'google.com'">Accepted</v-btn>
              </v-col>
              <v-col cols="3">
                <v-btn elevation="0" block :to="'google.com'">Accepted</v-btn>
              </v-col>
            </v-row>
            <v-divider></v-divider>
            <v-list-item v-for="applicant in applicants" :key="applicant.name">
              <v-list-item-avatar>
                <v-img :src="applicant.image"></v-img>
              </v-list-item-avatar>

              <v-list-item-content>
                <v-list-item-title v-text="applicant.name"></v-list-item-title>
              </v-list-item-content>
              <v-list-item-content>
                <v-list-item-title v-text="applicant.date"></v-list-item-title>
              </v-list-item-content>

              <v-list-item-action class="mr-lg-15 mr-0">
                <v-btn elevation="0" :to="applicant.link">
                  See More
                  <!-- <nuxt-link :to="applicant.link">See More</nuxt-link> -->
                </v-btn>
              </v-list-item-action>
            </v-list-item>
            <v-divider inset></v-divider>
          </v-list>
          <v-select v-model="value" :items="items" attach chips label="Chips" multiple>
            <v-chip close></v-chip>
          </v-select>
        </v-col>
      </v-row>

      <BottomFooterComponent />

      <v-divider class="mx-4"></v-divider>
    </v-app>
  </div>
</template>
<script>
import SideBarComponent from "~/components/SideBarComponent";
import TopNavbar from "~/components/TopNavbar";
import BottomFooterComponent from "~/components/BottomFooterComponent";
export default {
  components: { SideBarComponent, TopNavbar, BottomFooterComponent },
  data() {
    return {
      sideHeight: `20vh`,
      name: "tom",
      date: "9/20/2021",
      link: "http:idk.com",
      value: [],
      items: ["foo", "bar", "fizz", "buzz"],
      applicants: [
        {
          date: "Jan 9, 2014",
          name: "America Has a Booger",
          image: "https://avatars.githubusercontent.com/u/53276606?v=4",
          link: "https://google.com"
        },
        {
          date: "Jan 17, 2014",
          name: "America Has a Booger",
          image: "https://avatars.githubusercontent.com/u/53276606?v=4",
          link: "https://google.com"
        },
        {
          date: "Jan 28, 2014",
          name: "America Has a Booger",
          image: "https://avatars.githubusercontent.com/u/53276606?v=4",
          link: "https://google.com"
        },
        {
          date: "Jan 9, 2014",
          name: "America Has a Booger",
          image: "https://avatars.githubusercontent.com/u/53276606?v=4",
          link: "https://google.com"
        },
        {
          date: "Jan 17, 2014",
          name: "America Has a Booger",
          image: "https://avatars.githubusercontent.com/u/53276606?v=4",
          link: "https://google.com"
        },
        {
          date: "Jan 28, 2014",
          name: "America Has a Booger",
          image: "https://avatars.githubusercontent.com/u/53276606?v=4",
          link: "https://google.com"
        }
      ]
    };
  },
  computed: {}
};
</script>