<template>
    <b-card class="text-center" >
        <b-form @submit.prevent="onSubmit" @reset.prevent="onReset">
        <b-form-group
            id="input-group-1"
            label="Email:"
            label-for="input-1"
        >
            <b-form-input
            id="input-1"
            v-model="form.email"
            type="email"
            required
            placeholder="Seu email"
            ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-2" label="Senha:" label-for="input-2">
            <b-form-input
            id="input-2"
            v-model="form.password"
            type="password"
            required
            placeholder="Sua senha"
            ></b-form-input>
        </b-form-group>

        <b-form-checkbox v-model="form.checked" :value="true">Lembrar de mim</b-form-checkbox>

        <b-button type="submit" variant="primary">Entrar</b-button>
        </b-form>
    </b-card>
</template>

<script>
export default {
    data() {
        return {
            form: {
                email: '',
                password: '',
                checked: false
            },       
        }
    },
    methods: {
        onSubmit() {
            if (this.form.email === 'eu@eu.com'&& this.form.password === '123') {
                this.$router.push('/register')
            }
        },
        onReset() {
            this.form.email = ''
            this.form.name = ''
            this.form.checked = []
        }
  }
}
</script>

<style>
    
</style>