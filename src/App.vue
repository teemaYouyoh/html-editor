<template>
  <div id="app">
    <LeftSidebar v-on:add="addItem($event)"/>
    <WorkArea :componentsArr="componentsArr" @deleteItem="deleteItem($event)"/>
  </div>
</template>

<script>
import WorkArea from './components/WorkArea.vue'
import LeftSidebar from './components/LeftSidebar.vue'

export default {
  name: 'App',
  components: {
    WorkArea,
    LeftSidebar,
  },
  data: function() {
    return {
      componentsArr: [],
    }
  },
  methods: {
    addItem: function(type) {
      this.componentsArr.push({
        type: type,
        id: Math.random(),
        text: '',
      });
    },
    deleteItem(id) {
      this.componentsArr.forEach((element, index) => {
        if (element.id === id) {
          this.componentsArr.splice(index ,1);
        }
      });
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
