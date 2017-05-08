<template>
  <!-- use component tag and simple router system with :is directive -->
  <component :is="current_view"></component>
</template>
<script>
  import library from './library.vue';
  import reader from './reader.vue';
  import vocabList from './vocabList.vue';
  import eventBus from './../eventBus.js';

  export default {
    data() {
      return {
        currentView: 'vocabList',
      };
    },
    components: {
      library,
      reader,
      vocabList,
    },
    computed: {
      current_view() {
        return this.currentView;
      },
    },
    mounted() {
      const that = this;
      eventBus.$on('changePage', (page) => {
        that.currentView = page;
        console.log('Event received: ' + page);
      });
    },
  };
</script>
