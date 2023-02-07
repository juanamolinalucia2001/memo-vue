<template>
  <div class="home">

    <Playfield :pairs="6" />
    
  </div>
</template>

<script>
// @ is an alias to /src
import Playfield from '@/components/Playfield.vue'

export default {
  name: 'HomeView',
  components: {
    Playfield
  }
}
</script>
