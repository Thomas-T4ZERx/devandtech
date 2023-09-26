<template>
  <q-header elevated style="background-color: white">
    <q-toolbar class="text-blue shadow-2 rounded-borders">
      <img alt="Quasar logo" src="~assets/logo.png" style="height: 70px" />

      <q-btn
        icon="menu"
        round
        size="md"
        class="q-pa-md"
        @click="toggleLeftDrawer"
        v-if="isScreenSmall"
        style="margin-left: auto"
      />

      <q-space v-else />

      <q-tabs v-model="tab" shrink stretch v-if="!isScreenSmall">
        <q-tab
          v-for="link in essentialLinks"
          :key="link.title"
          :name="link.title"
          class="icon-tab"
        >
          <div class="icon-container">
            <q-icon
              :name="link.icon"
              size="24px"
              style="margin-right: 10px"
              class="test"
            />
            {{ link.title }}
          </div>
        </q-tab>
      </q-tabs>
    </q-toolbar>
  </q-header>

  <q-drawer
    v-model="leftDrawerOpen"
    side="left"
    bordered
    content-class="bg-white burger-drawer"
    :width="400"
    style="position: fixed; top: 0; left: 0; height: 100%"
  >
    <!-- Utilisation de flex pour centrer le contenu verticalement -->

    <q-list dense>
      <q-item>
        <q-btn
          round
          icon="close"
          text-color="blue"
          size="md"
          @click="leftDrawerOpen = false"
          class="q-ml-auto"
          style="float: right; margin-right: 15px; top: 15px"
        />
      </q-item>
      <q-item
        clickable
        v-for="link in essentialLinks"
        :key="link.title"
        @click="navigateTo(link.link)"
        style="top: 50px"
      >
        <!-- Icône et texte ici -->
        <q-item-section
          avatar
          class="blue-text"
          v-if="isScreenSmall"
          style="margin-left: 80px; margin-right: auto"
        >
          <q-icon :name="link.icon" />

          <br />
        </q-item-section>

        <q-item-section class="blue-text" style="font-size: 20px">
          <q-item-label>{{ link.title }}</q-item-label>

          <br />
        </q-item-section>
      </q-item>
    </q-list>
  </q-drawer>
</template>

<script>
import { defineComponent, ref, computed, watch, onMounted } from "vue";

export default defineComponent({
  name: "EssentialLink",
  props: {
    title: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      default: "#",
    },
    icon: {
      type: String,
      default: "",
    },
  },
  setup() {
    const leftDrawerOpen = ref(false);
    const isScreenSmall = ref(window.innerWidth <= 870);

    const toggleLeftDrawer = () => {
      leftDrawerOpen.value = !leftDrawerOpen.value;
    };

    const closeDrawerOnLargeScreen = () => {
      if (window.innerWidth > 870) {
        leftDrawerOpen.value = false;
      }
    };

    const handleResize = () => {
      isScreenSmall.value = window.innerWidth <= 870;
      closeDrawerOnLargeScreen();
    };

    onMounted(() => {
      window.addEventListener("resize", handleResize);
    });

    watch(isScreenSmall, closeDrawerOnLargeScreen);

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      isScreenSmall,
      toggleLeftDrawer,
    };
  },
  methods: {
    navigateTo(link) {
      // Ajoutez la logique de navigation ici
    },
  },
});

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
</script>

<style>
.icon-tab {
  width: auto; /* Ajustez la largeur des onglets selon le contenu */
}

.icon-container {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  margin-right: 20px; /* Espace plus important entre l'icône et le texte */
}

/* Style pour le q-drawer */
.bg-white {
  background-color: white;
}

/* Style pour le texte bleu dans le tiroir */
.blue-text {
  color: #2196f3 !important;
}

/* Style pour le menu burger */
.burger-drawer {
  width: 300px; /* Largeur personnalisée du menu burger (ajustez selon vos besoins) */
}

@media screen and (max-width: 1000px) {
  .test {
    display: none;
  }
}
</style>
