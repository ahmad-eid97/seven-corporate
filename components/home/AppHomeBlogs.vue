<template>
   <section class="blog-section bg-f8">
        <div class="container">
            <div class="row">
                <div class="section-title">
                    <h2>WELCOME TO SEVEN CORPORATE!</h2>
                </div>
            </div>
            <div class="row">
                <div class="col-md-6 col-lg-4 slider-container">
                    <swiper :options="swiperOption" class="owl-carousel">
                        <swiper-slide>
                            <div class="item">
                                <div class=" projects-col">

                                    <div class="thumb">
                                        <img src="/assets/images/testimonials/9.jpg" alt="">
                                    </div>
                                    <div class="content">
                                        <h4>RICHARD SWIFT</h4>
                                        <h5>junior consultant</h5>
                                        <h6>Donec vestibulum lectus sem, vel convallis ligula commodo ac. Aenean congue
                                            placerat risus, eu ullamcorper velit maximus sed.</h6>
                                        <h5>tel. 001 234 56 789</h5>
                                        <h3>richard@your-website.com</h3>

                                    </div>
                                </div>
                            </div>
                        </swiper-slide>

                        <swiper-slide>
                            <div class="item">
                                <div class=" projects-col">

                                    <div class="thumb">
                                        <img src="/assets/images/testimonials/8.jpg" alt="">
                                    </div>
                                    <div class="content">
                                        <h4>MIRIAM GREENWOOD</h4>
                                        <h5>consultant</h5>
                                        <h6>Donec vestibulum lectus sem, vel convallis ligula commodo ac. Aenean congue
                                            placerat risus, eu ullamcorper velit maximus sed.</h6>
                                        <h5>tel. 001 234 56 789</h5>
                                        <h3>miriam@your-website.com</h3>

                                    </div>
                                </div>
                            </div>
                        </swiper-slide>
                        <div class="swiper-button-next" slot="button-next"></div>
                        <div class="swiper-button-prev" slot="button-prev"></div>
                    </swiper>
                </div>
                <div class="col-md-6 col-lg-4">
                    <div class="">
                        <div class="overview-item mb-20">
                            
                            <div class="overview-details">
                                <h3 class="title">Lorem ipsum dolor sit</h3>
                                <p class="text-black">Lorem ipsum dolor sit amet, consectetur
                                    adipisicing elit. Sunt
                                    voluptates amet voluptatum.
                                </p>
                            </div>
                            <div class="overview-icon">
                                <h4 class="one"><font-awesome-icon icon="fa-solid fa-leaf" /></h4>
                            </div>
                        </div>
                        <div class="overview-item mb-20">
                            
                            <div class="overview-details">
                                <h3 class="title">Lorem ipsum dolor sit</h3>
                                <p class="text-black">Lorem ipsum dolor sit amet, consectetur
                                    adipisicing elit. Sunt
                                    voluptates amet voluptatum.
                                </p>
                            </div>
                            <div class="overview-icon">
                                <h4 class="one"><font-awesome-icon icon="fa-solid fa-layer-group" /></h4>
                            </div>
                        </div>
                        <div class="overview-item mb-20">
                            
                            <div class="overview-details">
                                <h3 class="title">Lorem ipsum dolor sit</h3>
                                <p class="text-black">Lorem ipsum dolor sit amet, consectetur
                                    adipisicing elit. Sunt
                                    voluptates amet voluptatum.
                                </p>
                            </div>
                            <div class="overview-icon">
                                <h4 class="one"><font-awesome-icon icon="fa-solid fa-arrows-spin" /></h4>
                            </div>
                        </div>
                        <div class="overview-item mb-20">
                            
                            <div class="overview-details">
                                <h3 class="title">Lorem ipsum dolor sit</h3>
                                <p class="text-black">Lorem ipsum dolor sit amet, consectetur
                                    adipisicing elit. Sunt
                                    voluptates amet voluptatum.
                                </p>
                            </div>
                            <div class="overview-icon">
                                <h4 class="one"><font-awesome-icon icon="fa-solid fa-layer-group" /></h4>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 col-lg-4">
                    <div class="">
                        <div class="thumb">
                            <img alt="" src="/assets/images/art001-1161x599.jpg">
                        </div>

                        <div class="content mt-40 right ">
                            <h3>REFRACTORY SERVICES</h3>

                            <p>Donec odio augue placerat est, nec semper nisl lorem ipsum vestibulum lectus sem!

                                Maecenas feugiat, nulla eget maximus elementum, odio augue placerat est, nec semper
                                nisl erat ac ex el convallis ligula commodo ac. Aenean congue. Nunc eu tellus
                                pellentesque!</p>
                        </div>
                        <a href="blog-details.html" class="read-btn float-end">Continue Reading

                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppHomeBlogs',
    data() {
        return {
        swiperOption: {
            loop: true,
            slidesPerView: 1,
            spaceBetween: 50,
            navigation: { nextEl: '.swiper-button-prev', prevEl: '.swiper-button-next', }
        },
        }
    },
    methods : {
        
    }
}
</script>

<style>
    .slider-container {
        position: relative;
    }
    .slider-container .owl-carousel {
        background: #fff;
        padding: 30px 0px;
    }
    .slider-container .owl-carousel .owl-item {
        padding: 35px 15px;
    }
    .slider-container .owl-theme .owl-nav .owl-next,
    .slider-container .owl-theme .owl-nav .owl-next:hover, 
    .slider-container .owl-theme .owl-nav .owl-prev, 
    .slider-container .owl-theme .owl-nav .owl-prev:hover {
        background-color: var(--main-color);
        color: transparent;
        display: inline-block;
        height: 75px;
        width: 24px;
        top: 197px;
        text-align: center;
        line-height: 75px;
        font-size: 18px;
        position: absolute;
    }
    .slider-container .owl-nav .owl-next {
        right: 0px;
    }
    .slider-container .owl-nav .owl-prev {
        left: 0px;
    }
    .next {
        display: inline-block;
        top: 232px;
        text-align: center;
        line-height: 75px;
        font-size: 18px;
        position: absolute;
        color: #fff;
        right: 24px;
        z-index: 2;
    }
    .prev {
        display: inline-block;
        top: 232px;
        text-align: center;
        line-height: 75px;
        font-size: 18px;
        position: absolute;
        color: #fff;
        left: 24px;
        z-index: 2;
    }
    .overview-icon {
        height: 34px !important;
    }
    .overview-icon .one {
        position: static !important;
        font-size: 23px !important;
        text-align: center;
    }
</style>