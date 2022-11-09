<template>
    <section class="slider-wrapper p-0">
            <!-- Wrapper For Slides -->
                    <VueSlickCarousel ref="c1" :fade="true" :asNavFor="$refs.c2" :arrows="false" :slidesToShow="1" :focusOnSelect="true" :dots="false" >
                        <div class="item">
                            <img src="/assets/images/slider/1.jpg" alt="">
                            <div class="text">
                                <h1>
                                    Investment &  Stock Exchange
                                </h1>
                                <div class="seprate">

                                </div>
                                <p>
                                    Donec odio augue placerat est, nec semper nisl lorem ipsum vestibulum
                                            lectus sem! Maecenas feugiat, nulla eget maximus elementum, odio augue
                                </p>
                            </div>
                        </div>
                        <div class="item">
                            <img src="/assets/images/slider/2.jpg" alt="">
                            <div class="text">
                                <h1>
                                    Investment &  Stock Exchange
                                </h1>
                                <div class="seprate">

                                </div>
                                <p>
                                    Donec odio augue placerat est, nec semper nisl lorem ipsum vestibulum
                                            lectus sem! Maecenas feugiat, nulla eget maximus elementum, odio augue
                                </p>
                            </div>
                        </div>
                        <div class="item">
                            <img src="/assets/images/slider/3.jpg" alt="">
                            <div class="text">
                                <h1>
                                    Investment &  Stock Exchange
                                </h1>
                                <div class="seprate">

                                </div>
                                <p>
                                    Donec odio augue placerat est, nec semper nisl lorem ipsum vestibulum
                                            lectus sem! Maecenas feugiat, nulla eget maximus elementum, odio augue
                                </p>
                            </div>
                        </div>
                        <div class="item">
                            <img src="/assets/images/slider/4.jpg" alt="">
                            <div class="text">
                                <h1>
                                    Investment &  Stock Exchange
                                </h1>
                                <div class="seprate">

                                </div>
                                <p>
                                    Donec odio augue placerat est, nec semper nisl lorem ipsum vestibulum
                                            lectus sem! Maecenas feugiat, nulla eget maximus elementum, odio augue
                                </p>
                            </div>
                        </div>
                        <div class="item">
                            <img src="/assets/images/slider/5.jpg" alt="">
                            <div class="text">
                                <h1>
                                    Investment &  Stock Exchange
                                </h1>
                                <div class="seprate">

                                </div>
                                <p>
                                    Donec odio augue placerat est, nec semper nisl lorem ipsum vestibulum
                                            lectus sem! Maecenas feugiat, nulla eget maximus elementum, odio augue
                                </p>
                            </div>
                        </div>
                    </VueSlickCarousel>
                <!-- Indicators -->
                    <VueSlickCarousel
                        ref="c2"
                        v-show="c1"
                        :asNavFor="$refs.c1"
                        :slidesToShow="5"
                        :focusOnSelect="true" :dots="false" :arrows="false">
                            <img src="/assets/images/slider/1.jpg" class="img-fluid">  
                            <img src="/assets/images/slider/2.jpg" class="img-fluid"> 
                            <img src="/assets/images/slider/3.jpg" class="img-fluid"> 
                            <img src="/assets/images/slider/4.jpg" class="img-fluid">  
                            <img src="/assets/images/slider/5.jpg" class="img-fluid"> 
                    </VueSlickCarousel>


           
        </section>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
 import 'vue-slick-carousel/dist/vue-slick-carousel.css'; 
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

export default {
    name: 'AppHomeSlider',
    components: {VueSlickCarousel},
    data() {
        return {
            c1: undefined,
            c2: undefined,
        }
    },
    methods : {
        
    },
    mounted() {
        this.c1 = this.$refs.c1;
        this.c2 = this.$refs.c2;
    },
}
</script>
<style>
    .slick-slider .item {
        position: relative;
    }
    .slick-slider .item img {
        max-height: 90vh;
    }
    .slick-slider .item .text {
        position: absolute;
        top: 0;
        bottom: 0;
        width: 50%;
        padding: 70px;
        background: #1f365c;
        color: #fff;
    }
    .slick-slider .item .text h1 {
        color: #fff;
        position: relative;
        z-index: 2;
        font-size: 70px;
        top: 60px;
        opacity: 0;
        transition: all 0.5s ease-in;
    }
    .slick-slider .item .text .seprate {
        display: block;
        margin: 30px 0;
        height: 10px;
        background: var(--main-color);
        position: relative;
        z-index: 2;
        width: 0%;
        transition: all 0.5s ease-in;
    }
    .slick-slider .item .text p {
        position: relative;
        z-index: 2;
        top: -60px;
        opacity: 0;
        transition: all 0.5s ease-in;
    }
    .slick-slider .item .text::after {
        content: '';
        width: 100%;
        position: absolute;
        top: 0;
        bottom: 0;
        background: #1f365c;
        right: -70px;
        transform: skew(-10deg);
        z-index: 1;
    }
    .slick-slider .slick-active .item .text h1 {
        top: 0;
        opacity: 1;
    }
    .slick-slider .slick-active .item .text p {
        top: 0;
        opacity: 1;
    }
    .slick-slider .slick-active .item .text .seprate {
        width: 100%;
    }
    .slick-slider:last-of-type  {
        width: 600px;
        position: absolute !important;
        bottom: 30px;
        right: 20px;
        z-index: 3;
    }
    .slick-slider:last-of-type .slick-slide {
        padding: 0 5px;
        cursor: pointer;
    }
    .slick-slider:last-of-type img {
        opacity: 0.6;
    }
    .slick-slider:last-of-type img:hover {
        opacity: 1;
    }
    @media screen and (max-width: 991px) {
        .slick-slider .item .text h1 {
            font-size: 50px;
        }
        .slick-slider .item .text {
            width: 53%;
            padding: 60px 0 0 40px;
        }
        .slick-slider:last-of-type {
            width: 400px;
        }
    }
    @media screen and (max-width: 767px) {
        .slick-slider .item .text h1 {
            font-size: 36px;
        }
    }
    @media screen and (max-width: 575px) {
        .slick-slider .item .text h1 {
            font-size: 24px;
        }
        .slick-slider .item .text p {
            display: none;
        }
        .slick-slider .item .text {
            width: 53%;
            padding: 20px 0 0 20px;
        }
        .slick-slider:last-of-type {
            width: 280px;
            bottom: 20px;
        }
    }
</style>