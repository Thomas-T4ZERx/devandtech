<template>
  <div class="row">
    <div class="col-2"></div>
    <div class="col-8">
      <h1 style="color: #e47b29">Réalisations</h1>
    </div>
    <div class="col-2"></div>
  </div>
  <q-card class="my-card">
    <q-img src="https://cdn.quasar.dev/img/parallax2.jpg" style="height: 500px">
      <div class="absolute-bottom">
        <div class="text-h6">Mairie d'Essert</div>
        <div class="text-subtitle2">Site vitrine</div>
      </div>
    </q-img>

    <q-card-actions>
      <q-btn flat>Visiter le site</q-btn>
    </q-card-actions>
  </q-card>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "RealisationsContainer",
});
</script>
