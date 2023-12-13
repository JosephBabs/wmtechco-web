<template>
    <section class="home-slider-area slider-default">
        <div class="home-slider-content">
            <div class="home-slider-container">
                <swiper
                    :speed="1000"
                    :navigation="swiperOptions.navigation"
                    :effect="'fade'"
                    :loop="true"
                >
                    <!-- Start Slide Item -->
                    <swiper-slide class="home-slider-item" :style="{ backgroundImage: `url('/images/slider/bg1.jpg')` }">
                        <div class="slider-content-area">
                            <div class="content">
                                <div class="subtitle-content">
                                    <img src="/images/shape/line1.png" alt="Images">
                                    <h6>Welcome to WMTECHCO:</h6>
                                </div>
                                <div class="tittle-wrp">
                                    <h2>
                                         Your Partner in <span>Tech Innovation</span></h2>
                                </div>
                                <p>
                                    we transcend boundaries to bring you unparalleled technology solutions and cutting-edge graphic services.</p>
                                <nuxt-link to="/service" class="btn btn-theme btn-theme-color2">All Services <i class="icon icofont-long-arrow-right"></i></nuxt-link>
                            </div>
                            <div class="layer-style">
                                <div class="thumb">
                                    <img src="/images/slider/1.jpg" alt="Images">
                                </div>
                                <div class="success-rate"><div class="content">98% <span>Successful Project</span></div></div>
                                <div class="trusted-clients-content">
                                    <span>Trusted <br>Clients</span>
                                    <ul class="clients-list">
                                        <li><img src="/images/testimonial/clients1.png" alt="Images"></li>
                                        <li><img src="/images/testimonial/clients2.png" alt="Images"></li>
                                        <li><img src="/images/testimonial/clients3.png" alt="Images"></li>
                                        <li><img src="/images/testimonial/clients4.png" alt="Images"> <span>6</span></li>
                                    </ul>
                                </div>
                                <div class="shape-style1">
                                    <img src="/images/shape/1.png" alt="Images">
                                </div>
                                <div class="shape-style2">
                                    <img src="/images/shape/2.png" alt="Images">
                                </div>
                                <div class="shape-style3">
                                    <img src="/images/shape/3.png" alt="Images">
                                </div>
                                <div class="shape-style4">
                                    <img src="/images/shape/4.png" alt="Images">
                                </div>
                                <div class="shape-style5">
                                    <img src="/images/shape/5.png" alt="Images">
                                </div>
                            </div>
                        </div>
                    </swiper-slide>
                    <!-- End Slide Item -->
                    <!-- Start Slide Item -->
                    <swiper-slide class="home-slider-item" :style="{ backgroundImage: `url('/images/slider/bg1.jpg')` }">
                        <div class="slider-content-area">
                            <div class="content">
                                <div class="subtitle-content">
                                    <img src="/images/shape/line1.png" alt="Images">
                                    <h6>Welcome to WMTECHCO:</h6>
                                </div>
                                <div class="tittle-wrp">
                                    <h2> Your Partner in <span>Tech Innovation .</span></h2>
                                </div>
                                <p>we transcend boundaries to bring you unparalleled technology solutions and cutting-edge graphic services.</p>
                                <nuxt-link to="/service" class="btn btn-theme btn-theme-color2">All Services <i class="icon icofont-long-arrow-right"></i></nuxt-link>
                            </div>
                            <div class="layer-style">
                                <div class="thumb">
                                    <img src="/images/slider/2.jpg" alt="Images">
                                </div>
                                <div class="success-rate"><div class="content">85% <span>Successful Project</span></div></div>
                                <div class="trusted-clients-content">
                                    <span>Trusted <br>Clients</span>
                                    <ul class="clients-list">
                                        <li><img src="/images/testimonial/clients1.png" alt="Images"></li>
                                        <li><img src="/images/testimonial/clients2.png" alt="Images"></li>
                                        <li><img src="/images/testimonial/clients3.png" alt="Images"></li>
                                        <li><img src="/images/testimonial/clients4.png" alt="Images"> <span>6+</span></li>
                                    </ul>
                                </div>
                                <div class="shape-style1">
                                    <img src="/images/shape/1.png" alt="Images">
                                </div>
                                <div class="shape-style2">
                                    <img src="/images/shape/2.png" alt="Images">
                                </div>
                                <div class="shape-style3">
                                    <img src="/images/shape/3.png" alt="Images">
                                </div>
                                <div class="shape-style4">
                                    <img src="/images/shape/4.png" alt="Images">
                                </div>
                                <div class="shape-style5">
                                    <img src="/images/shape/5.png" alt="Images">
                                </div>
                            </div>
                        </div>
                    </swiper-slide>
                    <!-- End Slide Item -->
                </swiper>
                <!-- Add Arrows -->
                <div class="swiper-button-next">
                    <i class="icofont-rounded-double-right"></i>
                </div>
                <div class="swiper-button-prev">
                    <i class="icofont-rounded-double-left"></i>
                </div>
            </div>
        </div>
        <div class="home-slider-sidebar" data-aos="fade-zoom-in" data-aos-duration="1300">
            <div class="social-icon">
                <a href="#"><i class="icofont-facebook"></i></a>
                <a href="#"><i class="icofont-skype"></i></a>
                <a href="#"><i class="icofont-twitter"></i></a>
            </div>
        </div>
    </section>
</template>

<script>
    import { Swiper, SwiperSlide } from "swiper/vue"
    import SwiperCore, { Navigation, EffectFade } from 'swiper/core'
    SwiperCore.use([Navigation, EffectFade])

    export default {
        components: {
            Swiper,
            SwiperSlide
        },
        data() {
            return {
                swiperOptions: {
                    navigation: {
                        nextEl: '.home-slider-container .swiper-button-next',
                        prevEl: '.home-slider-container .swiper-button-prev',
                    }
                }
            }
        },
    };
</script>
