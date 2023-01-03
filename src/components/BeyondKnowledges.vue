<script lang="ts">
import BeyondKnowledge from '@/components/BeyondKnowledge.vue'
import BeyondKnowledges from '@/store/BeyondKnowledges'

export default {
  components: {    
    BeyondKnowledge    
  },
  data () {
    return {
      readMore: false,
      items: BeyondKnowledges.items      
    }
  }  
  
}
</script>

<template>
<div class="">
<p class="p-4 text-left">   
     * Conocimientos
     <button class="bg-stone-700 hover:bg-stone-600 px-3 rounded" @click="readMore =! readMore">
        <span v-if="readMore">Leer -</span>
        <span v-else>Leer +</span>
      </button>
  </p>
  <div v-if="readMore"> 
    <BeyondKnowledge
      v-for="(item, index) in items"
      :key="index"
      :n="index"
      :data="item"/>  
  </div>
</div>
</template>



<style scoped></style>
