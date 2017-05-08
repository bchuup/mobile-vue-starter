<template>
  <!-- use component tag and simple router system with :is directive -->
  <v-ons-page>
    <v-ons-toolbar>
      <div class="center">
        <v-ons-button @click="goTo('library')">Library</v-ons-button>
        <v-ons-button @click="goTo('reader')">Reader</v-ons-button>
        <v-ons-button @click="goTo('vocabList')">Vocabulary</v-ons-button>
      </div>
      <div class="right">
        <v-ons-toolbar-button>
          <v-ons-icon icon="ion-navicon, material: md-menu"></v-ons-icon>
        </v-ons-toolbar-button>
      </div>
    </v-ons-toolbar>
    <div style="text-align: center; padding-top:10px">VOCAB LIST</div>
    <p style="text-align: center">
      <!-- <v-ons-button @click="alert">Click Me!</v-ons-button> -->
    </p>
  </v-ons-page>
</template>
<script>
  import eventBus from './../eventBus.js';

  export default {
    data() {
      return {
        title: 'My app'
      };
    },
    methods: {
      goTo(page) {
        eventBus.$emit('changePage', page);
        // this.$ons.notification.alert(`go to ${page}`);
      },
    },
  };
</script>
