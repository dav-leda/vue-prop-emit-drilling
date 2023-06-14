<template>
  <main>

    <h2>Componente 2</h2>

    <ComponenteTres
      :una-prop="unaProp" 
      @emitir-data="reEmitirData"
    />

  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

import ComponenteTres from './ComponenteTres.vue'

export default defineComponent({

  components: {
    ComponenteTres
  },

  emits: ['emitir-data'],

  props: {
    unaProp: String
  },

  methods: {
    reEmitirData(value: string) {
      this.$emit('emitir-data', value)
    },
  }
})
</script>

<style scoped>

</style>
