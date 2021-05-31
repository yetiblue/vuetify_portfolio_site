<template>
  <div>
    <TopNavbar />
    <v-app>
      <v-row flat justify="end">
        <SideBarComponent :sideHeight="sideHeight">
          <template #userDesktopProfile>
            <v-card-subtitle class="ml-1 text-left">www.melacast.com</v-card-subtitle>
            <v-card-actions class="justify-center">
              <v-icon class="ml-2 ml-lg-n3">mdi-instagram</v-icon>
              <v-icon class="ml-4">mdi-youtube</v-icon>

              <v-icon class="ml-4">mdi-vimeo</v-icon>
              <v-icon class="ml-4">mdi-linkedin</v-icon>
            </v-card-actions>
            <v-divider class="mt-2 mx-4"></v-divider>
            <v-card-subtitle class="justify-start">
              <h3>Project Interests:</h3>
            </v-card-subtitle>
            <!-- <template > -->
            <div v-for="tab in projectInterests" :key="tab">
              <v-card-text class="mt-n6 justify-center">{{tab}}</v-card-text>
            </div>
            <!-- </template> -->
            <v-btn class="mb-2 brown" elevation="0" block>Contact Me</v-btn>
            <v-card-title>Languages</v-card-title>
          </template>

          <template #userMobileProfile>
            <v-card-subtitle class="text-center">www.melacast.com</v-card-subtitle>
            <v-card-actions class="justify-center">
              <v-icon class="ml-2 ml-lg-0">mdi-instagram</v-icon>
              <v-icon class="ml-4">mdi-youtube</v-icon>

              <v-icon class="ml-4">mdi-vimeo</v-icon>
              <v-icon class="ml-4">mdi-linkedin</v-icon>
            </v-card-actions>
            <v-card-title class="justify-center">Project Interests</v-card-title>
            <v-card-text class="text-center">Cool Stuff Cool Stuff Cool Stuff</v-card-text>
            <v-card-actions class="justify-center">
              <v-btn class="mb-2 brown mx-auto" elevation="0">Contact Me</v-btn>
            </v-card-actions>
            <!-- MOVE LANGUAGES TO PROFILE CARD SECTION BELOW -->
            <!-- <v-card-title>Languages</v-card-title> -->
          </template>
        </SideBarComponent>

        <v-col cols="12" lg="10">
          <v-list class="ml-lg-n5 px-5 pr-sm-10 mt-n10 mt-lg-0" two-line>
            <v-subheader>Pirates of the caribbean 10</v-subheader>

            <v-header class="text-sm-h3 text-h6 justify-xs-center">APPLICANTS</v-header>

            <v-row v-if="!isMobile" class="mb-5">
              <v-combobox
                class="mt-6"
                v-model="filterValue"
                :items="items"
                clearable
                label="Apply Filters"
                multiple
                prepend-icon="mdi-filter-variant"
                solo
              >
                <template v-slot:selection="{ item }">
                  <v-chip close @click:close="remove(item)">
                    <strong>{{ item }}</strong>&nbsp;
                    <span>(interest)</span>
                  </v-chip>
                </template>
              </v-combobox>
              <v-btn class="mt-8 white" elevation="0" @click="filter()">Filter</v-btn>
              <!-- slot -->
              <!-- <v-col cols="3">
                <v-btn class="grey" elevation="0" block :to="'google.com'">Accepted</v-btn>
              </v-col>
              <v-col cols="3">
                <v-btn elevation="0" block :to="'google.com'">Accepted</v-btn>
              </v-col>
              <v-col cols="3">
                <v-btn elevation="0" block :to="'google.com'">Accepted</v-btn>
              </v-col>
              <v-col cols="3">
                <v-btn elevation="0" block :to="'google.com'">Accepted</v-btn>
              </v-col>-->
              <!-- slot -->
            </v-row>
            <v-row v-else class="mb-5">
              <v-col cols="12">
                <v-menu offset-y>
                  <template v-slot:activator="{ on, attrs }">
                    <v-btn color="primary" block elevation="0" dark v-bind="attrs" v-on="on">Select</v-btn>
                  </template>
                  <v-list>
                    <!-- pass up different values for mobileTabs when the buttons above change -->
                    <v-list-item
                      v-for="(item, index) in mobileTabs"
                      :key="index"
                      @click="clickElement(item)"
                    >
                      <v-list-item-title>{{ item }}</v-list-item-title>
                    </v-list-item>
                  </v-list>
                </v-menu>
              </v-col>
            </v-row>

            <v-divider></v-divider>
            <v-list-item v-for="applicant in applicants" :key="applicant.name">
              <v-list-item-avatar>
                <v-img :src="applicant.image"></v-img>
              </v-list-item-avatar>
              <!-- extra space for when there's 4 columns -->
              <slot name="profession"></slot>

              <v-list-item-content>
                <v-list-item-text>{{applicant.name}}</v-list-item-text>
              </v-list-item-content>

              <v-list-item-content>
                <v-list-item-text v-text="applicant.date"></v-list-item-text>
              </v-list-item-content>

              <v-list-item-action class="mr-lg-15 mr-0">
                <v-btn :x-small="$vuetify.breakpoint.xs" elevation="0" :to="applicant.link">See More</v-btn>
              </v-list-item-action>
            </v-list-item>
            <v-divider></v-divider>
          </v-list>
          <!-- <v-select v-model="value" :items="items" attach chips label="Chips" multiple>
            <v-chip close></v-chip>
          </v-select>-->
        </v-col>
      </v-row>

      <!-- <BottomFooterComponent /> -->

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
      chips: [],
      sideHeight: `20vh`,
      name: "tom",
      date: "9/20/2021",
      link: "http:idk.com",
      filterValue: [],
      mobileTabs: ["Accepted", "Declined", "Pending", "Archived"],
      projectInterests: ["horror, Thriller, Scary"],
      items: ["actor", "Dancer", "makeup"],
      returnedValues: [],
      actors: [
        {
          id: 1,
          name: "timmy",
          role: "actor"
        },
        {
          id: 2,
          name: "Tom",
          role: "Dancer"
        },
        {
          id: 3,
          name: "Tam",
          role: "router"
        },
        {
          id: 4,
          name: "Tamantha",
          role: "makeup"
        }
      ],
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
  computed: {
    isMobile() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return true;
      }
    }
  },
  methods: {
    clickElement(clickItem) {
      window.alert(clickItem);
    },
    remove(item) {
      console.log("REMOVE");
      this.filterValue.splice(this.filterValue.indexOf(item), 1);
      this.filterValue = [...this.filterValue];
    },
    filter() {
      this.returnedValues = [];
      let testArray = this.filterValue;
      for (let i = 0; i < testArray.length; i++) {
        // console.log(testArray[i]);
        const result = this.actors.filter(item => item.role == testArray[i]);

        this.returnedValues.push(result);
      }
    }
  }
};
</script>