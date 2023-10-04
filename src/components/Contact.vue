<template>
  <div class="col-12">
    <h1 class="titleComponents">Contactez-nous</h1>
  </div>

  <div class="row">
    <div class="col-md-6 col-sm-12">
      <div class="q-pa-md" style="max-width: 700px">
        <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md">
          <q-input filled v-model="SocietyName" label="Nom de la société *" />
          <q-input filled v-model="FirstName" label="Nom *" lazy-rules />

          <q-input filled v-model="LastName" label="Prénom" lazy-rules />

          <q-input filled v-model="Phone" label="Téléphone" lazy-rules />

          <q-input v-model="Email" filled type="email" label="E-mail" />

          <q-input v-model="Message" filled type="textarea" label="Message" />
          <div>
            <q-btn label="Envoyer" type="submit" color="primary" />
            <q-btn
              label="Réinitialiser"
              type="reset"
              color="primary"
              flat
              class="q-ml-sm"
            />
          </div>
        </q-form>
      </div>
    </div>
    <div class="col-md-6 col-sm-12">
      <br />
      <img src="~assets/mail.png" width="500" class="d-none d-md-block" />
    </div>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "ContactContainer",

  setup() {
    return {
      SocietyName: ref(""),
      FirstName: ref(""),
      LastName: ref(""),
      Phone: ref(""),
      Email: ref(""),
      Message: ref(""),
    };
  },
});
</script>
