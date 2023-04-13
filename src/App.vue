<template>
  <div>
    <h2>{{ header || 'Welcome' }}</h2>
    <div>
      <input type="text" placeholder="Add Item" v-model="newItem">
      <button @click="addItem">Submit</button>
    </div>
    <div><span style="color:red"> {{ newItem }} </span></div>
    <ul v-for="item in items" :key="item.id">
      <li>
        <input type="checkbox" >
        {{ item.name }}
        <button @click="removeItem(item)">X</button>
      </li>
    </ul>
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
      newItem: '',
      completedItem: false,
      items: [
        {id:id++, name: 'Maize Flour',completed: false},
        {id:id++, name: 'Nduma', completed: false},
        {id:id++, name: 'New Laptop', completed: false},
        {id:id++, name: 'Baby Cloths', completed:false},
      ]
    }
  },
  methods: {
    addItem(){
      this.items.push({id: id++, name: this.newItem})
      this.newItem=''
    },
    removeItem(item){
      this.items=this.items.filter((t) => t != item)
    },
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
