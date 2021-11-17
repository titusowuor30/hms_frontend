<template>
  <div class="home">
    <section class="hero is-small is-mb-6 has-background-grey">
    <div class="hero-body has-text-centered">
      <p class="title has-text-white">Welcome To Maseno Town Hostel Manager</p>
      <p class="subtitle"><strong>Find your favourite Hostel with ease!</strong></p>
    </div>
    </section>

<!-- display blog post -->
<section class="section">
  <div class="columns is-multiline">
    <div class="column is-12">
      <h1 class="is-size-2 has-text-centered">Top Rated Hostels</h1>
    </div>
      <div class="colum is-3">
      <div class="box mb-2 m-2 is-light">
        <h3 class="is-size-4">Botanic Hostels</h3>
        <hr>
        <div class="box">
          <figure class="image mb-4">
                <img src="../assets/hostel_img4.jpg">
            </figure>
       <p class="is-size-6 has-text-gray">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
       <router-link to="" class="button is-info mt-4">Read More &nbsp;<i class="fas fa-arrow-right"></i></router-link>
      </div>
      </div>
       <div class="box mb-2 m-2 is-light">
        <h3 class="is-size-4">Imani Hostels</h3>
        <hr>
        <div class="box">
            <figure class="image mb-4">
                <img src="../assets/hostel_img1.jpg">
            </figure>
       <p class="is-size-6 has-text-gray">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
       <router-link to="" class="button is-info mt-4">Read More &nbsp;<i class="fas fa-arrow-right"></i></router-link>
      </div>
      </div>
       <div class="box mb-2 m-2 is-light">
        <h3 class="is-size-4">Caro Hostels</h3>
        <hr>
        <div class="box">
           <figure class="image mb-4">
                <img src="../assets/hostel_img2.jpg">
            </figure>
       <p class="is-size-6 has-text-gray">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
       <router-link to="" class="button is-info mt-4">Read More &nbsp;<i class="fas fa-arrow-right"></i></router-link>
      </div>
      </div>
       <div class="box mb-2 m-2 is-light">
        <h3 class="is-size-4">Villa Hostels</h3>
        <hr>
        <div class="box">
           <figure class="image mb-4">
                <img src="../assets/hostel_img3.jpg">
            </figure>
       <p class="is-size-6 has-text-gray">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
       <router-link to="" class="button is-info mt-4">Read More &nbsp;<i class="fas fa-arrow-right"></i></router-link>
      </div>
      </div>
      </div>
  </div>
</section>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from '../../node_modules/axios'

export default {
  name: 'Home',
  data() {
    return {
     
    }
  },
  components: {
  },
  computed:{
    
    },
  methods: {
    
  },
  mounted(){
    
},
}
</script>
<style scoped>
 .image {
    margin-top: -1.25rem;
    margin-left: -1.25rem;
    margin-right: -1.25rem;
  }
</style>
