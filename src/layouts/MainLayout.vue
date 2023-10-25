<template>
  <q-layout view="hhr lpr ffR">
    <q-header elevated style="background-color: white">
      <EssentialLink />
    </q-header>
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
      <vue-cookie-accept-decline
        :debug="false"
        :disableDecline="false"
        :showPostponeButton="false"
        @clicked-accept="cookieClickedAccept"
        @clicked-decline="cookieClickedDecline"
        @clicked-postpone="cookieClickedPostpone"
        @removed-cookie="cookieRemovedCookie"
        @status="cookieStatus"
        elementId="myPanel1"
        position="bottom-left"
        ref="myPanel1"
        transitionName="slideFromBottom"
        type="floating"
        style="max-width: 700px"
      >
        <template #postponeContent>&times;</template>
        <template #message>
          Pour offrir les meilleures expériences, nous utilisons des
          technologies telles que les cookies pour stocker et/ou accéder aux
          informations des appareils. Le fait de consentir à ces technologies
          nous permettra de traiter des données telles que le comportement de
          navigation ou les ID uniques sur ce site.
        </template>
        <template #declineContent>Refuser</template>
        <template #acceptContent>Accepter</template>
      </vue-cookie-accept-decline>
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
import VueCookieAcceptDecline from "vue-cookie-accept-decline";
import "vue-cookie-accept-decline/dist/vue-cookie-accept-decline.css";

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
    VueCookieAcceptDecline,
  },
  methods: {
    cookieStatus(status) {
      console.log("status: " + status);
      this.status = status;
    },
    cookieClickedAccept() {
      console.log("here in accept");
      this.status = "accept";
    },
    cookieClickedDecline() {
      console.log("here in decline");
      this.status = "decline";
    },
    cookieRemovedCookie() {
      console.log("here in cookieRemoved");
      this.status = null;
      this.$refs.myPanel1.init();
    },

    removeCookie() {
      console.log("Cookie removed");
      this.$refs.myPanel1.removeCookie();
    },
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
