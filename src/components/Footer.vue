<template>
  <q-layout-footer bordered>
    <q-row justify="center" no-gutters>
      <q-col class="text-center mt-4" cols="12">
        <q-toolbar bordered class="bg-grey-3 text-primary">
          <q-toolbar-title style="font-size: 15px">
            Copyright ©  {{ new Date().getFullYear() }} —
            <strong>Dev&Tech</strong> - Tous droits réservés.
            <a href="https://storyset.com/online"
            >Online illustrations by Storyset</a
            >
          </q-toolbar-title>
        </q-toolbar>
      </q-col>
    </q-row>
  </q-layout-footer>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "FooterContainer",
});
</script>
