<script lang="ts">
import FrontendKnowledge from '@/components/FrontendKnowledge.vue'
import FrontendKnowledges from '@/store/FrontendKnowledges'

export default {
  components: {    
    FrontendKnowledge    
  },
  data () {
    return {
      readMore: false,
      items: FrontendKnowledges.items      
    }
  }  
  
}
</script>

<template>
<div>
  <p class="p-4 text-left">   
     * Conocimientos
     <button class="bg-stone-700 hover:bg-stone-600 px-3 rounded" @click="readMore =! readMore">
       <Transition>
          <span v-if="readMore">Leer -</span>
          <span v-else>Leer +</span>
        </Transition>
      </button>
  </p>
  <div v-if="readMore">
    <FrontendKnowledge
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
