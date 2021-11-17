<template>
  <div id="wrapper">
    <nav class="navbar is-dark">
      <div class="navbar-brand">
        <router-link to="/" class="navbar-item">
        <h1 style="font-size:36px;"><strong>Hostel Manager</strong></h1>
    </router-link>
    
      </div>
      <a class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbar-menu" @click="showMobileMenu = !showMobileMenu">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
         <span aria-hidden="true"></span>
       </a>
      <div class="navbar-menu" id="navbar-menu" :class="{'is-active':showMobileMenu}">
         <div class="navbar-start">
          <div class="navbar-item">
            <form method="get" action="/search">
              <div class="field has-addons">
                <div class="control">
                  <input type="text" class="input" placeholder="What are you looking for?" name="query">
                </div>

                <div class="control">
                  <button class="button is-success">
                      <span class="icon">
                      <i class="fas fa-search"></i>
                      </span>
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
         <div class="navbar-end">
          <router-link to="/about" class="navbar-item">About</router-link>
          <router-link to="/rooms" class="navbar-item">Hostels</router-link>
         <router-link to="/explore" class="navbar-item">Explore</router-link>
         <div class="navbar-item">
           <div class="buttons">
             <router-link :to="{name:'Login'}" class="button is-link">
             <span class="icon"><i class="fas fa-sign-in-alt"></i></span>
             </router-link>
             <router-link :to="{name:'MyAccount'}">
                <span class="button is-success"><i class="fas fa-user-alt"></i>&nbsp;My Account</span>
              </router-link>
           </div>
         </div>
         </div>
       </div>
    </nav>
    <section class="section">
  <router-view/>
</section>
    <footer class="footer">
     <p class="has-text-centered is-italic">Copyright &copy; TDBSoft @2021</p>
   </footer>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showMobileMenu:false,
    }
  },
}
</script>
<style lang="scss">
@import '../node_modules/bulma'
</style>
