<template>
  <div id="app">
    <Header />
    <div class="devider"></div>
    <LeftSidebar v-on:add="addItem($event)"/>
    <div class="mainArea">
      <div class="subHeader">
      <WorkArea :componentsArr="componentsArr" @deleteItem="deleteItem($event)"/>

      </div>
  </div>
  </div>
</template>

<script>
import WorkArea from './components/WorkArea.vue'
import LeftSidebar from './components/LeftSidebar.vue'
import Header from './components/Header';
export default {
  name: 'App',
  components: {
    WorkArea,
    LeftSidebar,
    Header
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
.mainArea{
  position: absolute;
left: 270px;
right: 0px;
top: 70px;
bottom: 0px;

/* Grey 100 */
background: #F5F5FC;
}

.subHeader{
  position: absolute;
width: 1170px;
height: 70px;
left: 0px;

/* White */
background: #FFFFFF;
box-shadow: 0px 5px 10px rgba(37, 42, 50, 0.1);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
  max-width: 1440px;
  width: 100%;
  box-sizing: border-box;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
*{
  margin: 0;
  padding: 0;
}

.devider{
  position: absolute;
  width: 1359px;
  height: 1px;
  left: 0px;
  top: 69px;

/* Grey 300 */
background: #E4E6F1;
}

h1,h2,h3,h4,h5,h6{
  margin: 0;
  padding: 0;
}

  .item {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
