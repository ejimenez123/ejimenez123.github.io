<template> 
  <div class="flex border-b-2 border-red-200">
    <div class="w-full p-6 text-left">
      <a
        class="font-normal underline text-blue-600 hover:text-blue-800 visited:text-purple-600"
        :href="data.h"
        target="_blank">
          {{ data.k }}
      </a>
      {{ data.v1 }}
      <Transition>
        <span v-if="readMore">{{ data.v2 }}</span>
        <span v-else> ... </span>       
      </Transition>
      <button class="bg-stone-700 hover:bg-stone-600 px-3 rounded" @click="readMore =! readMore">
        <span v-if="readMore">Leer -</span>
        <span v-else>Leer +</span>
      </button>
    </div>
 </div>
</template>

<script lang="ts">

export default {
  props: {
    data: Object,
    n: Number
  },
  data () {
    return {
      readMore: false
    }
  } 
}
</script>

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
