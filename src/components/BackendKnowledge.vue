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

<template> 
  <div class="flex" :class="n % 2 === 0 ? 'bgClass1' : 'bgClassResume'">
    <div class="w-1/4 p-2 text-left text-sm">
      <a
        class="font-normal underline text-blue-600 hover:text-blue-800 visited:text-purple-600"
        :href="data.h"
        target="_blank">
          {{ data.k }}
      </a>
    </div>
    <div class="w-1/2 p-2 text-base text-left">
      {{ data.v1 }}
      <Transition>
      <span v-if="readMore">{{ data.v2 }}</span><span v-else>...</span>
      </Transition>
    </div>
    <div class="w-1/4 p-2">
      <button class="bg-stone-700 hover:bg-stone-600 px-3 rounded" @click="readMore =! readMore">
        <Transition>
        <span v-if="readMore">Leer -</span>
        <span v-else>Leer +</span>
        </Transition>
      </button>
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
