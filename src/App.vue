<template>
  <div id="app">
    <Toolbar v-on:add="addItem($event)"/>
    <WorkArea :items="items" @deleteItem="deleteItem($event)" @changeItem="changeItem($event)"/>
    <ResultArea :items="items"/>
  </div>
</template>

<script>
import WorkArea from './components/WorkArea.vue'
import Toolbar from './components/Toolbar.vue'
import ResultArea from './components/ResultArea.vue'

export default {
  name: 'App',
  components: {
    WorkArea,
    Toolbar,
    ResultArea,
  },
  data: function() {
    return {
      items: [],
    }
  },
  methods: {
    addItem: function(type) {
      this.items.push({
        type: type,
        id: Math.random(),
        text: type,
      });
    },
    deleteItem(id) {
      this.items.forEach((element, index) => {
        if (element.id === id) {
          this.items.splice(index ,1);
        }
      });
    },
    changeItem(data) {
      this.items.forEach((element) => {
        if (element.id === data.id) {
          element.text = data.text;
          console.log(element.text);
        }
      });
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

  display: flex;
  flex-direction: row;
  justify-content: space-around;
}


  .item {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
