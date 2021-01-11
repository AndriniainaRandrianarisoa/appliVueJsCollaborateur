<template>
  <b-form id="formulaire" @submit.prevent="valider()">
        <b-form-group
          label="Nom"
          label-for="nom">
            <b-form-input
              v-model="newCollaborateur.Nom"
              id="nom"
              placeholder="Entrer votre nom"
              required>
            </b-form-input> 
        </b-form-group>

        <b-form-group
          label="Prenom"
          label-for="prenom">
            <b-form-input
              v-model="newCollaborateur.Prenom"
              id="prenom"
              placeholder="Entrer votre prénom"

              required>
            </b-form-input>
        </b-form-group>

        <b-form-group
          label="Adresse mail"
          label-for="mail">
            <b-form-input
            v-model="newCollaborateur.Email"
            id="mail"
            required
            placeholder="Entrer votre email"
            type="email">
            </b-form-input>
        </b-form-group>

        <b-form-group
          label="Entrer votre Sexe"
          label-for="sexe">
            <b-form-select
            v-model="selected"
            id="sexe"
            options="options()">
            </b-form-select>
        </b-form-group>


        <b-button type="submit" for="formulaire">Enregistrer</b-button>
      </b-form>
</template>

<script>
export default {
    name: "FormulaireCollaborateur",
    data() {
        return {
            selected: ["a"],
            options: [
                {value: null, text:"Selectionner votre sexe"},
                {value: "a", text: "Homme"},
                {value: "b", text:"Femme"}
            ],
            newCollaborateur: {},    
        }
    },
    methods: {
      // fonction pour transferer les donnees au parents
        valider() {
            this.$emit("create", this.newCollaborateur);
        },
    }
}
</script>

<style>

</style>