<template>
<Scrollspy/>
<Footer/>
</template>

<script>
import Scrollspy from "./components/scrollspy.vue"
import Footer from "./components/footer.vue"
export default {
  name: 'App',
  components: {
    Scrollspy,
    Footer
  }

}
</script>

<style>
 body{
   background-color: rgb(8, 8, 8) !important; /**dark-mode*/
 }
p,h1,h2,h3,h4,h4,form,input, div, a{
color: #cfcfcf !important; /**dark-mode*/
font-family: 'Raleway', sans-serif;
}
::-webkit-scrollbar {
  width: 10px;
  -webkit-overflow-scrolling: touch;
}

/* Track */
::-webkit-scrollbar-track {
  background: #cfcfcf;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: rgb(255, 88, 202);
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: rgb(255, 0, 157);
}
</style>

