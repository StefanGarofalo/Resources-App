<template>
  <ul>
    <ResourceItem v-for="resource in resources" :key="resource.id" v-bind="resource" 
    @delete-resource="deleteResource"/>
  </ul>
</template>

<script>
import ResourceItem from './ResourceItem'
export default {
  components: { ResourceItem },
  data(){
    return{
      resources: [
        { 
          title: 'official-guide', id: 'official-guide', 
          description: 'official Vuejs docs', link: 'https://vuejs.org' 
        },
        { 
          title: 'google', id: 'google', 
          description: 'learn to google', link: 'https://google.org' 
        }
      ]
    }
  },
  methods: {
    deleteResource(id){
      this.resources = this.resources.filter(resource => resource.id !== id)
    }
  }
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>