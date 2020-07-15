<template>
  <div class="sidebar">
      <button @click="addItem('Image')">Add img</button>
      <button @click="addItem('Headline')">Add headline</button>
      <button @click="addItem('Paragraph')">Add paragraph</button>
      <button @click="addItem('Button')">Add button</button>
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
  .sidebar{
    display: flex;
    flex-direction: column;
  }
</style>