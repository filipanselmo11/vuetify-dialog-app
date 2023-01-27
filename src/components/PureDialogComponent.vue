<template>
  <div>
    <h2>Modal Example</h2>
    <v-btn id="myBtn" @click="openModal"> Open Modal </v-btn>
    <div id="myModal" class="modal">
      <div class="modal-content">
        <span class="close">&times;</span>
        <p>Texto do Modal</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PureDialogComponent",
  methods: {
    openModal() {
      const modal = document.getElementById("myModal");
      const btn = document.getElementById("myBtn");
      const span = document.getElementsByClassName("close")[0];
      btn.onclick = function () {
        modal.style.display = "block";
      };
      span.onclick = function () {
        modal.style.display = "none";
      };
      window.onclick = function (event) {
        if (event.target == modal) {
          modal.style.display = "none";
        }
      };
    },
  },
};
</script>

<style></style>
