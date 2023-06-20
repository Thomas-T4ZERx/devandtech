<template>
  <div class="row">
    <div class="col-2"></div>
    <div class="col-8">
      <h1 style="color: #e47b29">Nos offres de services</h1>
    </div>
    <div class="col-2"></div>
  </div>
  <div class="row">
    <div class="col-5">
      <q-card flat bordered class="q-ma-sm">
        <img src="~assets/developpement.jpg" />

        <q-card-section>
          <div class="text-h6">Développement</div>
          <div class="text-subtitle2">
            Développement de votre site internet sur mesure
          </div>
        </q-card-section>
      </q-card>
    </div>
    <div class="col-1"></div>
    <div class="col-5">
      <q-card flat bordered class="q-ma-sm">
        <img src="~assets/referencement.jpg" />

        <q-card-section>
          <div class="text-h6">Référencement</div>
          <div class="text-subtitle2">
            Référencement naturel de votre site internet pour atteindre la
            première page
          </div>
        </q-card-section>
      </q-card>
    </div>

    <div class="col-5">
      <q-card flat bordered class="q-ma-sm">
        <img src="~assets/admin.jpg" />

        <q-card-section>
          <div class="text-h6">Administration</div>
          <div class="text-subtitle2">
            Gestion personnalisée de votre site internet
          </div>
        </q-card-section>
      </q-card>
    </div>
    <div class="col-1"></div>
    <div class="col-5">
      <q-card flat bordered class="q-ma-sm">
        <img src="~assets/web.jpg" />

        <q-card-section>
          <div class="text-h6">Les solutions</div>
          <div class="text-subtitle2">E-commerce, site dynamique</div>
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
