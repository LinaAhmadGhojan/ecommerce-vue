<template>
  <br>
 
  <div class="banner_bg_main" style="    text-align: center;
  background: none rgb(255 211 51);
  width: 50%;
  margin-left: 24%;
  margin-top: 49px;
  border-radius: 41px;;">

  <form @submit.prevent="login">
    <br><br>
    <div style="color: #000;font-size: large">
      User Name:
    </div>
      
      <input  type="text" v-model="username" required style="height: 47px;
      width: 79%;
      border: none;
      padding-left: 21px;
      border-radius: 11px;">
      <br><br>
      <div style="color: #000;font-size: large">
        Password:
      </div>
      <input type="password" v-model="password" required  style="height: 47px;
      width: 79%;
      border: none;
      padding-left: 21px;
      border-radius: 11px;">
      <br>
      <br><br> 
    <button type="submit" style="width: 26%;
    background-color: #000;
    color: #fff;
    height: 39px;
    border-radius: 11px;">Login</button>
    <br><br>
  </form>
  </div>
</template>

<script>
const baseUrl="http://127.0.0.1:8000/api/";
export default {
  data() {
    return {
      username: "mor_2314",
                password: "83r5^_"
    }
  },
  methods: {
    async login() {
      // Send POST request with user's credentials
      const response = await fetch('https://fakestoreapi.com/auth/login', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          username: this.username,
          password: this.password
        })
      })
      
      if (response.ok) {
        // Store token in app
        const { token } = await response.json()
        localStorage.setItem('token', token)
        
        // Redirect to dashboard
        this.$router.push('/dashboard')
      } else {
        // Handle login error
        console.log('Login error:', response.statusText)
      }
    }
  }
}
</script>
