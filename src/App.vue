<template>
  <div id="app" class="container p-5">
    <!-- $refs、$parent、$children 案例 -->
    <!-- <demo-ref></demo-ref> -->
    
    <!-- 全局消息提示 -->
    <div class="alert alert-primary" v-show="show">全局消息提示</div>
    
    <!-- provide 案例 -->
    <demo-provide></demo-provide>
    
  </div>
</template>

<script>
// import demoRef from '@/components/ref-parent-children/demo.vue'
import demoProvide from '@/components/provide/demo.vue'
export default {
  name: 'App',
  components: {
    // demoRef,
    demoProvide
  },
  provide() {
    return {
      show: this.show,
      showHide: this.showHide
    }
  },
  data() {
    return {
      show: false
    }
  },
  methods: {
    showHide(val) {
      this.show = val
    }
  }
}
</script>

<style>
</style>
