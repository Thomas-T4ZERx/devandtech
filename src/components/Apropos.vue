<template>
  <q-card flat bordered style="background-color: #fefcfa; margin-top: 20px">
    <q-card-section horizontal>
      <q-card-section>
        <div class="col-12">
          <h2
            style="
              color: #696df3;
              text-align: center;
              font-weight: unset;
              margin-left: -10px;
            "
          >
            A propos de DevandTech
          </h2>
          <h3
            style="
              font-family: Roboto;
              color: #1e0e6a;
              text-align: center;
              margin-left: -10px;
            "
          >
            Nous sommes à l'écoute de votre projet.
          </h3>
          <p style="font-size: 18px">
            La société Dev&Tech est là pour vous aider dans la création et le
            développement de votre entreprise. <br />
            <br />
            <img
              alt="Quasar logo"
              src="~assets/list-style.png"
              class="img-fluid"
            />
            Nous vous aidons dans le développement de votre solution
            informatique
            <br />
            <img
              alt="Quasar logo"
              src="~assets/list-style.png"
              class="img-fluid"
            />
            Nous vous accompagnons pour chaque étape de votre projet <br />

            <img
              alt="Quasar logo"
              src="~assets/list-style.png"
              class="img-fluid"
            />
            Nous adoptons le projet à vos besoins
          </p>
        </div>
      </q-card-section>
      <q-img class="col-6" src="~assets/logo-ordi.png" v-if="shouldShowImage" />
    </q-card-section>
  </q-card>
</template>
<script>
import { defineComponent, onMounted, onBeforeUnmount, ref } from "vue";

export default defineComponent({
  name: "AproposContainer",
  props: {},
  setup() {
    const shouldShowImage = ref(true);

    const handleResize = () => {
      // Mettre à jour la visibilité de l'image en fonction de la largeur de l'écran
      shouldShowImage.value = window.innerWidth >= 1000;
    };

    onMounted(() => {
      window.addEventListener("resize", handleResize);
      handleResize(); // Appeler la fonction pour gérer la visibilité initiale
    });

    onBeforeUnmount(() => {
      window.removeEventListener("resize", handleResize);
    });

    return {
      shouldShowImage,
    };
  },
});
</script>
