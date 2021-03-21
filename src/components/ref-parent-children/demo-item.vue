<template>
  <div>
    <h3>{{header}}</h3>
    <input type="text" class="form-control" 
      v-model="content" ref="input" 
      @input="changeInput" />
  </div>
</template>

<script>
  export default {
    data() {
      return {
        header: '我是子组件标题',
        content: '子组件的内容'
      }
    },
    methods: {
      focus() {
        this.$refs.input.focus()
      },
      renameHeader(value) {
        this.header = value
      },
      changeInput(e) {
        // this.$parent.header = e.target.value
        this.$parent.changeName(e.target.value)
      }
    }
  }
</script>

<style>
</style>
