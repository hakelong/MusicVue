<template>
  <div id="app">
    <Mheader></Mheader>
    <Mtab></Mtab>
    <keep-alive>
      <router-view></router-view>
    </keep-alive>
  </div>
</template>

<script type='type/javascript'>
import Mheader from "@/components/m-header/m-header";
import Mtab from "@/components/tab/tab";
export default {
  components:{
    Mheader,
    Mtab
  },
  name: 'App'
}
</script>

<style scoped lang='stylus' >
  @import "common/stylus/variable.styl"


</style>
