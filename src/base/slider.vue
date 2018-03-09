<template>
<div class='slider' ref='slider'>
  <div class='slider-group'>
    <slot>

    </slot>
  </div>
  <div class='dots'>

  </div>
</div>
</template>
<script>
export default{
  mounted(){
    this._setSliderWidth()
  },
  methods:{
    _setSliderWidth(){
      console.log([this.$refs.slider])
    }
  }
}
</script>
