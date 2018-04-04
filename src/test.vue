<template>
<div>
  dsd
</div>
</template>
<script>
export default{
  mounted(){
    let p = new Promise(function(resolve, reject) {
        resolve(1)
    })

    p.then(function(value) {
        return 3
    }).then(value=>{
      console.log(value)
    })
  }
}
</script>
