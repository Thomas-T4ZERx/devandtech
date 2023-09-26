<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated style="background-color: white">
      <EssentialLink />
    </q-header>

    <q-page-container>
      <BannerContainer />
      <div class="page-container">
        <div class="content-container">
          <AproposContainer />
          <ServicesContainer />
          <RealisationsContainer />
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
.page-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.content-container {
  width: 100%;
  max-width: 1500px;
  padding: 20px;
  box-sizing: border-box;
}

@media (max-width: 600px) {
  .content-container {
    padding: 10px;
  }
}
</style>
