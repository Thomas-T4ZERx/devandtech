<template>
  <div class="col-12">
    <h1 class="titleComponents">Nos offres de services</h1>
  </div>
  <div class="row">
    <div class="col-md-3 col-sm-12">
      <q-card flat bordered class="q-ma-sm">
        <img src="~assets/dev.gif" />

        <q-card-section>
          <div class="text-h6" style="text-align: center">Développement</div>
          <div class="text-subtitle2" style="text-align: center">
            Développement de votre site internet sur mesure
            <br />
            <br />
          </div>
        </q-card-section>
      </q-card>
    </div>

    <div class="col-md-3 col-sm-12">
      <q-card flat bordered class="q-ma-sm">
        <img src="~assets/referencement.gif" />

        <q-card-section>
          <div class="text-h6" style="text-align: center">Référencement</div>
          <div class="text-subtitle2" style="text-align: center">
            Référencement naturel de votre site internet pour atteindre la
            première page
          </div>
        </q-card-section>
      </q-card>
    </div>

    <div class="col-md-3 col-sm-12">
      <q-card flat bordered class="q-ma-sm">
        <img src="~assets/admin.gif" />

        <q-card-section>
          <div class="text-h6" style="text-align: center">Administration</div>
          <div class="text-subtitle2" style="text-align: center">
            Gestion personnalisée de votre site internet <br />
            <br />
          </div>
        </q-card-section>
      </q-card>
    </div>
    <div class="col-md-3 col-sm-12" style="text-align: center">
      <q-card flat bordered class="q-ma-sm">
        <img src="~assets/web.gif" />

        <q-card-section>
          <div class="text-h6">Les solutions</div>
          <div class="text-subtitle2" style="text-align: center">
            E-commerce, site dynamique <br />
            <br />
          </div>
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "ServicesContainer",
});
</script>
