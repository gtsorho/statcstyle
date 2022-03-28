<template>
<div class="content mt-1" id="scrollspyHeading3">
<div class="container">
    <div class="row justify-content-center">
    <div class="col-md-10">
        <div class="row align-items-center">
        <div class="col-lg-7 mb-5 mb-lg-0">
            <h1 class="mb-5"> Send us a message.</h1> 
            <h2> It's easy.</h2>
            <form
            class="border-right pr-5 mb-5"
            method="post"
            id="contactForm"
            name="contactForm"
            >
            <div class="row">
                <div class="col-md-6 form-group">
                    <input type="text" class="form-control" name="fname" id="fname" placeholder="First name"/>
                </div>
                <div class="col-md-6 form-group">
                    <input type="text" class="form-control" name="lname" id="lname" placeholder="Last name"/>
                </div>
            </div>
            <div class="row">
                <div class="col-md-12 form-group">
                <input type="text" class="form-control" name="email" id="email" placeholder="Email" />
                </div>
            </div>
            <div class="row">
                <div class="col-md-12 form-group">
                <textarea class="form-control" name="message" id="message" cols="30" rows="7" v-model="itemDescription" placeholder="Write your message"></textarea>
                </div>
            </div>
            <div class="row">
                <div class="col-md-12">
                    <input type="submit" value="Send Message" class="btn rounded-5 py-2 px-4"/>
                    <span class="submitting"></span>
                </div>
            </div>
            </form>
            <div id="form-message-warning mt-4"></div>
            <div id="form-message-success">
            Your message was sent, thank you!
            </div>
        </div>
        <div class="col-lg-4 ml-auto">
            <h3 class="mb-4">Let's talk about everything.</h3>
            <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil
            deleniti itaque similique magni. Magni, laboriosam perferendis
            maxime!
            </p>
            <p><a href="#">Read more</a></p>
        </div>
        </div>
    </div>
    </div>
</div>
</div>
</template>

<script>
export default {
    name: "Contact",
    props: {
        imageCode : Array
    },
    data() {
        return {
            
        }
    },
    computed:{
        itemDescription(){
            if(this.imageCode.length != 0){
            return this.imageCode[1] + ' (' + this.imageCode[0] + ')'
            }
        },  
    }

        
    
    
};

</script>

<style scoped>
/* @import url('https://fonts.googleapis.com/css2?family=Gwendolyn:wght@700&display=swap'); */
h1 {
    /* font-family: 'Tangerine', serif; */
    font-size: 48px;
    margin-bottom: 0px !important;
}
h2, h3 {
    /* font-family: 'Gwendolyn', cursive; */
    font-size: 30px;
}
.form-control {
    font-weight: 500;
    border: none;
    border-bottom: 1px solid #929292;
    padding-left: 0;
    padding-right: 0;
    border-radius: 0;
    color: #ffffff !important;
    background-color: #fff0 !important;
}
.btn, .form-control {
    height: 45px;
    transition: 0.4s;
}
.btn{
    background-color: rgb(255, 88, 202);
    color: #ffffff !important;
    
}
.btn:hover{
    background-color: #ff00ae;
    transform: scale(1.05, 1.05);
}
.form-group {
    margin-bottom: 1rem;
}
.border-right {
    border-right: 1px solid #8686869c!important;
}
form.border-right {
    padding-right: 6rem !important;
}
.form-control:focus {
    box-shadow: none;
    transform: scale(1.05, 1.05);
    border-bottom-color: #ff00ae;
}
.content{
        margin-top: 10% !important;
}
</style>