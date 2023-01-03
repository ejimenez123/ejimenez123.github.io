<template>
<div class="">
  <div class="pt-4 text-base font-bold flex border-b-2 border-red-200">
    <icon name="baggage" /> Repositories
    <button class="bg-stone-700 hover:bg-stone-600 px-3 rounded" @click="readMore1 =! readMore1">
        <span v-if="readMore1">Leer -</span>
        <span v-else>Leer +</span>
      </button>
    </div>    
  <div v-if="readMore1">
  <Repository
    v-for="(item, index) in items"
    :key="index"
    :n="index"
    :data="item"/>
</div>
</div>
</template>

<script lang="ts">
import Icon from '@/components/Icon.vue'
import Repository from '@/components/Repository.vue'

export default {
  components: {
    Icon,
    Repository    
  },
  data () {
    return {      
      readMore1: false,
      items: [{
        k: 'Code Pen',
        h: 'https://codepen.io/ejimenez123/'
      },{
        k: 'Code Wars',
        h: 'https://www.codewars.com/users/ejimenez123'
      },{
        k: 'CaribesTIC Desarrollo Web',
        h: 'https://caribestic.github.io/'
      },{
        k: 'Git Hub',
        h: 'https://github.com/ejimenez123'
      },{
        k: 'Git Lab',
        h: 'https://gitlab.com/fdsoil'
      },{
        k: 'Stack Overflow',
        h: 'https://stackoverflow.com/users/16601080/'
      }]
    }
  }  
}
</script>

<style scoped></style>

