<template>
  <section class="detalleAnimal section_gap">
    <div class="container">
      <div class="Animal_details_inner">            
        <div class="row">
          <div class="col-md-6">
              <h1>{{ animal.nombre }}</h1>
              <img class="img-fluid" :src="animal.foto" alt="Animal-foto">
            </div>
            <div class="offset-md-1 col-md-5">
              <div class="Animal_right_text mt-30">
                <p>{{animal.nota}}</p>
                <ul class="list">
                  <li><span>Edad</span>: 
                  {{animal.edad}}</li>
                  <li><span>Raza</span>: 
                  {{animal.raza}}</li>
                  <li><span>Genero</span>: 
                  {{animal.genero}}</li>
                  <li><span>Locación</span>: 
                  {{animal.locacion}}</li>    
                </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
  </section>
</template>

<script>
import { mapState } from 'vuex'

export default {

  name: 'Pet',

  data () {
    return {
    	animal: {}
    }
  },
  computed: {
  	...mapState(['cats','dogs'])
  },
  mounted() {
    const animal = this[this.$route.params.species][this.$route.params.id]
    this.animal = animal
  }
}
</script>
