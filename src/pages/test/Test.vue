<template>
  <div>
    我是组件
    <input type="text" v-model="valueCom"  @handelCom = "handelCom" />
    <test-com-inp v-model="valueCom" @handelCom = "handelCom"></test-com-inp>
  </div>
</template>
<script>
import TestComInp from './components/ComInp'
export default {
  name: 'Test',
  components: {
    TestComInp
  },
  data () {
    return {
      valueCom: ''
    }
  },
  methods: {
    handelCom (e) {
      this.valueCom = e
    },
    changeValue (e) {
      console.log(e.target.value)
      this.valueCom = e.target.value
    }
  }

}
</script>

<style>

</style>
