<template>
  <div class="home">
    
    <NavBar />

    <div class="banniere">
       <img src="src/assets/static/img/mink-mingle-HRyjETL87Gg-unsplash.jpg">
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import NavBar from '@/components/NavBar.vue'

export default {
  name: 'HomeView',
  components: {
    NavBar
  }
}
</script>
