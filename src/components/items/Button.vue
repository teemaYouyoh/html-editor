<template>
  <div class="item">
    <button class="button" @click="isEdit = !isEdit">
      <span class="button_label">{{text}}</span>
    </button>

    <div class="edit-panel" v-if="isEdit">
      <input v-model="text" type="text">
      <button v-on:click="deleteItem(item.id)">delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Btn',
  props: ['item'],
  data: () => {
    return {
      text: "Button",
      isEdit: false,
    }
  },
  methods: {
    deleteItem(id) {
      this.$emit('deleteItem', id);
    }
  }
}
</script>

<style>
.button{
  display: flex;
  justify-content: center;
flex-direction: row;
padding: 10px 30px;

position: static;
width: 145px;
height: 40px;
left: 241.5px;
top: 467px;

/* Primary */
background: #4368E0;
border-radius: 4px;

/* Inside Auto Layout */
flex: none;
order: 3;
align-self: center;
margin: 0px 30px
}

.button_label{
  position: static;
left: 20.69%;
right: 20.69%;
top: 25%;
bottom: 25%;

font-family: Roboto;
font-style: normal;
font-weight: 500;
font-size: 14px;
line-height: 145%;

/* or 20px */
display: flex;
justify-content: center;
align-items: flex-end;
text-align: center;
letter-spacing: 0.02em;

/* Blue 100 */
color: #F6F9FE;

/* Inside Auto Layout */
flex: none;
order: 1;
align-self: center;
margin: 10px 0px;
text-align: center;
}
</style>
