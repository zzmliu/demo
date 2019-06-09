<template>
  <div class="view-wrapper">
    <cube-recycle-list class="list" :size="size" :on-fetch="onFetch" :offset="offset">
      <template slot="item" slot-scope="{ data }">
        <div class="card clearfix">
          <div class="card-left"><img src="http://img5.imgtn.bdimg.com/it/u=1431679950,894096947&fm=26&gp=0.jpg" class="card-left-img" alt=""></div>
          <div class="card-right">
            <p>酒店名称：321321</p>
            <p>酒店地址：321321</p>
            <p>酒店电话：321321</p>
          </div>
        </div>
      </template>
    </cube-recycle-list>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        size: 50,
        offset: 100
      }
    },
    methods: {
      onFetch() {
        let items = []
        return new Promise((resolve) => {
          // 模拟请求 50 条数据，因为 size 设置为 50
          setTimeout(() => {
            for (let i = 0; i < 50; i++) {
              items.push({
                id: i,
                avatar: 'https://s3.amazonaws.com/uifaces/faces/twitter/danpliego/128.jpg',
                msg: '123',
                time: 'Thu Oct 25 2018 15:02:12 GMT+0800 (中国标准时间)'
              })
            }
            resolve(items)
          }, 1000)
        })
      },
      handleClick(data) {
        console.log('Item:' + data)
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped="less">
  .view-wrapper{
    position: fixed;
    top: 54px;
    left: 0;
    bottom: 0;
    width: 100%;
  }
  .card{
    padding: 10px;
  }
  　.clearfix:after{

    　　　　　　content:"";//设置内容为空

  　　　　　　height:0;//高度为0

  　　　　　　line-height:0;//行高为0

  　　　　　　display:block;//将文本转为块级元素

  　　　　　　visibility:hidden;//将元素隐藏

  　　　　　　clear:both//清除浮动

  　　　　　}
.card-left{
  width: 30%;
  float: left
}
.card-left-img{
  width: 100%;
}
  .card-right{
    width: 70%;
    float: right;
  }
</style>
