<template>
<div class="container mt-5" id="scrollspyHeading2" >
    <h1 class="header">Portfolio</h1>
    <hr width="50%">
    <p class="subtext">{{subtext}}</p>
</div>


<div class="container mt-5 px-5">
	<div class="gal">	
        <div class="container container-img" 
        @dblclick="$emit('getImageCode' , [image.itemCode,image.description])"
        v-for="image in portfolio" :key="image" 
        >
            <img :src="image.src" alt=""  >
            <div class="overlay">
                {{image.description}}
                <br>
                <span class="float-start">
                    <img :src="hint" alt="" style="width: 20px;">
                    <small class="text-start ms-2 text-light fw-normal" style="font-size:12px">Double-click to request a qoute</small>
                </span>
            </div>
        </div>
	</div>
</div>
</template>

<script>
export default {
    name: "Portfolio",
    emits: ['getImageCode'],  
    data() {
        return {
            hint: require("../assets/lightbulb.png"),
            portfolio:[
                {src:[require("../assets/1000_F_149594236_OnTSffIxq6J0EbBRSlSRG34wBV8qtIW8.jpg")], description:"lorem ipsm Init", itemCode:"aks0011" },
                {src:[require("../assets/luis-quintero-3qqiMT2LdR8-unsplash.jpg")], description:"lorem ipsm Init", itemCode:"aks0014" },
                {src:[require("../assets/IMG_6039.jpg")], description:"lorem ipsm Init", itemCode:"aks0018" },
                {src:[require("../assets/IMG_6037.jpg")], description:"lorem ipsm Init", itemCode:"aks0012" },
                {src:[require("../assets/IMG_6036.jpg")], description:"lorem ipsm Init", itemCode:"aks0010" },
                {src:[require("../assets/IMG_6035.jpg")], description:"lorem ipsm Init", itemCode:"aks0010" },
                {src:[require("../assets/IMG_6039.jpg")], description:"lorem ipsm Init", itemCode:"aks0018" },
                {src:[require("../assets/IMG_6036.jpg")], description:"lorem ipsm Init", itemCode:"aks0010" },

            ],
            subtext:`Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt 
                    ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
                    aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore 
                    eu fugiat nulla pariatur`
        }
    },
}


</script>

<style scoped>
/* @import url('https://fonts.googleapis.com/css2?family=Gwendolyn:wght@700&display=swap'); */
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@300&display=swap');

.gal {
-webkit-column-count: 3; /* Chrome, Safari, Opera */
-moz-column-count: 3; /* Firefox */
column-count: 3;
}	
.gal img{
width: 100%;
transition: 0.4s;
opacity: .7; /*dark-mode*/
}
.container-img:hover img{
    transform: scale(1.03, 1.03);
    border-top-left-radius: 20px;
    border-top-right-radius: 20px;
    /* box-shadow: 0px 0px 8px 6px rgb(0 0 0 / 20%), -5px -5px 15px -7px rgb(0 0 0 / 17%); */
}
@media (max-width: 700px) {		
    .gal {	
        -webkit-column-count: 2; /* Chrome, Safari, Opera */
        -moz-column-count: 2; /* Firefox */
        column-count: 2;
    }
}

@media (max-width: 500px) {		
    .gal {	
        -webkit-column-count: 1; /* Chrome, Safari, Opera */
        -moz-column-count: 1; /* Firefox */
        column-count: 1;
    }
}

.header{
font-family: 'Raleway', sans-serif;
    font-size: 58px;
}
.subtext{
    
font-family: 'Raleway', sans-serif;
    font-size: 20px
}

/* 
* {box-sizing: border-box} */

/* Container needed to position the overlay. Adjust the width as needed */
.container-img {
    position: relative;
    padding-left: 0px;
    padding-right: 0px;
    margin: 20px;
    padding-top: 20px;
}

/* The overlay effect - lays on top of the container-img and over the image */
.overlay {
    position: absolute;
    bottom: -1.3%;
    right: 0px;
    text-align: left !important;
    background: rgba(0, 0, 0, 0.63); /* Black see-through */
    width: 100%;
    transition: .2s cubic-bezier(0.68, 0.01, 1, 1);
    opacity:0;
    color: white;
    font-size: 20px;
    padding: 20px;
    text-align: center;
    box-shadow: 0px 1px 5px 5px rgb(0 0 0 / 6%), -2px 2px 21px 0px rgb(0 0 0 / 16%);
}

/* When you mouse over the container-img, fade in the overlay title */
.container-img:hover .overlay {
    opacity: 1;
    transform: scale(1.03, 1.03);
}

</style>
