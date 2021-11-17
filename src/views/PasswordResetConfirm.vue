<template>
    <div class="container">
        <h1 class="title">Request for password reset</h1>
<form @submit.prevent="onSubmit" class="form-control">
<div class="field">
  <label class="label">New Password</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="password" placeholder="*********" required v-model="password">
    <span class="icon is-small is-left">
      <i class="fas fa-key"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
  </div>

</div>

<div class="field">
  <label class="label">Token</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="password" placeholder="*********" required v-model="token">
    <span class="icon is-small is-left">
      <i class="fas fa-key"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
    <p class="is-success">Paste reset token sent to your email here</p>
  </div>
<br>
  <div class="field is-grouped">
  <div class="control">
    <button class="button is-link" type="submit">Reset Password</button>
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
            passoword:'',
            token:'',
        }
    },
    methods: {
        onSubmit(){
            axios
            .post('password_reset/confirm',{
               password:this.passoword,
               token:this.token, 
            })
            .then(() =>{
             alert('Success!')   
              toast({
                message: 'Success!',
                type: 'is-success',
                dismissible: true,
                'duration': 3000,
                'position': 'top',
            })
            })
            .catch(error =>{
                 toast({
                message:toString(error),
                type: 'is-danger',
                dismissible: true,
                'duration': 3000,
                'position': 'top-left',
            })
            })
            this.$router.push({name:'Login'})
        }
    },
}
</script>