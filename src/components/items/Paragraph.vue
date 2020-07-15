<template>
  <div class="item">
    <p @click="isEdit = !isEdit">
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
</style>
