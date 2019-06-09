<template>
  <div class="tabBar">
    <cube-button @click="showCascadePicker"  :primary="true" class="tabBtn">{{this.value}}</cube-button>
  </div>
</template>

<script>
  // import {cube-tab-bar,cube-tab }from 'cube-ui'
  const cascadeData = [
    {
      value: '北京',
      text: '北京',
      children:[{ value: 1, text: '文化古迹' }, { value: 2, text: '酒店旅店' }, { value: 3, text: '星级景区' }]
    },
    {
      value: '上海',
      text: '上海',
      children: [{ value: 1, text: '文化古迹' }, { value: 2, text: '酒店旅店' }, { value: 3, text: '星级景区' }]
    }
  ]
  export default {
  name: 'tabBar',
    data() {
      return {
        value: '请选择地址',
      }
    },
    mounted () {
      this.cascadePicker = this.$createCascadePicker({
        title: 'Cascade Picker',
        data: cascadeData,
        selectedIndex: [0, 1, 0],
        onSelect: this.selectHandle,
        onCancel: this.cancelHandle
      })
    },
    methods: {
      showCascadePicker() {
        this.cascadePicker.show()
      },
      selectHandle(selectedVal, selectedIndex, selectedText) {
        // console.log(selectedText)
        this.value=selectedText[0]+selectedText[1]
        // this.$createDialog({
        //   type: 'warn',
        //   content: `Selected Item: <br/> - value: ${selectedVal.join(', ')} <br/> - index: ${selectedIndex.join(', ')} <br/> - text: ${selectedText.join(' ')}`,
        //   icon: 'cubeic-alert'
        // }).show()
      },
      cancelHandle() {
        this.$createToast({
          type: 'correct',
          txt: 'Picker canceled',
          time: 1000
        }).show()
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .tabBar{
    padding-top: 5px;
    padding-left: 20px;
    box-sizing: border-box;
    height: 50px;
    background:#fc9153;
  }
 .tabBtn{
   width: 99px;
   height: 5px;
   line-height: 1px;
   font-size: 11px;
 }
</style>
