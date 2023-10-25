<template>
  <div class="col-12">
    <h1 class="titleComponents">Contactez-nous</h1>
  </div>

  <div class="row">
    <div class="col-md-6 col-sm-12 formMobile">
      <div class="q-pa-md" style="max-width: 100%">
        <q-form @submit.prevent="sendEmail" class="q-gutter-md">
          <q-input
            filled
            v-model="SocietyName"
            label="Nom de la société *"
            :rules="[val => isSocietyNameValid || val && val.length > 0 || 'Nom de la société obligatoire']"
            :error="!isSocietyNameValid"
          />

          <q-input
            filled
            v-model="FirstName"
            label="Nom *"
            :rules="[val => isFirstNameValid || val && val.length > 0 || 'Nom obligatoire']"
            :error="!isFirstNameValid"
          />

          <q-input
            filled
            v-model="LastName"
            label="Prénom"
            :rules="[val => isLastNameValid || val && val.length > 0 || 'Prénom obligatoire']"
            :error="!isLastNameValid"
          />

          <q-input
            filled
            v-model="Phone"
            label="Téléphone"
            :rules="[val => isPhoneValid || val && val.length > 0 || 'Téléphone obligatoire']"
            :error="!isPhoneValid"
          />

          <q-input
            v-model="Email"
            filled
            type="email"
            label="E-mail"
            :rules="[val => isEmailValid || val && val.length > 0 || 'E-mail obligatoire']"
            :error="!isEmailValid"
          />

          <q-input
            v-model="Message"
            filled
            type="textarea"
            label="Message"
            :rules="[val => isMessageValid || val && val.length > 0 || 'Message obligatoire']"
            :error="!isMessageValid"
          />
          <div>
            <vue-friendly-captcha sitekey="FCMIQ6ARDN414T91" />
            <br />
            <q-btn label="Envoyer" type="submit" value="Send" color="primary"/>
            <q-btn
              label="Réinitialiser"
              type="reset"
              color="primary"
              flat
              class="q-ml-sm"
              @click="resetForm"
            />
          </div>
        </q-form>
      </div>
    </div>
    <div class="col-md-6 col-sm-12">
      <br />
      <img src="~assets/mail.png" width="500" class="d-none d-md-block imageMobile" />
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
import { useQuasar } from 'quasar'
import emailjs from 'emailjs-com'
import VueFriendlyCaptcha from '@somushq/vue3-friendly-captcha'

export default {
  name: "ContactContainer",
  components: {
    VueFriendlyCaptcha
  },
  setup() {
    const $q = useQuasar()
    const SocietyName = ref("")
    const FirstName = ref("")
    const LastName = ref("")
    const Phone = ref("")
    const Email = ref("")
    const Message = ref("")
    const isEmailSent = ref(false)

    const isSocietyNameValid = ref(true)
    const isFirstNameValid = ref(true)
    const isLastNameValid = ref(true)
    const isPhoneValid = ref(true)
    const isEmailValid = ref(true)
    const isMessageValid = ref(true)

    const sendEmail = async () => {
      if (!SocietyName.value || SocietyName.value.length === 0) {
        isSocietyNameValid.value = false;
        return;
      } else {
        isSocietyNameValid.value = true;
      }

      if (!FirstName.value || FirstName.value.length === 0) {
        isFirstNameValid.value = false;
        return;
      } else {
        isFirstNameValid.value = true;
      }

      if (!LastName.value || LastName.value.length === 0) {
        isLastNameValid.value = false;
        return;
      } else {
        isLastNameValid.value = true;
      }

      if (!Phone.value || Phone.value.length === 0) {
        isPhoneValid.value = false;
        return;
      } else {
        isPhoneValid.value = true;
      }

      if (!Email.value || Email.value.length === 0) {
        isEmailValid.value = false;
        return;
      } else {
        isEmailValid.value = true;
      }

      if (!Message.value || Message.value.length === 0) {
        isMessageValid.value = false;
        return;
      } else {
        isMessageValid.value = true;
      }

      const templateParams = {
        societyName: SocietyName.value,
        firstName: FirstName.value,
        lastName: LastName.value,
        phone: Phone.value,
        email: Email.value,
        message: Message.value
      }

      try {
        await emailjs.send(
          "service_4g6vomz",
          "template_99jr5lb",
          templateParams,
          "FMUu0TeZu-HpJRWC0"
        )
        isEmailSent.value = true
        $q.notify({
          position: 'center',
          icon: 'done',
          color: 'positive',
          message: 'Votre message a bien été envoyé'
        })
        resetForm()
      } catch (error) {
        $q.notify({
          position: 'center',
          icon: 'done',
          color: 'negative',
          message: "Erreur lors de l'envoi de votre message"
        })
        resetForm()
      }
    }

    const resetForm = () => {
      isSocietyNameValid.value = true
      isFirstNameValid.value = true
      isLastNameValid.value = true
      isPhoneValid.value = true
      isEmailValid.value = true
      isMessageValid.value = true

      SocietyName.value = ""
      FirstName.value = ""
      LastName.value = ""
      Phone.value = ""
      Email.value = ""
      Message.value = ""
      isEmailSent.value = false
    }

    return {
      SocietyName,
      FirstName,
      LastName,
      Phone,
      Email,
      Message,
      isEmailSent,
      sendEmail,
      resetForm,
      isSocietyNameValid,
      isFirstNameValid,
      isLastNameValid,
      isPhoneValid,
      isEmailValid,
      isMessageValid
    }
  }
}
</script>
