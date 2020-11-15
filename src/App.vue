<template>
  <div id="app">
    <div class="container">
      <h2>Shopping List</h2>
      <input
        class="input"
        v-model="newItem"
        v-on:keyup.enter="add()"
      />
      <button class="add-button" v-on:click="add()" >Add</button>
      <ul style="list-style-type: none;">
        <li v-for="(item,i) in listItem">
          <span>
            {{i + 1}}. {{item.text}} 
          </span>
          <span>
            <button class="inc" @click="incQt(i)">+</button>
            <span v-if="item.qt > 0">{{item.qt}}</span>
            
            <button class="dec" @click="decQt(todo.qt)">-</button>
          </span>
          <button class="delete-button" @click="deleteItem(i)" >delete</button>
        </li>
      </ul> 
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      newItem: "",
      listItem: [
        {text: "Complete Project", id: 0, qt:1 },
        {text: "Upload to Git", id:1, qt: 1}
      ]
    }
   },
  methods: {
    add() {
      this.listItem.push({
        text: this.newItem,
        id: new Date().valueOf(),
        qt: 1
      }),
      this.newItem = ""
    },
    deleteItem(i) {
      this.listItem.splice(i,1)
    },
    incQt(i) {
      
    },
    decQt(i) {
     
    }
   }
}
</script>

<style>

</style>
