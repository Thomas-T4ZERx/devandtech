<template>
  <q-layout view="hhr lpr ffR">
    <EssentialLink />
    <q-page-container>
      <BannerContainer />
      <div class="page-container" id="page-container-apropos">
        <div class="content-container">
          <AproposContainer />
        </div>
      </div>
      <div class="page-container" id="page-container-service">
        <div class="content-container">
          <ServicesContainer />
        </div>
      </div>
      <div class="page-container" id="page-container-realisations">
        <div class="content-container">
          <RealisationsContainer />
        </div>
      </div>
      <div class="page-container" id="page-container-contact">
        <div class="content-container">
          <ContactContainer />
        </div>
      </div>

      <FooterContainer />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";
import AproposContainer from "components/Apropos.vue";
import ServicesContainer from "components/Services.vue";
import RealisationsContainer from "components/Realisations.vue";
import ContactContainer from "components/Contact.vue";
import BannerContainer from "components/Banner.vue";
import FooterContainer from "components/Footer.vue";

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink,
    AproposContainer,
    ServicesContainer,
    RealisationsContainer,
    ContactContainer,
    BannerContainer,
    FooterContainer,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>

<style>
@media (max-width: 600px) {
  .content-container {
    padding: 10px;
  }
}
</style>
