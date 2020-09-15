<template>
  <div class="login">
    <div class="info">
      <h1>Vuejs</h1>
      <p>
        The best JS framework to work with, enjoy the developer experience to the maximum while also increasing productivity and building awesome projects. Sign in to start the journey.
      </p>
    </div>
    <div class="login-container">
      <div class="form-container">
        <form @submit.prevent="login">
          <div>
            <input type="email" placeholder="Email" v-model="email">
          </div>
          <div>
            <input type="password" placeholder="Password" v-model="password">
          </div>
          <div>
            <button type="submit" class="login-button">
              Log in
            </button>
          </div>
        </form>
        <div>
          <a href="#">Forgot password?</a>
        </div>
        <hr>
        <div>
          <router-link to="/signup" class="create-button">
            Create new account
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
// axios.defaults.headers.common['Authorization'] = AUTH_TOKEN;

export default {
  name: 'SignIn',
  data() {
    return {
      email: '',
      password: ''
    } 
  },
  methods: {
    async login() {
      try {
        const response = await axios.post('http://localhost:3000/api/user/login', {
          email: this.email,
          password: this.password
        })

        console.log(response.data)
      } catch (e) {
        console.log(e)
      }
      
      this.email = ''
      this.password = ''
    }
  }
}
</script>

<style lang="stylus" scoped>
.login
  width 100%
  height 100%
  display flex
  justify-content center
  align-items center
  padding: 0 5%
  
.info
  width: 50%
  text-align  left
  
  h1 
    margin-bottom 15px
    color #2f855a
    font-weight 700
    letter-spacing 0.025em
    font-size: 2.75rem;
  
  p
    line-height 1.4

.login-container
  width: 50%
  display flex
  justify-content center
  align-items center
  
  .form-container 
    box-shadow 1px 1px 5px rgba(0,0,0,0.20)
    width: 75%
    border-radius 10px
    padding 12px
    
    div 
      margin-bottom 10px
      
      input
        padding 12px
        width: 100%
        border-radius 5px
        border 1px solid #c4c4c4
        color #1a202c
        font-size 1.05rem
      
      input::placeholder
        color #718096
      
      input:focus
        outline none
        border 1px solid #2f855a
      
      button
        width: 100%
        background-color #2f855a
        border none
        color #f4f4f4
        padding 10px 0
        margin-top: 10px
        border-radius 5px
        font-weight bold
        font-size 1.25rem
        cursor pointer
      
      button:hover
        background-color #276749
      
      a
        color #38a169
        display inline-block
        padding 10px 0
      
      a:hover 
        color #276749
      
      a.create-button
        background-color #4a5568
        border none
        color #fff
        padding 10px
        margin-top: 10px
        border-radius 5px
        font-weight bold
        font-size 1.05rem
      
      a.create-button:hover
        background-color #2d3748
</style>