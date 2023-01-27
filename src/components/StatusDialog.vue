<template>
  <v-dialog v-model="showDialog" max-width="500px">
    <v-card>
      <v-card-title>Título do Dialog</v-card-title>
      <v-card-text>
        Tabela
      </v-card-text>
      <v-divider></v-divider>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="primary" @click.stop="showDialog = false">
          <v-icon>mdi mdi-window-close</v-icon>
        </v-btn>
        <v-btn color="primary" @click.stop="showDialog = false">
          <v-icon>mdi mdi-check</v-icon>
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "StatusDialog",
  props: ["dialog"],
  computed: {
    showDialog: {
      get() {
        return this.dialog;
      },
      set(value) {
        if (!value) {
          this.$emit("close");
        }
      },
    },
  },
};
</script>

<style>
</style>