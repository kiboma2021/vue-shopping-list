<template>
  <div>
    <h2>{{ header || 'Welcome' }}</h2>
    <div>
      <input type="text" placeholder="Add Item">
      <button>Submit</button>
    </div>
    <div v-for="item in items" :key="item.id">
      {{ item.name }}
    </div>
  </div>
</template>

<script>
let id = 0

export default {
  name: 'App',
  components: {},
  data(){
    return {
      header: "April 2022 Shopping",
      items: [
        {id:id++, name: 'Maize Flour'},
        {id:id++, name: 'Nduma'},
        {id:id++, name: 'New Laptop'},
        {id:id++, name: 'Baby Cloths'},
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
