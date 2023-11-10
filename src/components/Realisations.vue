<template>
  <div class="col-12">
    <h1 class="titleComponents">Réalisations</h1>
  </div>
  <div class="row">
    <div class="col-md-6 col-sm-12 cardMobile">
      <q-card class="q-ma-sm">
        <q-img src="~assets/essert.png" style="height: 544px">
          <div class="absolute-bottom">
            <div class="text-h6">Mairie d'Essert</div>
            <div class="text-subtitle2">Site vitrine</div>
          </div>
        </q-img>

        <q-card-actions>
          <q-btn flat>Visiter le site</q-btn>
        </q-card-actions>
      </q-card>
    </div>

    <div class="col-md-6 col-sm-12 cardMobile">
      <q-card class="q-ma-sm">
        <q-img src="~assets/loading.png" style="height: 544px">
          <div class="absolute-bottom">
            <div class="text-h6">Mairie de Frahier-et-Chatebier</div>
            <div class="text-subtitle2">Site vitrine</div>
          </div>
        </q-img>

        <q-card-actions>
          <q-btn flat>Visiter le site</q-btn>
        </q-card-actions>
      </q-card>
    </div>

    <div class="col-md-6 col-sm-12 cardMobile">
      <q-card class="q-ma-sm">
        <q-img src="~assets/loading.png" style="height: 544px">
          <div class="absolute-bottom">
            <div class="text-h6">Pole jeunesse Essert</div>
            <div class="text-subtitle2">Maintenance du site internet</div>
          </div>
        </q-img>
      </q-card>
    </div>
  </div>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "RealisationsContainer",
});
</script>
<style>
@media (max-width: 600px) {
  .cardMobile {
    width: 100%;
  }
}
</style>
