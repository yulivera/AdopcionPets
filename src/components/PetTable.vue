<template>
 <div class="container Adopción_table">
    <h1 class="mb-2">{{ species }} en Adopción</h1>
    <b-table striped hover :items="pets">
      <template v-slot:cell(nombre)="data">
        <router-link :to="`/pets/${species}/${data.index}`">
          {{ data.value }}
        </router-link>
      </template>
    </b-table>
  </div>
</template>

<script>
export default {
  props: {
    species: String,
    pets: Array
  }
}
</script>
