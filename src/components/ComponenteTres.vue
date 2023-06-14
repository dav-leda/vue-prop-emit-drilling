<template>

  <main>

    <h2>Componente 3</h2>

    <button
      class="btn-primary mt-1" 
      @click="$emit('emitir-3', someData)"
    >emitir data</button>

  </main>

</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({

  components: {
  },

  props: {
    someProp: String
  },

  data: () => ({ 
    someData: 'data desde Componente 3'
  }),

  methods: {
  }
})
</script>

<style scoped>

</style>
