<template>
        <div>
            <h1 class=display-1>Commander</h1>

            <h2>Produits disponibles</h2>
            <div class="card-deck">
                <Produit v-for="produit in produits" v-bind:nom="produit.nom" role="commander" v-bind:prix="produit.prix" v-on:commande="ajouterProduit"/>
            </div>

            <h2>Produits commandés</h2>
            <div class="card-deck">
                <Produit v-for="produit in commandes" v-bind:nom="produit.nom" role="affichage" v-bind:prix="produit.prix" />
            </div>
        </div>
</template>
    

<script>
import Produit from '@/components/Produit.vue'

export default {
    components: {
        Produit
    },
    data(){
        return {
            produits: [
                {nom: 'Pizza', prix: 3.0 },
                {nom: 'Frites', prix: 4.0 },
                {nom: 'Hamburger', prix: 5.0 },
                {nom: 'Cheesburger', prix: 2.0 }
            ],
            commandes: [
                { nom: 'Frites', prix: 2.0 }
            ]
        }
    },
    methods:{
        ajouterProduit(nom, prix){
            this.commandes.push({nom: nom, prix: prix})
        }
    }
}
</script>

<style scoped>

</style>