<template>
  <v-app>
    <v-content>
      <v-container fluid>
        <v-row>
          <!-- <v-col cols="1" /> -->
          <v-col class="box" cols="7">
            <v-col class="inside-desktop" cols="12">
              <Desktop />
            </v-col>
          </v-col>
          <v-col cols="1"></v-col>
          <v-col class="box" cols="3">
            <v-col class="inside-mobile" cols="12">
              <Mobile/>
            </v-col>
          </v-col>
          <v-col cols="1"></v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import Desktop from "./components/Desktop";
import Mobile from "./components/Mobile";

export default {
  name: "App",
  components: {
    Desktop,
    Mobile
  },
  data: () => ({
    //
  })
};
</script>

<style scoped>
.box {
  height: 95vh;
  border: 2px solid;
  border-top-right-radius: 15px;
  border-top-left-radius: 15px;
  /* // &.inside-mobile {
  //   &.inside-mobile-2 {
  //     width: 30%;

  //     @for $i from 1 to 12 {
  //       .col-sm-#{$i} {
  //         width: 100%;
  //       }
  //     }
  //   }
  // } */
}

.box .inside-mobile {
  height: 95%;
  overflow-y: scroll;
  border: 2px solid;
  overflow: auto;
  border-radius: 10px;
}

.box .inside-desktop {
  height: 93%;
  overflow-y: scroll;
  border: 2px solid;
  margin-top: 7%;
}
</style>
