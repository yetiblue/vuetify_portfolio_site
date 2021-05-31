<template>
  <v-row>
    <v-col cols="8" sm="10" lg="9" class="pl-8 pl-sm-14 pl-lg-4">
      <slot name="rowTitleOne"></slot>
      <slot name="rowTitleTwo"></slot>
      <slot name="rowTitleThree"></slot>Applicants
    </v-col>
    <v-col class="pr-16 pr-lg-0" cols="4" sm="2" lg="1">
      <slot name="navButtonOne"></slot>
      <slot name="navButtonTwo"></slot>
      <slot name="navButtonThree"></slot>

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
  </v-row>
</template>