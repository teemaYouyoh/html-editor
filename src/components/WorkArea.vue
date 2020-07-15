<template>
  <div class="div">
    <div v-for="(item, index) in componentsArr" v-bind:key="index">
        <Img 
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
        />
    </div>
  </div>
</template>


<script>
import Img from './items/Image.vue'
import Headline from './items/Headline.vue'
import Paragraph from './items/Paragraph.vue'
import Btn from './items/Button.vue'


export default {
  name: 'HelloWorld',
  components: {
    Img,
    Headline,
    Paragraph,
    Btn,
  },
  props: {
    componentsArr: Array,
  },
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
