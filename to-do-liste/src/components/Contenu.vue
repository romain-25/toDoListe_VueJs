<template>
    <div class="container mt-5">
        <h1>Entrez des tâches.</h1>

    <form>
        <div class="form-group">
            <label for="action"></label>
            <input v-model="formData.tache" type="text" id="action" class="form-control">
        </div>

        <button v-on:click.prevent="creationItem" class="btn btn-primary mb-3">Créer une tâche</button>

    </form>
        <ul>
            <li v-bind:key="index" v-for="(tache, index) in tableauTaches">
                <item v-bind:id="index" :tache="tache" :suppression="suppression"></item>
            </li>

        </ul>

    </div>
</template>

<script>
    import Item from './Item'
    export default {
        name: "Contenu.vue",
        data() {
            return{
                formData: {
                    tache:''
                },
                tableauTaches: ['Voici vos tâches']
            }

        },
        components: {
            'item': Item
        },
        methods: {
                creationItem: function(){
                    this.tableauTaches.push(this.formData.tache)
                    this.formData.tache=''
                },
            suppression: function (e) {
                this.tableauTaches.splice(e.target.parentNode.id, 1)
            }
            },

    }
</script>

<style scoped>
    h1{
        margin-top: 100px !important;
        margin-bottom: 100px !important;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
</style>