<template>

  <main>

    <h2>Componente 1</h2>

    <ComponenteDos
      :una-prop="unaProp" 
      @emitir-data="reEmitirData"
    />

  </main>
  
</template>

<script lang="ts">

import { defineComponent } from 'vue'
import ComponenteDos from './ComponenteDos.vue';

export default defineComponent({

  components: { 
    ComponenteDos 
  },

  emits: ['emitir-data'],

  props: {
    unaProp: String
  },

  methods: {
    reEmitirData(value: string) {
      this.$emit('emitir-data', value)
    }
  },
})

</script>

<style scoped>

</style>
