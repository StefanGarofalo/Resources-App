<template>
  <li>
    <BaseCard>
      <header>
        <h3>{{ title }}</h3>
        <BaseButton type="button" mode="flat" @click="deleteResourceCall(this.id)">Delete</BaseButton>
      </header>
      <p>{{ description }}</p>
      <nav>
        <a :href="link">Follow Resource</a>
      </nav>
    </BaseCard>
  </li>
</template>

<script>
import BaseButton from '../UI/BaseButton.vue';

export default{
  components: { BaseButton },
  emits: {
    'delete-resource': function(id){
      if(!id){
        console.warn('no id')
        return false
      }
      return true
    }
  },
  props: {
    title: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    link: {
      type: String,
      required: true
    }
  },
  methods: {
    deleteResourceCall(id){
      this.$emit('delete-resource', id)
    }
  }
}
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h3 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
}

p {
  margin: 0.5rem 0;
}

a {
  text-decoration: none;
  color: #ce5c00;
}

a:hover,
a:active {
  color: #c89300;
}
</style>
