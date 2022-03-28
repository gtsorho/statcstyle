<template>
  <nav id="navbar-example2" :style="navbar" class="navbar navbar-dark navbar-expand-lg fixed-top  px-3 mt-0">
    
  <!-- <ul class="nav">
    <li class="nav-item">
      <a class="nav-link" href="#scrollspyHeading1">Home</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="#scrollspyHeading2">Portfolio</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="#scrollspyHeading3">Contact</a>
    </li>
    
  </ul> -->

  <div class="container-fluid">
    <a class="navbar-brand" href="#">
      <img :src="logoimg" :style="logo" alt=""  >
    </a>

    <button class="navbar-toggler " type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse " id="navbarNavAltMarkup">
      <div class="navbar-nav float-end">
        <a class="nav-link" href="#scrollspyHeading1">Home</a>
        <a class="nav-link" href="#scrollspyHeading2">Portfolio</a>
        <a class="nav-link" href="#scrollspyHeading3">Contact</a>
      </div>
    </div>
  </div>
</nav>
<div data-bs-spy="scroll" data-bs-target="#navbar-example2" data-bs-offset="0" class="scrollspy-example" tabindex="0" >
  
  <Banner/>
  <Portfolio @getImageCode="getimageCode"/>
  <Contact :imageCode="imageCode" />
</div>
</template>

<script>
import Banner from "./banner.vue"
import Portfolio from "./portfolio.vue"
import Contact from "./contact.vue"
export default {
  name: 'Scrollspy',
  components:{
    Banner,
    Portfolio,
    Contact
  },
  data() {
    return {
      imageCode: [],
      navbar:{
      padding : "30px 10px"
      },
      logo:{
        width: "80px"
      },
      logoimg : require("../assets/logo1.png")
    }
  },
  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll (event) {
        // Any code to be executed when the window is scrolled
      if (document.body.scrollTop > 500 || document.documentElement.scrollTop > 500) {
      this.navbar = "padding : 5px 10px; background-color : rgb(255 168 228 / 91%) !important;";
      this.logo = "width : 30px";
      
      } else {
      this.navbar = "padding : 30px 10px";
      this.logo = "width : 40px";
      }
    },
    getimageCode(event){
        this.imageCode = event
        window.location.href = '#scrollspyHeading3'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar {
   background: rgba(0, 0, 0, 0.473) !important;
   transition: 0.4s;
}
.nav-link{
    color: #ffffff !important;
    font-variant: common-ligatures;
    font-weight: 600;
    font-size: 15px;
    margin: 0px 20px 0 20px
}
.nav-link:focus, .nav-link:hover {
    color: hsl(319, 100%, 50%) !important;
    transform: scale(1.05, 1.05);
}
.navbar-collapse {
    flex-grow: 0;
}
</style>
