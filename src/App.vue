
<template>
  <main>
    
    <h1 class="title">App.vue</h1>

    <p class="mt-1 bold">Cadena de emits desde Componente 3:</p>

    <p>{{ dataRecibida }}</p>

    <ComponenteUno
      :una-prop="dataEnviada" 
      @emitir-data="recibirData"
    />

  </main>
</template>

<script lang="ts">

import { defineComponent } from 'vue'
import ComponenteUno from './components/ComponenteUno.vue';


export default defineComponent({

  components: {
    ComponenteUno
  },

  data: () => ({ 
    dataEnviada: 'Data enviada desde App.vue',
    dataRecibida: ''
  }),

  methods: {
    recibirData(value: string) {
      this.dataRecibida = value
    }
  }
})

</script>


<style>

</style>
