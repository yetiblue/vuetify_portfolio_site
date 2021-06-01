<template>
  <v-row class="pb-lg-16 mb-lg-n16" justify="end" align="start">
    <v-col cols="8" sm="10" lg="9" class="pl-8 pl-sm-14 pl-lg-10">
      <slot name="rowTitleOne"></slot>
      <slot name="rowTitleTwo"></slot>
      <slot name="rowTitleThree"></slot>
    </v-col>
    <v-col class="mb-n16 mr-lg-7 pr-16 pr-lg-0" cols="4" sm="2" lg="1">
      <slot name="navButtonOne"></slot>
      <slot name="navButtonTwo"></slot>
      <slot name="navButtonThree"></slot>
    </v-col>
    <v-col class="pb-16" cols="12" sm="12" md="12" lg="10" justify="end">
      <v-row class="mb-lg-n16 pl-4 pr-4 pl-sm-10 pl-lg-0 pr-sm-10 pr-lg-8" justify="start">
        <v-col
          justify="end"
          v-for="n in displayGridCount"
          :key="n"
          cols="6"
          sm="4"
          md="3"
          lg="3"
          xl="2"
          :class="{
                  custom5cols: $vuetify.breakpoint.lgAndUp
                }"
        >
          <slot name="cardSlot"></slot>
          <slot name="cardSlotTwo"></slot>
          <slot name="cardSlotThree"></slot>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>
<script>
export default {
  props: ["displayGridCount"],
  computed: {}
};
</script>
<style>
.custom5cols {
  width: 20%;
  max-width: 20%;
  flex-basis: 20%;
}
</style>
