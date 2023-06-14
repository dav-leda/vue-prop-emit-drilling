<template>

  <main>

    <h2>Componente 1</h2>

    <ComponenteDos @emitir-3="recibirEmitir"/>

  </main>
  
</template>

<script lang="ts">

import { defineComponent } from 'vue'
import ComponenteDos from './ComponenteDos.vue';

export default defineComponent({

  components: { 
    ComponenteDos 
  },

  //emits: ['emitir-data', 'emitir-data-2'],

  props: {
    someProp: String
  },
  data: () => ({
    someData: ""
  }),

  methods: {
    recibirEmitir(value) {
      this.$emit('emitir-3', value)
    }
  },
})

</script>

<style scoped>

</style>
