<template>
  <div> 
    <b-list-group>
      <b-list-group-item v-for= "collaborateur in collaborateurs" :key="collaborateur.nom">
        {{ collaborateur.Nom }} {{ collaborateur.Prenom }} 
        <template>
          <div class="mb-1" style="display:inline; margin-top:10px ">
            <b-icon icon="arrow-right-square"></b-icon>
          </div>
        </template>

       <!-- <button v-on:click="editer(collaborateur)">Editer</button> -->
      </b-list-group-item>
    </b-list-group>
    <b-button variant="outline-primary" v-on:click="ajouter" style="margin-top:10px">Ajouter un nouveau collaborateur
      <template>
        <div class="mb-1" style="display:inline; margin-top:10px ">
          <b-icon icon="plus-circle"></b-icon>
        </div>
      </template>
    </b-button>
   
    <b-modal v-model="showModal" hide-footer>
      <template #modal-title>
      Ajouter un collaborateur
      </template>
          <formulaire-collaborateur v-on:create="creer"></formulaire-collaborateur>      
    </b-modal>    
  </div>  
  
  
</template>

<script>
import formulaireCollaborateur from "./FormulaireCollaborateur"

export default {
  name: 'Liste',
  components: { formulaireCollaborateur },
  data() {
      return {
      showModal: false,  
      collaborateurs: [],
      }
  },
  methods: {
    ajouter() {
      this.showModal = true
    },
    creer(newCollaborateur) {
      this.collaborateurs.push(newCollaborateur);
      this.showModal = false;
    },
    // editer(collaborateur) {
    //   this.ajouter();
    //   this.newCollaborateur=collaborateur
    // }
  }
  
  
}
</script>

<style scoped>



</style>
