<template>
    <div class="container">
        <h1 class="title">Login to Your Account</h1>
<form action="" class="form-control">
<div class="field">
  <label class="label">Username</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="text" placeholder="username" required>
    <span class="icon is-small is-left">
      <i class="fas fa-user"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
  </div>
</div>
<div class="field">
  <label class="label">Password</label>
  <div class="control has-icons-left has-icons-right">
    <input class="input is-success" type="password" placeholder="**********" required>
    <span class="icon is-small is-left">
      <i class="fas fa-key"></i>
    </span>
    <span class="icon is-small is-right">
      <i class="fas fa-check"></i>
    </span>
  </div>
</div>
<div class="field is-grouped">
  <div class="control">
    <router-link :to="{name:'PasswordReset'}" class="is-link">
        <span class="is-danger" style="color:red;">Forgot password?</span>
    </router-link>
  </div>
  <div class="control">
      <div to="/">
          <router-link :to="{name:'SignUp'}" class="is-link is-light">Create account</router-link>
      </div>
  </div>
</div>

<div class="field is-grouped">
  <div class="control">
    <button class="button is-link">Login</button>
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