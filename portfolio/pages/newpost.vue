<template>
  <div>
    <TopNavbar />
    <v-app id="bigGrid">
      <div v-if="!mobile">
        <h1 class="text-center text-md-left ml-md-8 mt-md-2">
          New Post
        </h1>
      </div>
      <!-- <v-form> -->
      <v-container>
        <h1 style="padding-bottom: 20px" class="text-center">
          Submit Information Here
        </h1>

        <v-row justify="center">
          <v-col cols="12" sm="8">
            <v-text-field
              outlined
              justify="center"
              label="Regular"
            ></v-text-field>
          </v-col>
          <v-col cols="12" sm="8">
            <v-textarea label="Bio" outlined v-model="form.bio" color="teal">
              <template v-slot:label>
                <div>Bio <small>(optional)</small></div>
              </template>
            </v-textarea>
          </v-col>

          <v-row v-if="!mobile" justify="center" class="mb-6">
            <v-col cols="12" sm="4">
              <v-btn
                class="ml-md-18 ml-16"
                width="200px"
                height="60px"
                color="brown"
                depressed
              >
                <v-icon left>
                  mdi-upload
                </v-icon>
                Thumbnail
              </v-btn>
              <input
                ref="uploader"
                class="d-none"
                type="file"
                accept="image/*"
              />
            </v-col>
            <v-col cols="12" sm="4">
              <v-btn
                class="ml-6"
                width="200px"
                height="60px"
                color="brown"
                depressed
              >
                <v-icon left>
                  mdi-upload
                </v-icon>
                Gallery
              </v-btn>
              <input
                ref="uploader"
                class="d-none"
                type="file"
                accept="image/*"
              />
            </v-col>
          </v-row>
          <v-row v-if="mobile" justify="center" class="mb-6">
            <v-col cols="12" sm="4">
              <v-btn
                justify="center"
                class="ml-16"
                width="200px"
                height="60px"
                color="brown"
                depressed
              >
                <v-icon left>
                  mdi-upload
                </v-icon>
                Thumbnail
              </v-btn>
              <input
                ref="uploader"
                class="d-none"
                type="file"
                accept="image/*"
              />
            </v-col>
            <v-col cols="8" sm="4">
              <v-btn
                justify="center"
                width="200px"
                height="60px"
                color="brown"
                depressed
              >
                <v-icon left>
                  mdi-upload
                </v-icon>
                Gallery
              </v-btn>
              <input
                ref="uploader"
                class="d-none"
                type="file"
                accept="image/*"
              />
            </v-col>
          </v-row>
          <v-col cols="12" sm="8">
            <v-menu
              v-model="startDateMenuOpen"
              :nudge-right="40"
              transition="scale-transition"
              offset-y
              max-width="290px"
              min-width="290px"
            >
              <template v-slot:activator="{ on }">
                <v-text-field
                  outlined
                  label="Start Date"
                  readonly
                  :value="form.start_date"
                  v-on="on"
                ></v-text-field>
              </template>
              <v-date-picker
                v-model="form.start_date"
                no-title
                @input="startDateMenuOpen = false"
                :min="minDate"
              ></v-date-picker>
            </v-menu>
          </v-col>
          <v-col cols="12" sm="8">
            <v-menu
              v-model="endDateMenuOpen"
              :nudge-right="40"
              transition="scale-transition"
              offset-y
              max-width="290px"
              min-width="290px"
            >
              <template v-slot:activator="{ on }">
                <v-text-field
                  outlined
                  label="End Date"
                  readonly
                  :value="form.end_date"
                  v-on="on"
                ></v-text-field>
              </template>
              <v-date-picker
                v-model="form.end_date"
                no-title
                @input="endDateMenuOpen = false"
                :min="minDate"
              ></v-date-picker>
            </v-menu>
          </v-col>
          <v-col outlined style="height=10vh" cols="6" sm="6"
            ><v-checkbox
              v-model="form.tags"
              label="Travel"
              color="green"
              value="Travel"
            ></v-checkbox>
            <v-checkbox
              v-model="form.tags"
              label="Paid"
              color="green"
              value="Paid"
            ></v-checkbox>
            <v-checkbox
              v-model="form.tags"
              label="Paid"
              color="green"
              value="Paid"
            ></v-checkbox>
          </v-col>
          <v-col outlined style="height=10vh" cols="4" sm="2"
            ><v-checkbox
              v-model="form.tags"
              label="Travel"
              color="green"
              value="Travel"
            ></v-checkbox>
            <v-checkbox
              v-model="form.tags"
              label="Paid"
              color="green"
              value="Paid"
            ></v-checkbox>
            <v-checkbox
              v-model="form.tags"
              label="Paid"
              color="green"
              value="Paid"
            ></v-checkbox>
          </v-col>
        </v-row>

        <v-row justify="center">
          <v-col cols="6">
            <v-btn class="brown" style="margin-top: 50px"> Back</v-btn>
          </v-col>
          <v-col cols="4" sm="2">
            <v-btn style="margin-top: 50px;"> Next </v-btn>
          </v-col>
        </v-row>
      </v-container>

      <!-- </v-form> -->
    </v-app>
  </div>
</template>
<script>
import TopNavbar from "~/components/TopNavbar";
export default {
  data() {
    return {
      picker: new Date().toISOString().substr(0, 10),
      date: null,
      startDateMenuOpen: false,
      endDateMenuOpen: false,
      minDate: "2019-07-04",
      maxDate: "2019-08-30",
      form: {
        bio: "",
        date: "",
        start_date: null,
        end_date: null,
        tags: null
      }
      //   extraSmallMobile: true
    };
  },
  components: { TopNavbar },
  computed: {
    mobile() {
      switch (this.$vuetify.breakpoint.name) {
        case "md":
          return true;
        case "sm":
          return true;
        case "xs":
          return true;
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
