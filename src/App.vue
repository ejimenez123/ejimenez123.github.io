<template> 
  <div class="container mx-auto lg:py-16">
    <div class="max-w-6xl flex items-center h-auto lg:h-screen flex-wrap mx-auto my-32 lg:my-0">
      <Resume />
      <Card />
    </div>
  </div>
</template>

<script lang="ts">
import Card from '@/components/Card.vue'
import Resume from '@/components/Resume.vue'

export default {
  name: 'App',
  components: {
    Card,   
    Resume    
  }
}
</script>

<style>

</style>
