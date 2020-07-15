<template>
  <div class="item">
    <h1 class="headline" @click="isEdit = !isEdit">
      {{title}}
    </h1>

    <div class="edit-panel" v-if="isEdit">
      <input v-model="title" type="text">
      <button v-on:click="deleteItem(item.id)">delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Headline',
  props: ['item'],
  data: () => {
    return {
      title: "Hello",
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
.headline{
  font-family: Roboto;
font-style: normal;
font-weight: bold;
font-size: 22px;
line-height: 150%;

/* identical to box height, or 33px */
letter-spacing: 0.02em;

/* Dark */
color: #252A32;

/* Inside Auto Layout */
flex: none;
order: 1;
align-self: center;
margin: 0px 30px
}
</style>
