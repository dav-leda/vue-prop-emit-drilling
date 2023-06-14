
<template>
  <main>
    
    <h1 class="title">App.vue</h1>

    <p class="mt-1">emits desde Componente 2:</p>
    <br>
    <p class="mb-1">{{ someData }}</p>
    <p>{{ data2 }}</p>
    <p>{{ data3 }}</p>

    <ComponenteUno
      @emitir-data="recibirData"
      @emitir-data-2="recibirData2"
      @emitir-3="recibirData3"
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
    someData: '',
    data2: '',
    data3: ''
  }),

  computed: {
    someComputed() {
      return this.someData
    }
  },

  methods: {
    recibirData(value) {
      this.someData = value
    },
    recibirData2(value) {
      this.data2 = value
    },
    recibirData3(value) {
      this.data3 = value
    }
  }
})

</script>


<style scoped>

</style>
