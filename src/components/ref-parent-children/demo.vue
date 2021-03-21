<template>
  <div>
    <!-- 
     $ref、$parent、$children 在跨级通信时是有弊端的，
     当组件A和组件B中间隔了数代（甚至不确定具体级别）时，
     以往会借助 Vuex 这样的解决方案，不得不引入三方库来支持。
     本节课则介绍一种无依赖的组件通信方法：Vue.js 内置的 provide / inject 接口 -->
    
    <!-- 获取普通元素 -->
    <!-- <input type="text" class="" ref="ref-input" /> -->
    
    <!-- 获取列表 -->
    <!-- <ul class="list-group">
      <li class="list-group-item" 
        v-for="(item, index) in list" ref="list" :key="index">
        {{ item }}
      </li>
    </ul> -->
    
    <!-- 获取组件 -->
    <!-- <demoItem ref="demo-item"></demoItem> -->
    
    <!-- $children -->
    <!-- <demoItem></demoItem>
    <demoItem></demoItem>
    <demoItem></demoItem>
    <demoItem></demoItem> -->
    
    <!--  -->
    <h2 class="text-center">{{ header }}</h2>
    <demoItem></demoItem>
    
  </div>
</template>

<script>
  import demoItem from './demo-item.vue'
  export default {
    components: {
      demoItem
    },
    data() {
      return {
        list: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
        header: '我是父组件标题'
      }
    },
    // 页面渲染完毕
    mounted() {
      // 获取input
      // console.log(this.$refs['ref-input'])
      // 修改样式
      // this.$refs['ref-input'].style.borderColor = 'red'
      // 获取焦点
      // this.$refs['ref-input'].focus()
      
      // 获取列表
      // console.log(this.$refs.list)
      // 修改背景颜色（动态背景颜色）
      // this.$refs.list.forEach(li => {
      //   li.style.backgroundColor = '#' + Math.floor(Math.random() * 1000000)
      // })
      
      // 获取子组件
      // 调用子组件中的 focus() 方法
      // this.$refs['demo-item'].focus()
      // 父组件修改子组件中的值
      // this.$refs['demo-item'].renameHeader('父组件修改子组件中的值1')
      // this.$refs['demo-item'].content = '父组件修改子组件中的值2'
      
      // $children - 可以拿到父组件中所有的子组件，是一个数组
      // console.log(this.$children[0].renameHeader('修改第1个子组件的值'))
      // console.log(this.$children[2].renameHeader('修改第3个子组件的值'))
    },
    methods: {
      changeName(data) {
        this.header = data
      }
    }
  }
</script>

<style>
</style>
