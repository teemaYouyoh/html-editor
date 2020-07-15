<template>
  <div class="item">
    <button @click="isEdit = !isEdit">
      {{text}}
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
</style>
