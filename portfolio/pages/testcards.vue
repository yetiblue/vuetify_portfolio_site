<template>
  <div id="app">
    <v-app>
      <v-tabs style="height:10vh">
        <v-tab>Item One</v-tab>
        <v-tab>Item Two</v-tab>
        <v-tab>Item Three</v-tab>
        <v-tab>Item Four</v-tab>
      </v-tabs>
      <v-container fluid pa-0>
        <v-row align="center" justify="center" style="height:40vh">
          <v-col
            cols="12"
            lg="12"
            md="12"
            class="bg grey lighten-2 d-flex flex-column justify-center align-center"
          >
            <h1
              :class="[$vuetify.breakpoint.mdAndUp ? 'display-4' : 'display-2']"
            >
              Title
            </h1>
            <h1
              :class="[$vuetify.breakpoint.mdAndUp ? 'display-3' : 'display-1']"
            >
              Subtitle
            </h1>
          </v-col>
        </v-row>
        <v-row align="center" style="height:60vh;">
          <v-col cols="12" lg="6" md="6">
            <v-card class="bg2" style="height:50vh">
              <h1
                :class="[
                  $vuetify.breakpoint.mdAndUp ? 'display-4' : 'display-2'
                ]"
              >
                Title
              </h1>
              <h1
                :class="[
                  $vuetify.breakpoint.mdAndUp ? 'display-3' : 'display-1'
                ]"
              >
                Subtitle
              </h1>
            </v-card>
          </v-col>
          <v-col cols="12" lg="6" md="6">
            <v-card class="bg3 white--text" style="height:50vh">
              <h1
                :class="[
                  $vuetify.breakpoint.mdAndUp ? 'display-4' : 'display-2'
                ]"
              >
                Title
              </h1>
              <h1
                :class="[
                  $vuetify.breakpoint.mdAndUp ? 'display-3' : 'display-1'
                ]"
              >
                Subtitle
              </h1>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-app>
  </div>
</template>
<style>
.bg {
  width: 100%;
  height: 100%;
  position: relative;

  background: url("https://images.unsplash.com/photo-1621415780222-5a62b90a7b50?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80")
    no-repeat center center;
  background-size: cover;
}
.bg2 {
  width: 100%;
  height: 100%;
  position: relative;

  background: url("https://images.unsplash.com/photo-1619652118542-6bb9611bf9e2?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=934&q=80")
    no-repeat center center;
  background-size: cover;
}
.bg3 {
  width: 100%;
  height: 100%;
  position: relative;

  background: url("https://images.unsplash.com/photo-1621417809801-2fba61eaa511?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=934&q=80")
    no-repeat center center;
  background-size: cover;
}
</style>
