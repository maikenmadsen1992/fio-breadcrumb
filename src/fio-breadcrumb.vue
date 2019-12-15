<template>
  <div id="breadcrumb-container">
    <div class="breadcrumb-item-container" v-for="(item, index) in dateItemsList" v-bind:key="index">
        <span @click="breadcrumbItemClicked(item)" class="breadcrumb-text"> {{item.text}} </span>
        <span>
            <font-awesome-icon v-bind:class="{last : index === (dateItemsList.length-1)}" :icon="breadcrumbIcon" />
        </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'fio-breadcrumb',
  props: ['items', 'icon'],

  data () {
    return {
      dateItemsList: [],
      breadcrumbIcon: ''
    }
  },
  watch: {
    items: function () {
        this.dateItemsList =  this.$props.items  
    }
  },

  created () {
    this.dateItemsList =  this.$props.items
    this.breadcrumbIcon = this.$props.icon
  },
  
  methods: {
    breadcrumbItemClicked: function (item) {
      this.$emit('breadcrumbItemClicked', item)
    }
  }
}
</script>

<style scoped>
#breadcrumb-container {
    display: grid;
    grid-template-columns: repeat(auto-fill,minmax(120px, 1fr));
}

.breadcrumb-item-container {
    align-self: center;
}

.breadcrumb-text {
    font-family: inherit;
    margin: 0px 10px 0px 10px;
    cursor: pointer;
}

.last {
    display: none;
}


</style>