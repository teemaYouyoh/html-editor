<template>
  <div class="item">
    <img
    :src="src"
    :alt="item.type"
    @click="isEdit = !isEdit"
    >
    <div class="edit-panel" v-if="isEdit">
      <input v-model="src" type="text">
      <button v-on:click="deleteItem(item.id)">delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Img',
  props: ['item'],
  data: () => {
    return {
      src: "https://ru.vuejs.org/images/components.png",
      isEdit: false,
    }
  },
  mounted() {
    this.item.text !== '' ? this.src = this.item.text : false;
  },
  methods: {
    deleteItem(id) {
      this.$emit('deleteItem', id);
    }
  }
}
</script>

<style>
  img { 
    width: 400px;
  }

</style>
