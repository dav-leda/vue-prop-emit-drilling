<template>
  <main>

    <h2>Componente 2</h2>

    <button
      class="btn-primary mt-1" 
      @click="emitirData"
    >emitir data</button>
    <br>
    <button
      class="btn-primary mt-1" 
      @click="emitirData2"
    >emitir data 2</button>

    <ComponenteTres @emitir-3="reEmitirData"/>

  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

import ComponenteTres from './ComponenteTres.vue'

export default defineComponent({

  components: {
    ComponenteTres
  },

  props: {
    someProp: String
  },
  data: () => ({ 
    someData: 'data desde Componente 2',
    data2: 'data 2 desde Componente 2'
  }),

  methods: {
    reEmitirData(value) {
      this.$emit('emitir-3', value)
    },
    emitirData() {
      // this.$parent.$emit sirve para saltease UN componente
      // en la cadena de emits, pero NO MAS DE UNO
      this.$parent.$emit('emitir-data', this.someData)
    },
    emitirData2() {
      this.$parent.$emit('emitir-data-2', this.data2)
    }
  }
})
</script>

<style scoped>

</style>
