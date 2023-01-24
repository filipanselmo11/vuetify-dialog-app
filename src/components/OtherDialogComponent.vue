<template>
  <div>
    <v-dialog v-model="dialog1" width="500">
      <template v-slot:activator="{ attrs, on }">
        <v-btn v-on="on" v-bind="attrs"> Dialog 1 </v-btn>
      </template>
      <v-card>
        <v-img :src="urlImage1"></v-img>
      </v-card>
    </v-dialog>
    <v-spacer/>
    <v-dialog v-model="dialog2" width="500">
      <template v-slot:activator="{ attrs, on }">
        <v-btn v-on="on" v-bind="attrs"> Dialog2 </v-btn>
      </template>
      <v-card>
        <v-img :src="urlImage2"></v-img>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: "OtherDialogComponent",
  data: () => ({
    styleElement: null,
    dialog1: false,
    dialog2: false,
    urlImage1: require('../assets/images/kaisa.jpg'),
    urlImage2: require('../assets/images/hokages.jpg'),
  }),
  computed: {
    style() {
      if (this.dialog2) {
        return `
            .v-overlay.v-overlay--active {
                opacity: 0.1;
            }
        `;
      }
      return "";
    },
  },
  watch: {
    style(style) {
      if (this.styleElement) {
        this.styleElement.parentNode.removeChild(this.styleElement);
      }
      this.styleElement = this.applyStyle(style);
    },
  },
  methods: {
    applyStyle(styleDef) {
      let styleElement = document.createElement("style");
      styleElement.type = "text/css";
      document.head.appendChild(styleElement);
      styleElement.innerHTML = styleDef;
      return styleElement;
    },
  },
};
</script>

<style></style>
