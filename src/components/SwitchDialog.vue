<template>
  <div>
    <v-switch v-model="status" @click.stop="showDialog = true" style="margin-left: 900px; margin-top: 126px;">
      <template v-slot:label>
        <span v-if="status"> Ativo </span>
        <span v-else> Inativo </span>
      </template>
    </v-switch>
    <status-dialog
    :dialog="showDialog"
    @close="showDialog=false"></status-dialog>
  </div>
</template>

<script>
import StatusDialog from './StatusDialog.vue';
export default {
    components: {
        StatusDialog
    },
    data:() => ({
      status: false,
      showDialog: false,
    }),
};
</script>

<style
        StatusDialog></style>
