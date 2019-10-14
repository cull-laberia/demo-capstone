<template>
  <v-container fluid>
    <v-row>
      <!-- <v-col cols="1" /> -->
      <v-col class="box" cols="8">
        <!-- <span>{{source}}</span> -->
        <iframe
          class="inside-destop"
          ref="desktopIframe"
          :src="source"
          frameborder="0"
          width="100%"
          height="99%"
        ></iframe>
      </v-col>
      <v-col cols="1"></v-col>
      <v-col cols="3">
        <iframe
          class="inside-mobile"
          ref="mobileIframe"
          :src="source"
          frameborder="0"
          width="375"
          height="610"
        ></iframe>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  props: {
    source: {
      type: String,
      default: ""
    }
  },
  beforeUpdate() {
    console.log("change ne");
    this.renderNewTemplate();
  },
  mounted() {
    console.log("load ne");
    this.renderNewTemplate();
  },
  methods: {
    renderNewTemplate() {
      this.$refs.desktopIframe.src = "about:blank";
      this.$refs.mobileIframe.src = "about:blank";
      setTimeout(() =>  {
				this.$refs.desktopIframe.contentWindow.document.write(this.source);
				this.$refs.mobileIframe.contentWindow.document.write(this.source);
      }, 500);
      
    }
  }
};
</script>
<style scoped>
.box {
  height: 89vh;
  width: auto;
  border: 2px solid;
  border-top-right-radius: 15px;
  border-top-left-radius: 15px;
}

.box .inside-mobile {
  height: 95%;
  border: 2px solid;
  border-radius: 10px;
}

.box .inside-desktop {
  height: 93%;
  overflow-y: scroll;
  border: 2px solid;
  margin-top: 5%;
}
</style>
