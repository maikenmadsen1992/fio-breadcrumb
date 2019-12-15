<template>
  <div id="app">
    <breadcrumb :items="dataitems" :icon="icon" v-on:breadcrumbItemClicked="itemIsClicked"/>
    <button v-on:click="addToBreadCrumb()">Add to breadcrumb</button>
  </div>
</template>

<script>
import breadcrumb from './fio-breadcrumb.vue'

export default {
  name: 'app',
  components: {
    breadcrumb
  },
  data () {
    return {
      /* Parse either: arrow-right or chevron-right for dividers */
      icon: 'arrow-right',
      dataitems: [
        {'text': 'Category1', 'value': 'if you want to parse some more information'},
        {'text': 'Category2', 'value': 'if you want to parse some more information'},
        {'text': 'Category3', 'value': 'if you want to parse some more information'},
        {'text': 'Category4', 'value': 'if you want to parse some more information'}
      ],
      countForTest: 4
    }
  },

  methods: {
    itemIsClicked: function (item) {
      console.log('breadcrumb item have been pressed ' + JSON.stringify(item));
    },

    addToBreadCrumb: function () {
      let counter = this.countForTest;
      let newCount = counter + 1;
      this.countForTest = newCount;

      let newText = 'Category' + this.countForTest; 

      this.dataitems.push({'text': newText, 'value': 'if you want to parse some more information'})

    }
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  margin-top: 200px;
}
</style>
