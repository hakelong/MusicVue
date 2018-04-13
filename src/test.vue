<template>
<div class='test'>
  <div class='animate-test' @click='dialogShow'></div>
  <transition name='bounce'>
    <div class='dialog' v-show='flag'>
      welcome to pig world
    </div>
  </transition>
</div>
</template>
<script>
export default{
  props:{

  },
  data(){
    return {
      flag:false
    }
  },
  methods:{
    dialogShow(){
      this.flag=!this.flag
    }
  },
  mounted(){
  }
}
</script>
<style scoped lang='stylus'>
  @keyframes mymove{
    from {top:50px}
    to {top:200px}
  }
  .animate-test
    width 100px
    height 100px
    background-color green
    animation mymove 3s linear
    position absolute

  @keyframes show{
    from {opacity:0}
    to {opacity:1}
  }

  .test
    position fixed
    top 88px
    bottom 0px
    width 100%
    background-color #fff
    color #000
  .dialog
    line-height 100px
    text-align center
    width 200px
    height 100px
    background-color red
    position fixed
    top 0
    bottom 0
    left 0
    right 0
    margin auto
    // animation show 2s ease

    @keyframes bouncein {
       0% {
        transform: scale(0);
      }
      50% {
        transform: scale(1.5);
      }
      100% {
        transform: scale(1);
      }

    }

   .bounce-enter-active{
     animation bouncein .5s
   }
   .bounce-leave-active{
     animation bouncein .5s reverse
   }
</style>

