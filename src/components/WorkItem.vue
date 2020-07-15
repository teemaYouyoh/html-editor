<template>
  <div class="item">
    <div class="item-block" @click="isEdit = !isEdit">
      <span>{{item.type}}</span>
    </div>

    <div class="edit-panel" v-if="isEdit">
      <input v-model="text" @change="changeItem" type="text">
      <button v-on:click="deleteItem(item.id)">delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WorkItem',
  props: ['item'],
  data: () => {
    return {
      text: '',
      isEdit: false,
    }
  },
  mounted() {
    this.text = this.item.text;
  },
  methods: {
    deleteItem(id) {
      this.$emit('deleteItem', id);
    },
    changeItem() {
      this.$emit('changeItem', {
        id: this.item.id, 
        text: this.text
      });
    },
  },
}
</script>

<style>
</style>
