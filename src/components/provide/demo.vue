<template>
  <div>
    <h1>{{title}}</h1>
    <demo-item></demo-item>
    
    <!-- <button class="alert alert-success" @click="showHide(true)">
      显示消息提示
    </button>
    <button class="alert alert-danger" @click="showHide(false)">
      隐藏消息提示
    </button> -->
  </div>
</template>

<script>
  import demoItem from './demo-item.vue'
  export default {
    components: {
      demoItem
    },
    inject: ['show', 'showHide'],
    // 向子组件暴露一个title属性、rename方法
    provide() {
      return {
         title: this.title,
         rename: this.rename
      }
    },
    data() {
      return {
        title: '我是父组件的标题'
      }
    },
    methods: {
      rename(val) {
        this.title = val
      }
    }
  }
</script>

<style>
</style>
