<template>
<div class="">
  <div class="pt-4 text-base font-bold flex items-center text-left border-b-2 border-red-200">
    <icon name="baggage" /> 
     <a href="https://es.wikipedia.org/wiki/Desarrollo_%C3%A1gil_de_software" target="_blank" class="font-bold text-blue-500 hover:text-blue-800 visited:text-purple-600">Agile Development</a>
    </div>
  <div class="p-4 text-base flex items-center text-left">
    <p>Conjunto de buenas prácticas y técnicas para trabajar en equipo y obtener el mejor resultado, adaptándose a los cambios de requerimientos inevitables y naturales en  cualquier punto
    <span v-if="readMore0">
      de la vida del proyecto. Tales como Scrum, eXtreme Programming, Kanban, Lean y Kaizen.
    </span>
    <span v-else> ... </span>        
      <button class="bg-stone-700 hover:bg-stone-600 px-3 rounded" @click="readMore0 =! readMore0">
        <span v-if="readMore0">Leer -</span>
        <span v-else>Leer +</span>
      </button> 
    </p>
  </div> 
    <p class="p-4 text-left">* Metodologías
      <button class="bg-stone-700 hover:bg-stone-600 px-3 rounded" @click="readMore1 =! readMore1">
        <span v-if="readMore1">Leer -</span>
        <span v-else>Leer +</span>
      </button>
  </p>
  <div v-if="readMore1">
  <AgileDevelopment
    v-for="(item, index) in items"
    :key="index"
    :n="index"
    :data="item"/>
</div>
</div>
</template>

<script lang="ts">
import Icon from '@/components/Icon.vue'
import AgileDevelopment from '@/components/AgileDevelopment.vue'
import AgileDevelopments from '@/store/AgileDevelopments'

export default {
  components: {
    Icon,
    AgileDevelopment    
  },
  data () {
    return {
      readMore0: false,
      readMore1: false,
      items: AgileDevelopments.items      
    }
  }  
}
</script>

<style scoped></style>

