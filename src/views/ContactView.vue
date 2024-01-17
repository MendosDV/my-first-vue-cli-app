<template>
  <h2>Contactez nous</h2>
		<p>Adresse : {{ address }}</p>
		<p>Téléphone : {{ phone }}</p>
		<p>Email : {{ email }}</p>
		<p>Horaires :</p>
		<ul class="no-bullet">
			<li>L-V: 06:00 à 16:00</li>
			<li>Samedi: 07:00 à 14:00</li>
			<li>Dimanche: 07:00 à 12:00</li>
		</ul>
</template>

<script>
export default {
  name: "ContactView",
	data() {
		return {
			address: "18 avenue du Beurre, Paris, France",
			email: "hello@cafewithavue.bakery",
			phone: "01 88 88 88 88"
		}
	},
  beforeCreate() {
    console.log("Je suis créé")
  },
  created() {
    console.log("Je suis créé")
  },
  beforeMount() {
    console.log("Avant d'être monté sur le DOM")
  },
  mounted() {
    console.log("J'ai été monté sur le DOM")
  },
  beforeUnmount() {
    console.log("Avant d'être démonté")
  },
  unmounted() {
    console.log("Je suis démonté")
  }
}
</script>

<style>
  .no-bullet {
    list-style: none;
  }
</style>
