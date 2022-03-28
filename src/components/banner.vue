<template>

<vueper-slides id="scrollspyHeading1" autoplay ref="myVueperSlides" :parallax="parallax" :parallax-fixed-content="parallaxFixedContent"  >
    <vueper-slide
    v-for="(slide, i) in slides" :key="i"
    :image="slide.image"
    :title="parallaxFixedContent ? slide.title : ''"
    :content="parallaxFixedContent ? slide.content : ''" />
</vueper-slides>

        <!-- <div id="scrollspyHeading1">
    <div id="carouselExampleCaptions" class="carousel slide" data-bs-ride="carousel" style="height:7.7in" >
    <div class="carousel-indicators">
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
    </div>
    <div class="carousel-inner">
        <div style="height:7.7in"  class="carousel-item" v-for="image in images" :key="image" :class="image.active">
            <img :src="image.src" class="d-block w-100" alt="...">
            <div class="carousel-caption d-none d-md-block">
                <h5>{{image.heading}}</h5>
                <p>{{image.subtext}}</p>
            </div>
        </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
    </button>
</div>
        </div> -->
<br>
</template>

<script>
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'

export default {
    name: "Banner",
    components: { VueperSlides, VueperSlide },
    data() {
        return {
            parallax: -1,
            parallaxFixedContent: true,
            slides: [
                {
                    title: 'El Teide Volcano, Spain',
                    content: 'Photo by Max Rive',
                    image: require("../assets/1000_F_149594236_OnTSffIxq6J0EbBRSlSRG34wBV8qtIW8.jpg")
                },
                {
                    title: 'El Teide Volcano, Spain',
                    content: 'Photo by Max Rive',
                    image: require("../assets/istockphoto-164297978-170667a.jpg")
                },
                {
                    title: 'El Teide Volcano, Spain',
                    content: 'Photo by Max Rive',
                    image: require("../assets/mediamodifier-7cERndkOyDw-unsplash.jpg")
                },
            ],
            // images:[
            //     {src:[require("../assets/1000_F_149594236_OnTSffIxq6J0EbBRSlSRG34wBV8qtIW8.jpg")], heading:"lorem ipsm Init", subtext: "lorem ipsm Init lorem ipsm Init lorem ipsm Init", active:"active" },
            //     {src:[require("../assets/istockphoto-164297978-170667a.jpg")] , heading:"lorem ipsm Init", subtext: "lorem ipsm Init lorem ipsm Init lorem ipsm Init" },
            //     {src: [require("../assets/1000_F_149594236_OnTSffIxq6J0EbBRSlSRG34wBV8qtIW8.jpg")], heading:"lorem ipsm Init", subtext: "lorem ipsm Init lorem ipsm Init lorem ipsm Init" }
            // ]
        }
    },
}
</script>

<style >
.vueperslide__content-wrapper{
    background-color: #0000006e;
}
.vueperslide__title{
    color: white;
    font-size: 30px;
    font-weight: bold;
}
.vueperslide__content{
    color: rgb(255, 255, 255);
    font-size: 20px;
    font-weight: 900;
}
@media screen and (max-width: 530px) {
   .vueperslides__parallax-wrapper{
        height: 400px !important;
    }
}
</style>