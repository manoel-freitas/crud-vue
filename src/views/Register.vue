<template>
    <b-container>
        <router-link to="/">Login</router-link>
        <h2 align-h="left">Cadastro</h2>
        <b-card class="text-center form-cadastro"  >
            <add-person-form @onAddPerson="onAddPerson($event)" />
        </b-card>
        <b-table striped hover :items="items" :fields="fields"></b-table>
    </b-container>
</template>

<script>
import AddPersonForm from "../components/AddPersonForm";
export default {
    components: {
        AddPersonForm
    },
    data() {
        return {
            fields: ['nome', 'email' ],
            items: []
        }
    },
    methods: {
        onAddPerson(person) {
            this.items.push(person)
        }
    }
}
</script>