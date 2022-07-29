<template>
<div class="">
  <div class="pt-4 text-base font-bold flex border-b-2 border-red-200">
    <icon name="baggage" /> Books
    </div>
  <div class="p-4 text-base flex items-center text-justify">
    <p>Por aquí les dejo el enlace a mis dos libros publicados.
      <button class="bg-blue-200 text-red-300 px-3 rounded" @click="readMore =! readMore">
        <span v-if="readMore">Leer -</span>
        <span v-else>Leer +</span>
      </button>   
    </p>
  </div>
  <div v-if="readMore">
    <Book
      v-for="(item, index) in items"
      :key="index"
      :n="index"
      :data="item"/>
  </div>  
</div>
</template>

<script>
import Icon from '@/components/Icon.vue'
import Book from '@/components/Book.vue'
import Books from '@/store/Books'

export default {
  components: {
    Icon,
    Book    
  },
  data () {
    return {
      readMore: false,
      items: Books.items      
    }
  }  
}
</script>

<style scoped></style>

