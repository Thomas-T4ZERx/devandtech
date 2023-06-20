<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated style="background-color: white">
      <q-toolbar>
        <q-toolbar-title>
          <img alt="Quasar logo" src="~assets/logo.png" style="height: 70px" />
        </q-toolbar-title>
        <q-tabs
          no-caps
          active-color="primary"
          indicator-color="transparent"
          class="text-grey-8"
          v-model="tab"
        >
          <EssentialLink
            v-for="link in essentialLinks"
            :key="link.title"
            v-bind="link"
            style="color: #2c91c9"
          />
        </q-tabs>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <div class="page-container">
        <div class="content-container">
          <AproposContainer />
          <ServicesContainer />
        </div>
      </div>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";
import AproposContainer from "components/Apropos.vue";
import ServicesContainer from "components/Services.vue";

const linksList = [
  {
    title: "Nous connaître",
    icon: "home_work",
    link: "",
  },
  {
    title: "Nos services",
    icon: "computer",
    link: "",
  },
  {
    title: "Nos références",
    icon: "web",
    link: "",
  },
  {
    title: "Contact",
    icon: "contact_mail",
    link: "",
  },
];

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink,
    AproposContainer,
    ServicesContainer,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      essentialLinks: linksList,
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
