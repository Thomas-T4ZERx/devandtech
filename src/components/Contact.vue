<template>
  <div class="row">
    <div class="col-2"></div>
    <div class="col-8">
      <h1 style="color: #e47b29">Contactez-nous</h1>
    </div>
    <div class="col-2"></div>
  </div>

  <div class="row">
    <div class="col-6">
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
    <div class="col-6">
      <br />
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m14!1m12!1m3!1d21637.29274576476!2d5.0431627722167995!3d47.32094924134575!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!5e0!3m2!1sfr!2sfr!4v1687877859652!5m2!1sfr!2sfr"
        width="600"
        height="450"
        style="border: 0"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
      ></iframe>
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
