<script lang="ts">
import Icon from '@/components/Icon.vue'
import BackendSkill from '@/components/BackendSkill.vue'
import BackendSkills from '@/store/BackendSkills'

export default {
  components: {
    Icon,
    BackendSkill    
  },
  data () {
    return {
      readMore0: false,
      readMore1: false,  
      items: BackendSkills.items      
    }
  }  
}
</script>

<template>
<div class="">
  <div class="pt-4 text-base font-bold flex items-center text-left border-b-2 border-red-200">
    <icon name="baggage" /> 
     <a href="https://fp.uoc.fje.edu/blog/que-es-un-backend-developer/" target="_blank" class="font-bold text-blue-500 hover:text-blue-800 visited:text-purple-600">Backend Developer</a>
    </div>
  <div class="p-4 text-base flex items-center text-left">
    <p>
    Desarrollador que trabaja del lado del servidor procesando información recibida a través del Frontend. Encargado de diseñar la lógica  para que las acciones solicitadas en una página
    <Transition>     
    <span v-if="readMore0">
    web sean ejecutadas correctamente. Requiere conocer las interacciones con bases de datos, debido a que toda aplicación web necesita almacenar datos. Prácticamente es quien se encuentra detrás del escenario.
    </span>
    <span v-else> ... </span>
    </Transition>
      <button class="bg-stone-700 hover:bg-stone-600 px-3 rounded" @click="readMore0 =! readMore0">
      <Transition>
        <span v-if="readMore0">Leer -</span>
        <span v-else>Leer +</span>
      </Transition>
      </button>
    </p>
  </div> 
    <p class="p-4 text-left">* Habilidades
      <button class="bg-stone-700 hover:bg-stone-600 px-3 rounded" @click="readMore1 =! readMore1">
        <Transition>
        <span v-if="readMore1">Leer -</span>
        <span v-else>Leer +</span>
        </Transition>
      </button>
  </p>
  <div v-if="readMore1">
  <BackendSkill
    v-for="(item, index) in items"
    :key="index"
    :n="index"
    :data="item"/>
</div>
</div>
</template>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>

