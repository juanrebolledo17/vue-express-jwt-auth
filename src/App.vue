<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/signin">Sign in</router-link> |
      <router-link to="/signup">Sign up</router-link>
    </div>
    <main>
      <router-view/>
    </main>
  </div>
</template>

<style lang="stylus">
*
  margin 0
  padding 0
  box-sizing border-box 

body
  font-family Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  color #2c3e50
  overflow-x hidden

a
  // color #42b983
  text-decoration none

#app
  height 100vh
  width 100vw
  text-align center

#nav 
  width 100%
  display flex
  justify-content center
  padding 25px
  color #f4f4f4
  background-color #42b983

#nav a 
  margin 0 1rem
  color inherit
  // transition all linear 0.25s
  text-transform capitalize
  letter-spacing 0.05em

#nav a:hover
  color #2f855a

main
  width: 100%
  height: 100%
</style>
