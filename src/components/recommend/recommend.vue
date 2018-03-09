<template>
<div>
  <Slider></Slider>
</div>
</template>
<script>
import {getRecommend} from '@/api/recommend'
import {ERR_OK} from '@/api/config.js'
import Slider from 'base/slider'

export default{
  created(){
    this._getRecommend()
  },
  methods:{
    _getRecommend(){
      getRecommend().then((res)=>{
        console.log(res)
        if(res.code===ERR_OK){
          console.log(res)
        }

      })
    }
  },
  components:{
    Slider
  }
}
</script>

