<template>
    <div class="container">
        <h1 class="title">Request for password reset</h1>
<form @submit.prevent="onSubmit" class="form-control" autocomplete="true">
<div class="field">
  <label class="label">Email</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="email" placeholder="Enter the email used during signup" required v-model="email">  
    <span class="icon is-small is-left">
      <i class="fas fa-envelope"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
    <p class="is-success">Enter the email used during signup</p>
  </div>
<br>
  <div class="field is-grouped">
  <div class="control">
    <button class="button is-link" type="submit">Send Request</button>
  </div>
  <div class="control">
      <router-link to="/">
          <button class="button is-link is-light">Cancel</button>
      </router-link>
  </div>
</div>
</div>
</form>
</div>
</template>

<script>
import axios from "../../node_modules/axios"
import { toast } from "bulma-toast"
export default{
    data() {
        return {
            email:'',
        }
    },
    methods: {
        onSubmit(){
            axios
            .post('password_reset/',{
               email:this.email 
            })
            .then(response =>{
              toast({
                message: 'Success:An email has been sent to your account!',
                type: 'is-success',
                dismissible: true,
                'duration': 3000,
                'position': 'top',
            })
            })
            .catch(error =>{
                 toast({
                message:toString(error.response.data),
                type: 'is-danger',
                dismissible: true,
                'duration': 3000,
                'position': 'top-left',
            })
            })
            alert('Success:An email has been sent to your account!')   
            this.$router.push({name:'PasswordResetConfirm'})
        }
    },
}
</script>