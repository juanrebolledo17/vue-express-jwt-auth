<template>
  <div class="register">
    <div class="register-container">
      <form @submit.prevent="register">
        <div>
          <input type="text" placeholder="First name" v-model="firstname">
        </div>
        <div>
          <input type="text" placeholder="Last name" v-model="lastname">
        </div>
        <div>
          <input type="text" placeholder="Username" v-model="username">
        </div>
        <div>
          <input type="email" placeholder="Email" v-model="email">
        </div>
        <div>
          <input type="password" placeholder="Password" v-model="password"> 
        </div>
        <div>
          <button type="submit" class="login-button">
            Sign Up
          </button>
        </div>
      </form>
      <div>
        <router-link to="/signin">Already have an account? Sign in.</router-link>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'SignUp',
  data() {
    return {
      firstname: '',
      lastname: '',
      username: '',
      email: '',
      password: ''
    }
  },
  methods: {
    async register() {
      const response = await axios.post( 'http://localhost:3000/api/user/register',{
        firstname: this.firstname,
        lastname: this.lastname,
        username: this.username,
        email: this.email,
        password: this.password
      })
      console.log(response.data)
      this.firstname = ''
      this.lastname = ''
      this.username = ''
      this.email = ''
      this.password = ''
    }
  }
}
</script>

<style lang="stylus" scoped>
.register
  width 100%
  height 100%
  display flex
  justify-content center
  align-items center

.register-container
  width 50%
  display flex
  justify-content center
  align-items center
  flex-direction column 
  box-shadow 1px 1px 5px rgba(0,0,0,0.20)
  border-radius 10px
  padding 25px
  
  form
    width 100%
    
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
</style>