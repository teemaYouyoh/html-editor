<template>
<div class="sidebar_wrapper">

  <div class="sidebar">
    <div class="block_row">
        <button class="buttons_adding" @click="addItem('Headline')">
          <img class="icon" src="./dashboard.png" alt="">
            <span class="label_button"> Headline</span>
        </button>
        <button class="buttons_adding" @click="addItem('Paragraph')">
            <img class="icon" src="./dashboard.png" alt="">
            <span class="label_button">Paragraph</span>
        </button>
    </div>
    <div class="block_row">     
      <button class="buttons_adding" @click="addItem('Button')"><img class="icon" src="./dashboard.png" alt=""><span class="label_button">Button</span></button>
      <button class="buttons_adding" @click="addItem('Image')"><img class="icon" src="./dashboard.png" alt=""><span class="label_button">Image</span></button>
   </div>
  </div>
  
</div>
</template>

<script>
export default {
  methods: {
    addItem(type) {
      this.$emit('add', type);
    }
  }
}
</script>

<style>

.sidebar_wrapper{
  position: absolute;
width: 270px;
height: auto;
left: 0px;
top: 69px;
}
  .sidebar{
display: flex;
flex-direction: column;
padding: 0px;

position: absolute;
width: 210px;
height: 176px;
left: calc(50% - 210px/2);
top: 30px;
  }

  .buttons_adding{
    display: flex;
flex-direction: column;
padding: 15px 10px;

position: static;
width: 100px;
height: 83px;
left: 0px;
top: 0px;
background: #F6F9FE;
border-radius: 6px;
  }

  .icon{
    position: static;
width: 25px;
height: 25px;
left: 37.5px;
top: 15px;
flex: none;
order: 0;
align-self: center;
margin: 0px 10px;
  }

  .label_button{
    position: static;
left: 10%;
right: 10%;
top: 60.24%;
bottom: 18.07%;

/* Small 12 / Regular */
font-family: Roboto;
font-style: normal;
font-weight: normal;
font-size: 12px;
line-height: 150%;

/* identical to box height, or 18px */
display: flex;
align-items: flex-end;
text-align: center;
letter-spacing: 0.02em;

/* Dark */
color: #252A32;

/* Inside Auto Layout */
flex: none;
order: 1;
align-self: center;
margin: 0px 10px;
  }

  .block_row{
    display: flex;
flex-direction: row;
padding: 0px;

position: static;
width: 210px;
height: 83px;
left: 0px;
top: 93px;
  }
</style>