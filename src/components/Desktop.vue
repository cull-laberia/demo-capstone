<template>
  <v-row>
    <v-col cols="12">
     <HelloWorld />
      <HelloWorld />
      <HelloWorld />
    </v-col>
  </v-row>
</template>

<script>
import HelloWorld from './HelloWorld'
export default {
  components: {
    HelloWorld,
  }
};
</script>

<style scoped>
.box {
  height: 400px ;
  border: 2px solid;
}
</style>