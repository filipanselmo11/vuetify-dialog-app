<template>
  <v-dialog v-model="dialog" width="500" height="300">
    <template v-slot:activator="{ on, attrs }">
      <v-btn v-on="on" v-bind="attrs">Open</v-btn>
    </template>
    <v-card>
      <v-toolbar dense color="elevation-0">
        <v-spacer></v-spacer>
        <v-btn icon color="black" @click="dialog = false">
          <v-icon>mdi-close</v-icon>
        </v-btn>
      </v-toolbar>
      <v-row no-gutters>
        <v-img
            :src="picture.Pic"
            :height="picture.PicHeight"
            :width="picture.PicWidth"
            contain></v-img>
      </v-row>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "DialogComponent",
  data: () => ({
    dialog: false,
  }),
};
</script>

<style>
</style>