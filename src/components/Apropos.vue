<template>
  <q-card flat bordered>
    <q-card-section horizontal>
      <q-card-section>
        <br />
        <p
          style="
            color: #696df3;
            line-height: 28px;
            font-family: Roboto;
            font-size: 30px;
          "
        >
          A propos de DevandTech
        </p>
        <br />
        <p
          style="
            font-family: K2D;
            line-height: 50px;
            font-weight: 600;
            font-size: 40px;
            font-family: Roboto;
            -ms-word-wrap: break-word;
            word-wrap: break-word;
            color: #1e0e6a;
          "
        >
          Nous sommes à l'écoute de votre projet.
        </p>
        <br />
        <p style="font-size: 18px">
          La société Dev&Tech est là pour vous aider dans la création et le
          développement de votre entreprise. <br />
          <br />
          <img alt="Quasar logo" src="~assets/list-style.png" />
          Nous vous aidons dans le développement de votre solution informatique
          <br />
          <img alt="Quasar logo" src="~assets/list-style.png" />
          Nous vous accompagnons pour chaque étape de votre projet <br />

          <img alt="Quasar logo" src="~assets/list-style.png" />
          Nous adoptons le projet à vos besoins
        </p>
      </q-card-section>

      <q-img class="col-5" src="~assets/logo-ordi.png" />
    </q-card-section>
  </q-card>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "AproposContainer",
  props: {},
});
</script>
