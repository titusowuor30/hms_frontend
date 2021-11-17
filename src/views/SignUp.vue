<template>
    <div class="container">
        <h1 class="title">{{pageName}}</h1>
<form @submit.prevent="onSubmit" class="form-control">
<div class="field">
  <label class="label">Username</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="text" placeholder="username" required v-model="username">
    <span class="icon is-small is-left">
      <i class="fas fa-user"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
  </div>
</div>

<div class="field">
  <label class="label">Phone</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="text" placeholder="+2547 xxx xxx xxx" required v-model="phone">
    <span class="icon is-small is-left">
      <i class="fas fa-phone"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
  </div>
</div>

<div class="field">
  <label class="label">Email</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-info" type="email" placeholder="Email input" required v-model="email">
    <span class="icon is-small is-left">
      <i class="fas fa-envelope"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-exclamation-triangle"></i>
    </span>
  </div>
</div>
<div class="field">
  <label class="label">National ID</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="text" placeholder="Id Number" required v-model="identification">
    <span class="icon is-small is-left">
      <i class="fas fa-id-card"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
  </div>
</div>

<div class="field">
  <label class="label">Password</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="password" placeholder="**********" required v-model="password">
    <span class="icon is-small is-left">
      <i class="fas fa-key"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
  </div>
</div>


<div class="field">
  <label class="label">Confirm Password</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="password" placeholder="**********" required v-model="confirm_password">
    <span class="icon is-small is-left">
      <i class="fas fa-key"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
  </div>
</div>


<div class="field is-info">
<label for="img" class="label">Select image:</label>
  <input type="file" id="img" class="is-info"  accept="image/*">
  </div>

<div class="field">
  <div class="control">
    <label class="checkbox">
      <input type="checkbox">
      I agree to the <a href="#">terms and conditions</a>
    </label>
  </div>
</div>

<div class="field is-grouped">
  <div class="control">
    <button class="button is-link" type="submit">Submit</button>
  </div>
  <div class="control">
      <router-link to="/">
          <button class="button is-link is-light">Cancel</button>
      </router-link>
  </div>
</div>
        </form>
    </div>
</template>

<script>
import axios from '../../node_modules/axios'
import  { toast } from 'bulma-toast'

export default{
    name:'SignUp',
    data() {
        return {
            username:'',
            phone:'',
            email:'',
            identification:'',
            password:'',
            confirm_password:'',
            users:[],
        }
    },
computed:{
pageName(){
  if(this.$route.name === 'SignUp'){
    return 'Create a Free Account'
  }else{
    return 'Update Profile'
  }
}
},    
created() {
    axios
    .get('/users')
    .then(response =>{
      this.users=response.data
    })
    .catch(error =>{
      console.log(error)
    }) 
},
mounted() {
    
},
methods: {
  onSubmit(){
if(this.$route.name === 'SignUp'){
  if(this.password === this.confirm_password){
     const newuser={
       username:this.username,
       phone:this.phone,
       email:this.email,
       identification:this.identification,
       password:this.password,
     } 
      axios
     .post('/register',newuser)
     .then(response =>{
       this.posts=[...this.users,response.data]
       toast({
        message: 'Account created',
        type: 'is-success',
        dismissible: true,
        'duration': 3000,
        'position': 'top-left',
      })
       this.$router.push({'name':'Login'})
     })
     .catch(error =>{
      toast({
        message: toString(error),
        type: 'is-danger',
        dismissible: true,
        'duration': 3000,
        'position': 'top-left',
      })
     })  
  }else{
      toast({
        message:'Passwords dont match',
        type: 'is-danger',
        dismissible: true,
        'duration': 3000,
        'position': 'top-left',
      })
  }
    
}else{
    const user_id=this.$route.params.id
    axios
    .put(`/users/${user_id}`,{
      username:this.username,
       phone:this.phone,
       email:this.email,
       identification:this.identification,
    })
    .then(()=>{
    toast({
      message: 'Profile updated',
      type: 'is-success',
      dismissible: true,
      'duration': 3000,
      'position': 'top-left',
    })
    })
    .catch(error =>{
      console.log(error)
      toast({
      message:toString(error),
      type: 'is-danger',
      dismissible: true,
      'duration': 3000,
      'position': 'top-left',
    })
    })
    this.$router.push({'name':'MyAccount'}) 
     }
    },
},
}
</script>