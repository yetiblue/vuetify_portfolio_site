<template>
  <div>
    <TopNavbar />
    <v-app id="bigGrid">
      <h1 class="text-center text-md-left ml-md-8 mt-md-2">
        New Post
      </h1>
      <v-form>
        <v-container>
          <h1 class="text-center">Submit Information Here</h1>

          <v-row justify="center">
            <v-col cols="12" md="8">
              <v-text-field
                outlined
                justify="center"
                label="Regular"
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="8">
              <v-textarea outlined v-model="form.bio" color="teal">
                <template v-slot:label>
                  <div>Bio <small>(optional)</small></div>
                </template>
              </v-textarea>
            </v-col>
            <v-col cols="12" md="8">
              <v-btn
                color="primary"
                depressed
                :loading="isSelecting"
                @click="onButtonClick"
              >
                <v-icon left>
                  cloud_upload
                </v-icon>
              </v-btn>
              <input
                ref="uploader"
                class="d-none"
                type="file"
                accept="image/*"
                @change="onFileChanged"
              />
            </v-col>
            <v-col cols="12" md="8">
              <!-- <v-menu> -->
              <!-- <v-text-field slot="activator" readonly></v-text-field> -->
              <v-date-picker v-model="date" no-title scrollable actions>
                <template scope="{ save, cancel }">
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn flat color="primary" @click="cancel">Cancel</v-btn>
                    <v-btn flat color="primary" @click="save">OK</v-btn>
                  </v-card-actions>
                </template>
              </v-date-picker>
              <!-- </v-menu> -->
            </v-col>
          </v-row>
        </v-container>
      </v-form>
    </v-app>
  </div>
</template>
<script>
import TopNavbar from "~/components/TopNavbar";
export default {
  data() {
    return {
      form: {
        bio: "",
        date: ""
      }
      //   extraSmallMobile: true
    };
  },
  components: { TopNavbar }
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
