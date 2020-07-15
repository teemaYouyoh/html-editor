<template>
  <div class="div">
    <div v-for="(item, index) in items" v-bind:key="index">
        <WorkItem :item="item" @deleteItem="deleteItem($event)"  @changeItem="changeItem($event)"/>
    </div>
  </div>
</template>


<script>
import WorkItem from './WorkItem.vue';

export default {
  name: 'WorkArea',
  components: {
    WorkItem,
  },
  props: ['items'],
  methods: {
    deleteItem(id) {
      this.$emit('deleteItem', id);
    },
    changeItem(data) {
      this.$emit('changeItem', data);
    },
  },
  mounted() {
  }
}
</script>

<style scoped>
</style>

<!-- <Img 
          v-if="item.type === 'Image'"
          :item="item"
          @deleteItem='deleteItem($event)'
        />
        <Headline 
          v-if="item.type === 'Headline'"
          :item="item"
          @deleteItem='deleteItem($event)'
        />
        <Paragraph
          v-if="item.type === 'Paragraph'"
          :item="item"
          @deleteItem='deleteItem($event)'
        />
        <Btn
          v-if="item.type === 'Button'"
          :item="item"
          @deleteItem='deleteItem($event)'
        /> -->