<template>
  <TheHeader/>
  <StoredResources/>
</template>

<script>
import StoredResources from './components/resources/StoredResources.vue'
import TheHeader from './components/layout/TheHeader.vue';


export default {
  components: { StoredResources, TheHeader },
  
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>