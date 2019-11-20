<template>
  <div class="Adoption_Home">
    <div class="overlay">
      <div class="Adoption_Home_contenido">
        <h1>Adopta a un nuevo Mejor Amigo.</h1>
        <p>Total de Animales: {{ animalsCount }}</p>
        <button @click="togglePetForm" class="btn btn-primary py-3 px-5">Nueva Mascota</button>
        <div class="Adoption_Form container">
          <b-form @submit.prevent="handleSubmit" v-if="showPetForm">
          <b-form-group id="exampleInputGroup2" label="Nombre:" label-for="exampleInput2">
            <b-form-input
              id="exampleInput2"
              type="text"
              v-model="formData.nombre"
              required
              placeholder="Ingresar Nombre" />
          </b-form-group>

          <b-form-group id="exampleInputGroup3" label="Especie:" label-for="exampleInput3">
            <b-form-select id="exampleInput3" :options="['cats', 'dogs']" required v-model="formData.species" />
          </b-form-group>

          <b-form-group id="exampleInputGroup2" label="Edad:" label-for="exampleInput2">
            <b-form-input
              id="exampleInput2"
              type="number"
              v-model="formData.edad"
              required
              placeholder="Ingresar Edad" />
          </b-form-group>

          <b-button type="submit" variant="primary">Guardar</b-button>
          <b-button type="reset" variant="success">Limpiar</b-button>
        </b-form>
        </div> 
      </div>        
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'

export default {
  name: 'home',
  data() {
    return {
      showPetForm: false,
      formData: {
        nombre: '',
        edad: 0,
        species: null
      }
    }
  },
  computed: {
    ...mapGetters([
      'animalsCount'
    ])
  },
  methods: {
    ...mapActions([
      'addPet'
    ]),
    togglePetForm() {
      this.showPetForm = !this.showPetForm
    },
    handleSubmit() {
      const { species, edad, nombre } = this.formData
      const payload = {
        species,
        pet: {
          nombre,
          edad
        }
      }
      this.addPet(payload)

      this.formData = {
        nombre: '',
        edad: 0,
        species: null
      }
    }
  }
}
</script>
