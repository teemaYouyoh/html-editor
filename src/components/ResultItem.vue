<template>
  <div class="item">
    <div class="item-block" @click="isEdit = !isEdit">
      <img
        v-if="item.type === 'Image'"
        :src="item.text"
        :alt="item.type"
      >
  
      <h1 v-if="item.type === 'Headline'">
        {{item.text}}
      </h1>
  
      <p v-if="item.type === 'Paragraph'">
        {{item.text}}
      </p>
  
      <button v-if="item.type === 'Button'">
        {{item.text}}
      </button>
    </div>

    <div class="edit-panel" v-if="isEdit">
      <input v-model="text" type="text">
      <button v-on:click="deleteItem(item.id)">delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Item',
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
</style>
