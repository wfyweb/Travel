<template>
  <div>
    <div>{{value}}</div>
    我是子组件
    <input type="text" @input="handle" :value="value">
  </div>
</template>

<script>
export default {
  name: 'TestComInp',
  props: ['value'],
  methods: {
    handle (e) {
      this.$emit('handelCom', e.target.value)
    }
  }
}
</script>
<style scope>
  input {
    border: 1px solid #999;
    margin: 20px;
  }
</style>
