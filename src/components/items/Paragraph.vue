<template>
  <div class="item">
    <p class="paragraph" @click="isEdit = !isEdit">
      {{text}}
    </p>

    <div class="edit-panel" v-if="isEdit">
      <input v-model="text" type="text">
      <button v-on:click="deleteItem(item.id)">delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Paragraph',
  props: ['item'],
  data: () => {
    return {
      text: "Hello",
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
.paragraph{
  position: static;
width: 568px;
height: 84px;
left: 30px;
top: 353px;
  font-family: Roboto;
font-style: normal;
font-weight: normal;
font-size: 14px;
line-height: 150%;

/* or 21px */
text-align: center;
letter-spacing: 0.02em;

/* Blue-Grey */
color: #97AACD;

/* Inside Auto Layout */
flex: none;
order: 2;
margin: 0px 30px;
}
</style>
