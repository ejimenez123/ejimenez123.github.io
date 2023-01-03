<script lang="ts">
import BackendKnowledge from '@/components/BackendKnowledge.vue'
import BackendKnowledges from '@/store/BackendKnowledges'

export default {
  components: {    
    BackendKnowledge    
  },
  data () {
    return {
      readMore: false,
      items: BackendKnowledges.items      
    }
  }  
  
}
</script>

<template>
<div class="">
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
    <BackendKnowledge
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
