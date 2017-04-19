<template>
  <div class="dashboard">
    <md-toolbar>
      <h1 class="md-title">{{ title }}</h1>
    </md-toolbar>
    
    <div class="main-content">
        <grid-layout
            :layout="layout"
            :col-num="12"
            :row-height="30"
            :is-draggable="true"
            :is-resizable="true"
            :vertical-compact="true"
            :margin="[10, 10]"
            :use-css-transforms="true"
        >

          <grid-item v-for="item in layout"
                   :x="item.x"
                   :y="item.y"
                   :w="item.w"
                   :h="item.h"
                   :i="item.i">
            {{item.i}}
        </grid-item>
        </grid-layout>
    </div>

  </div>
</template>

<style scoped>
    .main-content{
      padding: 0 10px;
      margin-top: 20px;
    }

    .vue-grid-item{
      background-color: green;
    }
</style>



<script>

import VueGridLayout from 'vue-grid-layout'

export default {

  name: 'Dashboard',
  components: {
    GridLayout: VueGridLayout.GridLayout,
    GridItem: VueGridLayout.GridItem
  },
  data () {
    return {
      title: 'Dashboard',
      layout: [
        {
          'x': 0,
          'y': 0,
          'w': 2,
          'h': 2,
          'i': '0'
        },
        {
          'x': 2,
          'y': 0,
          'w': 2,
          'h': 2,
          'i': '1'
        }
      ]
    }
  }
}
</script>
