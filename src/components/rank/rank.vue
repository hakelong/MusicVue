<template>
<div class='rank'>
  <div id='chart' style="width:500px; height:500px"></div>
</div>
</template>
<script>
// import {echarts,bar,tooltip,title} from 'echarts'
var echarts = require('echarts/lib/echarts');
// 引入柱状图
require('echarts/lib/chart/bar');
// 引入提示框和标题组件
require('echarts/lib/component/tooltip');
require('echarts/lib/component/title');
export default{
  data(){
    return{
      myChart:{}
    }
  },
  mounted(){
    let arr=[1,2,'2',2,2,3,4,'ds']
    let obj={}
    let n=[]
    for(let i=0;i<arr.length;i++){
      if(!obj[arr[i]]){
        console.log('ss')
        n.push(arr[i])
        obj[arr[i]]=1
      }
    }
    console.log(n)
    setTimeout(()=>{
      this.init()
      setTimeout(()=>{
        this.myChart.setOption({
          xAxis:{
            data:['a','b','c','d','e']
          },
          series:[{
            data:[100,90,80,70,60]
          }]
        })
      },1000)
    },20)
  },
  methods:{
    init(){
      // console.log(this.myChart)
      this.myChart=echarts.init(document.querySelector('#chart'))
        this.myChart.setOption({
          baseOption:{
            title: {
                text: 'ECharts 入门示例'
            },
            tooltip: {},
            xAxis: {
                data: []
            },
            yAxis: {},
            series: [{
                name: '销量',
                type: 'bar',
                data: []
            }]
          },
          media: [ // 这里定义了 media query 的逐条规则。
              {
                  query: {
                      maxWidth: 500               // 当容器宽度小于 500 时。
                  },
                  option: {
                      legend: {
                          right: 10,              // legend 放置在右侧中间。
                          top: '15%',
                          orient: 'vertical'      // 纵向布局。
                      },
                      series: [                   // 两个饼图上下布局。
                          {
                              radius: [20, '50%'],
                              center: ['50%', '30%']
                          }
                      ]
                  }
              },
          ]

        })
    }
  }
}
</script>
<style lang='stylus' scoped >
  .rank{
    position fixed
    top 88px
    bottom 0
    width 100%
  }

</style>
