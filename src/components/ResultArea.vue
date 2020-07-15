<template>
  <div class="result">
    <div v-for="(item, index) in items" v-bind:key="index">
        <ResultItem :item="item" @deleteItem='deleteItem($event)'/>
    </div>
  </div>
</template>


<script>
import ResultItem from './ResultItem.vue';

export default {
  name: 'HelloWorld',
  components: {
    ResultItem,
  },
  props: ['items'],
  methods: {
    deleteItem(id) {
      this.$emit('deleteItem', id);
    }
  },
  mounted() {
  }
}
</script>

<style scoped>
</style>
