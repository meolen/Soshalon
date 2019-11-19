<template>
    <div id ="dashboard">
        <header id = "header">
             <b-navbar toggleable="lg" type="dark"  variant="dark">
            <img id="logo" src="/logo.png">
            <img id = "notify" src="/notifi.png">
            <img id = "profile" src="/profile.jpeg">
        </b-navbar>  
        </header>
        <div id= "search">
            <b-navbar id="search"> 
                <button type="search" class="search-btn" v-on:click="search()">Search</button>
            </b-navbar>
        </div>  
        <Sidebar id="sidebar" v-if="!isHidden"></Sidebar>
        <div id="dash">
        <center>

        </center>
        </div>
    </div>
    
</template>

<script>
import Sidebar from 'components/frame/Sidebar.vue'
import AUTH from 'services/auth'

var fn = JSON.stringify(AUTH.currentUser.fname)
var ln = JSON.stringify(AUTH.currentUser.lname)       
var fullname = "Hi  "+fn+" "+ ln + "!"
fullname = fullname.replace(/['"]+/g, '')

export default {
  name: 'dashboard',
  data() {
      return{
        fn: fullname,
        isHidden: false
      }
  },
  components: {
      Sidebar
  }
}

</script>
<style>
    body {
    background-image: url("https://png.pngtree.com/thumb_back/fw800/background/20190223/ourmid/pngtree-dark-purple-geometric-minimalist-background-effectgradientbusiness-image_87387.jpg");
    background-repeat: no-repeat;
    background-size: cover
    }
    #logo{
            width: 200px;
            height: auto
        }   
    .bg-dark {
        background-color: black !important;
    }
    #notify{
            position: absolute;
            width: 50px;
            height: 50px;
            left: 1449px;
            top: 25px;
    }
    #profile{
            position: absolute;
            width: 50px;
            height: 50px;
            left: 1517px;
            top: 27px;
            border: 2px solid #ffff;
            border-radius: 50px;
    }    
    #search{
        background-color:rgba(0, 0, 0, 0.5);
    }
    .search-btn{
        background-color: rgba(0, 188, 212, 0.8);
        border-radius: 25px;
        width: 110px;
        height: 35px;
        margin-left: 92%;
        color:#fff;

    }
</style>