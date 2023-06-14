<template>

  <main>

    <h2>Componente 3</h2>

    <button
      class="btn-primary mt-1" 
      @click="$emit('emitir-data', someData)"
    >Emitir Data</button>

    <p class="mt-1 bold">Cadena de props desde App.vue:</p>
    <p>{{ unaProp }}</p>
    
  </main>

</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({

  emits: ['emitir-data'],

  props: {
    unaProp: String
  },

  data: () => ({ 
    someData: 'Data emitida desde Componente 3'
  })
})
</script>
