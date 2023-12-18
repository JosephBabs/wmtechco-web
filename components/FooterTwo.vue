<template>
    <footer class="footer-area bg-img-cover" :style="{ backgroundImage: `url('/images/photos/bg-footer.jpg')` }">
        <div class="container" data-aos="fade-up" data-aos-duration="1000">
            <div class="row">
                <div class="col-md-9 col-lg-4 col-xl-4">
                    <div class="widget-item mt-0">
                        <div class="about-widget">
                            <nuxt-link to="/" class="footer-logo">
                                <img src="/images/logo/logo.png" alt="Logo">
                            </nuxt-link>
                            <p>
                                At WMTECHCO, we transcend boundaries to bring you unparalleled technology solutions and cutting-edge graphic services. As a premier tech consulting company, we stand at the intersection of innovation and excellence, dedicated to shaping a digital future that redefines possibilities.
                                
                            </p>
                            <div class="widget-newsletter">
                                <form>
                                    <input type="email" class="form-control" placeholder="Enter your email">
                                    <button type="submit" class="btn btn-theme">
                                        Subscribe Now <i class="icon icofont-long-arrow-right"></i>
                                    </button>
                                </form>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-md-8 col-lg-6 col-xl-6">
                    <div class="widget-item menu-wrap-two-column">
                        <h4 class="widget-title">All Services</h4>
                        <img class="line-shape" src="/images/shape/line-s1.png" alt="shape">
                        <nav class="widget-menu-wrap">
                            <div class="row">
                                <div class="col-md-6">
                                    <ul class="nav-menu nav">
                                        <li><nuxt-link to="/service-details">Business Management</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Web Development</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Business Consultation</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Digital Marketing</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Brand Identity</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Insurance & Banking</nuxt-link></li>
                                    </ul>
                                </div>
                                <div class="col-md-6">
                                    <ul class="nav-menu nav">
                                        <li><nuxt-link to="/service-details">Website Optimization</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Social Media Marketing</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Link Building Services</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Pay Per Click Advertising</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Search Engine Marketing</nuxt-link></li>
                                        <li><nuxt-link to="/service-details">Content Marketing</nuxt-link></li>
                                    </ul>
                                </div>
                            </div>
                        </nav>
                    </div>
                </div>
                <div class="col-md-4 col-lg-2 col-xl-2 lg-pr-0">
                    <div class="widget-item menu-wrap-column">
                        <h4 class="widget-title">Useful Links</h4>
                        <img class="line-shape" src="/images/shape/line-s1.png" alt="Virtuf-HasTech">
                        <nav class="widget-menu-wrap">
                            <ul class="nav-menu nav">
                                <li><nuxt-link to="/">Group Profile</nuxt-link></li>
                                <li><nuxt-link to="/">Vision & Values</nuxt-link></li>
                                <li><nuxt-link to="/">Company History</nuxt-link></li>
                                <li><nuxt-link to="/">Careers</nuxt-link></li>
                                <li><nuxt-link to="/">Winning Awards</nuxt-link></li>
                                <li><nuxt-link to="/">Sustainability</nuxt-link></li>
                            </ul>
                        </nav>
                    </div>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <div class="container">
                <div class="footer-bottom-content">
                    <div class="row align-items-center">
                        <div class="col-md-6 order-2 order-md-1">
                            <div class="widget-copyright">
                                <p> &copy; {{ new Date().getFullYear() }} Allright Reserved. Designed by 
                            <a href="https://www.wmtechco.com">WMTECHCO</a>
                        </p>
                    </div>
                        </div>
                        <div class="col-md-6 order-1 order-md-2">
                            <div class="widget-social-icons">
                                <a href="#"><i class="icofont-facebook"></i></a>
                                <a href="#"><i class="icofont-skype"></i></a>
                                <a href="#"><i class="icofont-instagram"></i></a>
                                <a href="#"><i class="icofont-twitter"></i></a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
    export default {

    };
</script>