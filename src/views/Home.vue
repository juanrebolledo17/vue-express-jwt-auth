<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" class="vue-logo">
    <p class="name">Home Page</p>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld
  }
}
</script>

<style lang="stylus" scoped>
.home
  width 100%
  height 100%
  display flex
  flex-direction column
  justify-content center
  align-items center

.vue-logo:hover 
  animation rotateLogo 1s forwards

.name:hover
  animation rotateP 1s forwards

@keyframes rotateLogo 
  from
    transform rotateY(0)
  to 
    transform rotateY(30deg)

@keyframes rotateP 
  from
    transform rotateY(0)
  to 
    transform rotateY(-30deg)
</style>
