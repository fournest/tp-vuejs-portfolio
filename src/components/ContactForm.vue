<script setup>
import { ref, watch, computed } from 'vue'

const nomPrenom = ref('');
const email = ref('');
const telephone = ref('');
const message = ref('');
const accepteConditions = ref(false);

const isNomPrenomValid = ref(true)
const isEmailValid = ref(true);
const isTelephoneValid = ref(true);
const isMessageValid = ref(true);


const validateName = (nomPrenom) => {
  const nomPrenomRegex = /^[\p{L}\s'\-.]+$/
  return nomPrenomRegex.test(nomPrenom);
};



const validateEmail = (email) => {
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailRegex.test(email);
};

const validatePhone = (telephone) => {
  const phoneRegex = /^\+?[\d\s\-\(\).]{7,25}$/;
  return phoneRegex.test(telephone);
};

const validateMessage = (message) => {
  const messageRegex = /^[\p{L}\p{N}\p{P}\p{S}\p{Z}\s]+$/;
  return messageRegex.test(message);
};

watch(nomPrenom, (newNomPrenom) => {
  if (newNomPrenom) {
    isNomPrenomValid.value = validateName(newNomPrenom);
  } else {
    isNomPrenomValid.value
  }
});

watch(email, (newEmail) => {
  if (newEmail) {
    isEmailValid.value = validateEmail(newEmail)
  } else {
    isEmailValid.value
  }
});
watch(telephone, (newPhone) => {
  if (newPhone) {
    isTelephoneValid.value = validatePhone(newPhone)
  } else {
    isTelephoneValid.value
  }
});

watch(message, (newMessage) => {
  if (newMessage) {
    isMessageValid.value = validateMessage(newMessage)
  } else {
    isMessageValid.value
  }
});
</script>

<template>
  <h2>Formulaire de Contact</h2>
  <form>
    <label for="name">Nom/Prénom</label>
    <input type="text" placeholder="Votre nom et votre prénom ici" v-model="nomPrenom">
    <span v-if="!isNomPrenomValid && nomPrenom" class="error-msg">Nom Prénom invalides</span>

    <label for="email">E-mail</label>
    <input type="text" placeholder="Votre E-mail ici" v-model="email">
    <span v-if="!isEmailValid && email" class="error-msg">Email invalide</span>

    <label for="phone">Téléphone</label>
    <input type="tel" placeholder="Votre téléphone ici" v-model="telephone">
    <span v-if="!isTelephoneValid && telephone" class="error-msg">Telephone invalide</span>

    <textarea name="Message" placeholder="Votre message ici" v-model="message"></textarea>
    <span v-if="!isMessageValid && message" class="error-msg">Message invalide </span>

    <input type="checkbox" id="consent" v-model="accepteConditions" required>
    <label for="consent">En soumettant ce formulaire, j'accepte que les informations saisies soient exploitées
      dans le cadre de cette demande.</label>

    <button type="submit">Envoyer</button>


  </form>

</template>

<style scoped></style>