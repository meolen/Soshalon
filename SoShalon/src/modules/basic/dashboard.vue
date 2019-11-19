<template>
  <div id="dashboard">
    <header id="header">
      <b-navbar toggleable="lg" type="dark" variant="dark">
        <img id="logo" src="/logo.png">

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav class="ml-auto" id="options">
            <b-nav-item v-on:click="redirect('/login')">
              <img id="notify" src="/notifi.png">
            </b-nav-item>

            <b-nav-item v-on:click="redirect('/register')">
              <img id="profile" src="/profile.jpeg">
            </b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </header>

    <!-- search area -->
    <div>
      <b-navbar id="search">
        <b-dropdown id="dropdown-1" text="Choose Service" class="m-md-2">
          <b-dropdown-item>Nail Polish</b-dropdown-item>
          <b-dropdown-item>Haircut</b-dropdown-item>
        </b-dropdown>
        <button type="search" class="search-btn" v-on:click="search()">Search</button>
      </b-navbar>
    </div>
    <!-- cards -->
    <div>

      <div class="card-deck">
        <div class="card">
          <img src="/sp1.jpg" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Nadine Lustre</h5>
            <p
              class="card-text"
            >This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
            <p class="card-text">
              <small class="text-muted">Last updated 3 mins ago</small>
            </p>
          </div>
        </div>

        <div class="card">
          <img src="/sp2.jpg" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Kathryn Bernardo</h5>
            <p
              class="card-text"
            >This card has supporting text below as a natural lead-in to additional content.</p>
            <p class="card-text">
             <b-button href="#" variant="primary">Go somewhere</b-button>
            </p>
          </div>
        </div>

      </div>
    </div>

    <Sidebar id="sidebar" v-if="!isHidden"></Sidebar>
    <div id="dash">
      <center></center>
    </div>
  </div>
</template>

<script>
import Sidebar from "components/frame/Sidebar.vue";
import AUTH from "services/auth";

var fn = JSON.stringify(AUTH.currentUser.fname);
var ln = JSON.stringify(AUTH.currentUser.lname);
var fullname = "Hi  " + fn + " " + ln + "!";
fullname = fullname.replace(/['"]+/g, "");

export default {
  name: "dashboard",
  data() {
    return {
      fn: fullname,
      isHidden: false
    };
  },
  components: {
    Sidebar
  }
};
</script>
<style>
/* body {   
    background-image: url("/bg.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    } */
#logo {
  width: 200px;
  height: auto;
}
.bg-dark {
  background-color: black !important;
}
#notify {
  /* position: absolute; */
  width: 50px;
  height: 50px;

  /* left: 1449px; */
  /* top: 25px; */
  /* z-index: 3; */
}
#profile {
  width: 50px;
  height: 50px;
  /* position: absolute; */
  /* left: 1517px; */
  /* top: 27px; */
  border: 2px solid #ffff;
  border-radius: 50px;
}
#search {
  background-color: rgba(0, 0, 0, 0.3);
}
.search-btn {
  background-color: rgba(0, 188, 212, 0.8);
  border-radius: 25px;
  border-color: #00bcd4;
  width: 110px;
  height: 35px;
  margin-left: 82%;
  color: #fff;
}
.btn-secondary {
  color: #545b62;
  background-color: rgba(255, 255, 255, 0.8);
  /* border-color: #545b62; */
  margin-left: 645%;
}
.btn-secondary:hover {
  color: #fff;
  background-color: rgba(255, 255, 255, 0.8);
  /* border-color: #545b62;    */
}
.card-img {
  width: 40%;
  border-radius: calc(0.25rem - 1px);
}
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji",
    "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-size: 13px;
  font-weight: 200;
  line-height: 1.4;
  color: #212529;
  text-align: left;
  background-color: #fff;
  background-image: url("/bg.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}
#sp1,
#sp2 {
  width: 155px;
  height: auto;
}
</style>