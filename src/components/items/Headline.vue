<template>
  <div class="item">
    <h1 @click="isEdit = !isEdit">
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
</style>
