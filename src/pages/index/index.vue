<template>
  <div class="app">
    <ul class="list">
      <li class="list__item" v-for="(item, index) in list" :key="index">
        <a :url="item.link">{{ item.text }}</a>
      </li>
    </ul>

    <div>
      vuex count: {{ $store.state.counter.count }}
    </div>

    <div>
      globalData:{{ globalData }}
    </div>
  </div>
</template>

<script>
import mixin from './mixin.js'

(async function() {
  console.log('111')
})()

export default {
  mixins: [
    mixin
  ],
  data() {
    return {
      globalData:{},
      list: [
        {
          link: '/pages/todomvc/index',
          text: 'TodoMVC',
        },
        {
          link: '/pages/v-html/index',
          text: 'v-html',
        },
        {
          link: '/pages/v-model/index',
          text: 'v-model',
        },
        {
          link: '/pages/vuex/index',
          text: 'vuex',
        },
        {
          link: '/pages/webview/index',
          text: 'web-view',
        },
        {
          link: '/pages/native/index',
          text: '原生自定义组件',
        },
        {
          link: '/pages/img/index',
          text: 'img',
        },
        {
          link: '/packageA/pages/a/index',
          text: 'packageA-a',
        },
        {
          link: '/packageA/pages/todomvc/index',
          text: 'packageA-todomvc',
        },
      ]
    }
  },
  created() {
    var appInstance = getApp()
    this.globalData = appInstance.globalData;
    console.log(this)
  },
  methods: {
    onTouchStart(e) {
      console.log(e)
    }
  }
}
</script>

<style lang="less" scoped>
.list {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: stretch;
  &__item {
    padding: 10px;
    color: blue;
  }
}
</style>
