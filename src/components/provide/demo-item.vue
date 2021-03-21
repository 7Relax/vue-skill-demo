<template>
  <div class="pt-5">
    <div class="card">
      <div class="card-body">
        {{title}}
      </div>
    </div>
    <button type="button" class="btn btn-primary"
      @click="clickEvent">子组件按钮</button>
      
    <button class="alert alert-success" @click="showHide(true)">
      显示消息提示
    </button>
    <button class="alert alert-danger" @click="showHide(false)">
      隐藏消息提示
    </button>
  </div>
</template>

<script>
  export default {
    // 子组件中可以获取父组件向子组件暴露的属性、方法
    inject: ['title', 'rename', 'show', 'showHide'],
    methods: {
      clickEvent() {
        // 直接触发父组件的方法，修改父组件中的属性title，
        // 但这个title不会响应到子组件，只是“一次性的”
        this.rename('我是子组件派来修改你的')
      }
    }
  }
</script>

<style>
</style>
