<template>
  <q-layout-footer bordered>
    <v-row justify="center" no-gutters>
      <v-col class="text-center mt-4" cols="12">
        <q-toolbar bordered class="bg-grey-3 text-primary">
          <q-toolbar-title>
            {{ new Date().getFullYear() }} — <strong>Dev&Tech</strong> -
            <a href="https://storyset.com/online"
              >Online illustrations by Storyset</a
            >
          </q-toolbar-title>
        </q-toolbar>
      </v-col>
    </v-row>
  </q-layout-footer>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "FooterContainer",
});
</script>
