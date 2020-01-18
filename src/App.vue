<template>
  <div id="app">
    
   <b-container class="bv-example-row">
      <b-row align-h="center" class="mt-5">
        <b-card class="text-center" >
          <b-form @submit="onSubmit" @reset="onReset" v-if="show">
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

            <b-form-group id="input-group-4">
              <b-form-checkbox-group v-model="form.checked" id="checkboxes-4">
                <b-form-checkbox value="me">Lembrar de mim</b-form-checkbox>
              </b-form-checkbox-group>
            </b-form-group>

            <b-button type="submit" variant="primary">Entrar</b-button>
          </b-form>
        </b-card>
      </b-row>
    </b-container>

    <!--FORM CADASTRO -->

    <b-container>
       <h2 align-h="left">Cadastro</h2>
       <b-card class="text-center form-cadastro"  >
        <div>
          <b-form inline class="justify-content-center" >
            <label class="sr-only" for="inline-form-input-name">Name</label>
            <b-input
              id="inline-form-input-name"
              class="mb-2 mr-sm-2 mb-sm-0"
              placeholder="Jane Doe"
            ></b-input>

            <label class="sr-only" for="inline-form-input-username">Username</label>
            <b-input-group prepend="@" class="mb-2 mr-sm-2 mb-sm-0">
              <b-input id="inline-form-input-username" placeholder="Username"></b-input>
            </b-input-group>
            <b-button variant="primary">Save</b-button>
          </b-form>
        </div>

       </b-card>

       <div>
          <b-table striped hover :items="items" :fields="fields"></b-table>
       </div>


    </b-container>
 
</div>
   
</template>

<script>

export default {
  name: 'app',
  components: { 
  },
  data() {
    return {
        form: {
          email: '',
          password: '',
          checked: []
        },
        show: true,
        fields: ['Nome', 'email' ],
        items: [
          { Nome: 'Dickerson Macdonald', email: 'macdonald@email.com' },
          { Nome: 'Larsen Shaw', email: 'shaw@email.com' },
          { Nome: 'Geneva Wilson', email: 'wilson@email.com' },
          { Nome: 'Jami Carney', email: 'carney@email.com' }
        ]
      }
  },
  methods: {
    onSubmit(evt) {
      evt.preventDefault()
      alert(JSON.stringify(this.form))
    },
    onReset(evt) {
      evt.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.name = ''
      this.form.checked = []
      // Trick to reset/clear native browser form validation state
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    }
  }
}
</script>

<style>
  
</style>
