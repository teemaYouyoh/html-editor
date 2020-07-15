<template>
  <div class="div">
    <div class="result_area">
      <div v-for="(item, index) in items" v-bind:key="index">
          <WorkItem :item="item" @deleteItem="deleteItem($event)"  @changeItem="changeItem($event)"/>
      </div>
    </div>
    <!-- <div class="result_area">
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
      </div> -->
  <!-- </div> -->
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
.result_area{
  display: flex;
flex-direction: column;
padding: 30px;

position: absolute;
width: 568px;
height: 709px;
left: 542px;
top: 69px;

background: #FFFFFF;
}
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