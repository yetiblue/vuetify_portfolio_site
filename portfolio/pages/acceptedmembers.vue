<template>
  <div>
    <TopNavbar />
    <v-app>
      <v-row flat justify="end">
        <SideBarComponent :sideHeight="sideHeight">
          <template #userDesktopProfile>
            <v-card-subtitle>www.melacast.com</v-card-subtitle>
            <v-card-actions>
              <v-icon class="ml-2 ml-lg-0">mdi-instagram</v-icon>
              <v-icon class="ml-4">mdi-youtube</v-icon>

              <v-icon class="ml-4">mdi-vimeo</v-icon>
              <v-icon class="ml-4">mdi-linkedin</v-icon>
            </v-card-actions>
            <v-card-title>Project Interests</v-card-title>
            <v-card-text>Cool Stuff</v-card-text>
            <v-card-text>Cool Stuff</v-card-text>
            <v-card-text>Cool Stuff</v-card-text>
            <v-btn class="mb-2 brown" elevation="0" block>Contact Me</v-btn>
            <v-card-title>Languages</v-card-title>
          </template>
          <template #userMobileProfile>
            <v-card-subtitle>www.melacast.com</v-card-subtitle>
            <v-card-actions>
              <v-icon class="ml-2 ml-lg-0">mdi-instagram</v-icon>
              <v-icon class="ml-4">mdi-youtube</v-icon>

              <v-icon class="ml-4">mdi-vimeo</v-icon>
              <v-icon class="ml-4">mdi-linkedin</v-icon>
            </v-card-actions>
            <v-card-title>Project Interests</v-card-title>
            <v-card-text>Cool Stuff</v-card-text>
            <v-card-text>Cool Stuff</v-card-text>
            <v-card-text>Cool Stuff</v-card-text>
            <v-btn class="mb-2 brown" elevation="0" block>Contact Me</v-btn>
            <v-card-title>Languages</v-card-title>
          </template>
        </SideBarComponent>

        <v-col cols="12" lg="10">
          <v-list class="ml-lg-n5 px-5 pr-sm-10" two-line>
            <v-subheader>Pirates of the caribbean 10</v-subheader>
            <v-header class="text-sm-h3 text-h6 justify-xs-center">APPLICANTS</v-header>

            <v-row v-if="!isMobile" class="mb-5">
              <v-combobox
                class="mt-6"
                v-model="chips"
                :items="items"
                clearable
                label="Your favorite hobbies"
                multiple
                prepend-icon="mdi-filter-variant"
                solo
              >
                <template v-slot:selection="{  item }">
                  <v-chip close @click:close="remove(item)">
                    <strong>{{ item }}</strong>&nbsp;
                    <span>(interest)</span>
                  </v-chip>
                </template>
              </v-combobox>
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
      items: ["Streaming", "Eating"],
      sideHeight: `20vh`,
      name: "tom",
      date: "9/20/2021",
      link: "http:idk.com",
      value: [],
      mobileTabs: ["Accepted", "Declined", "Pending", "Archived"],
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
      this.chips.splice(this.chips.indexOf(item), 1);
      this.chips = [...this.chips];
    }
  }
};
</script>