<script lang="ts">
import Icon from '@/components/Icon.vue'
import FrontendSkill from '@/components/FrontendSkill.vue'
import FrontendSkills from '@/store/FrontendSkills'

export default {
  components: {
    Icon,
    FrontendSkill    
  },
  data () {
    return {
      readMore0: false,
      readMore1: false,      
      items: FrontendSkills.items      
    }
  }  
}
</script>

<template>
<div class="">
  <div class="pt-4 text-base font-bold flex items-center text-left border-b-2 border-red-200">
    <icon name="baggage" />
    <a href="https://en.wikipedia.org/wiki/Front-end_web_development" target="_blank" class="font-bold text-blue-500 hover:text-blue-800 visited:text-purple-600">Frontend Developer</a>
  </div>
  <div class="p-4 text-base flex items-center text-left">
    <p>Desarrollador que programa las definiciones de estructura, diseño y funcionalidad de una página web o interfaz de usuario. Teniendo en cuenta su usabilidad y legibilidad, para que los usuarios
    <Transition>
    <span v-if="readMore0">
      puedan interactuar con el software y disfrutar de una experiencia satisfactoria. Su trabajo también está relacionado con la optimización de los recursos consumidos por el cliente a través del servidor.
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
    <FrontendSkill
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
