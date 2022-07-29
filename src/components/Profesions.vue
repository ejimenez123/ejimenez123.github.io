<template>
<div>
  <p class="pt-4 text-base font-bold flex items-center text-left  border-b-2 border-red-200">
    <icon name="baggage" />          
     Mi Profesión       
  </p>  
  <Profesion
    v-for="(item, index) in items"
    :key="index"
    :n="index"
    :data="item"/>
</div>
</template>

<script lang="ts">
import Icon from '@/components/Icon.vue'
import Profesion from '@/components/Profesion.vue'
import Profesions from '@/store/Profesions'

export default {
  components: {
    Icon,
    Profesion    
  },
  data () {
    return {
      readMore: false,
      items: Profesions.items      
    }
  }  
}
</script>


