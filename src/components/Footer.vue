<template>
  <q-layout-footer bordered>
    <q-row justify="center" no-gutters>
      <q-col class="text-center mt-4" cols="12">
        <q-toolbar bordered class="bg-grey-3 text-primary">
          <q-toolbar-title style="font-size: 15px">
            <br />
            <q-btn
              round
              href="https://www.linkedin.com/company/devandtech90/"
              target="_blank"
            >
              <q-icon name="mdi-linkedin " />
            </q-btn>
            <br />
            <br />
            <!-- Affichez le bouton "Politique de confidentialité" uniquement en mode web -->
            <div class="row" v-if="isWebMode">
              <div class="col-md-4"></div>
              <div class="col-md-2 col-sm-12">
                <q-btn
                  label="Politique de confidentialité"
                  color="primary"
                  @click="politiques = true"
                  class="q-ma-sm mr-2"
                  style="float: right"
                />
              </div>
              <div class="col-md-3 col-sm-12">
                <q-btn
                  label="Les mentions légales"
                  color="primary"
                  @click="mentions = true"
                  class="q-ma-sm mr-2"
                  style="float: left"
                />
              </div>
              <div class="col-md-4"></div>
            </div>
            <!-- Affichez le bouton "Les mentions légales" uniquement en mode mobile -->
            <div class="row" v-else>
              <div class="col-12 q-mb-sm">
                <q-btn
                  label="Politique de confidentialité"
                  color="primary"
                  @click="politiques = true"
                  class="q-ma-sm mr-2"
                />
              </div>
              <div class="col-12 q-mb-sm">
                <q-btn
                  label="Les mentions légales"
                  color="primary"
                  @click="mentions = true"
                  class="q-ma-sm"
                />
              </div>
            </div>
            <br />
            Copyright © {{ new Date().getFullYear() }} —
            <strong>Dev&Tech</strong> - Tous droits réservés. Online
            illustrations by Storyset
          </q-toolbar-title>
        </q-toolbar>
      </q-col>
    </q-row>
  </q-layout-footer>
  <q-dialog v-model="politiques" full-width>
    <q-card>
      <q-card-section class="q-pt-none">
        <div v-html="data.politiques.politiques"></div>
      </q-card-section>
      <q-separator />
      <q-card-actions align="right">
        <q-btn flat label="Fermer" color="primary" v-close-popup />
      </q-card-actions>
    </q-card>
  </q-dialog>

  <q-dialog v-model="mentions" full-width>
    <q-card>
      <q-card-section class="q-pt-none">
        <div v-html="data.mentions.mentions"></div>
      </q-card-section>
      <q-separator />
      <q-card-actions align="right">
        <q-btn flat label="Fermer" color="primary" v-close-popup />
      </q-card-actions>
    </q-card>
  </q-dialog>
</template>

<script>
import { defineComponent, ref, computed } from "vue";
import data from "../data/data.js";
export default defineComponent({
  name: "FooterContainer",
  setup() {
    const isWebMode = computed(() => window.innerWidth >= 1000);

    return {
      politiques: ref(false),
      mentions: ref(false),
      isWebMode,
      data: data,
    };
  },
});
</script>
