<template>
<div class="container">
<h1 class="title">My Account</h1>
<hr>
<div class="box is-light">
 <div class="level">
  <!-- Left side -->
  <div class="level-left">
    <div class="level-item">
         <router-link to="" class="button is-danger">
             <strong>Log Out</strong>
         </router-link>
  </div>
  </div>
  <!-- Right side -->
  <div class="level-right">
      <router-link :to="{name:'SignUp'}" class="button is-link">
             <strong>Update Profile</strong>
         </router-link>
  </div>   
</div>
</div>
<section class="section">
    <div class="container">
        <h1 class="title">Active Bookings</h1>
        <div class="box has-background-gray-light">
        <table class="table">
  <thead>
    <tr>
      <th><abbr title="SNO">#</abbr></th>
      <th>NAME</th>
      <th><abbr title="Played">ID</abbr></th>
      <th><abbr title="Won">HOSTEL</abbr></th>
      <th><abbr title="Drawn">ROOM</abbr></th>
      <th><abbr title="Lost">RENT</abbr></th>
      <th><abbr title="Goals for">STATUS</abbr></th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <th><i>Active bookings</i></th>
    </tr>
  </tfoot>
<tbody>
    
</tbody>
</table>
        </div>
    </div>
</section>
</div>
</template>