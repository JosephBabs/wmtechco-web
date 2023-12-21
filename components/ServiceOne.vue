<template>
    <section class="service-area service-default-area">
        <div class="container">
            <div class="row">
                <div class="col-lg-8 col-xl-6 m-auto">
                    <div class="section-title text-center" data-aos="fade-up" data-aos-duration="1000">
                        <h2 class="title">What We Do?</h2>
                        <div class="separator-line mt-14">
                            <img class="me-1" src="/images/shape/line-s2.png" alt="Images">
                            <img src="/images/shape/line-s1.png" alt="Images">
                        </div>
                        <div class="desc">
                            <p class="mt-21">
                                <bold>WMTECHCO Tech Solutions:</bold>
                                <span><i class="">&#8595;</i></span>
                            </p>
                            <p class="mt-21">
                                Embark on a journey of technological transformation with our comprehensive suite of services. From custom software development to robust IT consulting, we are your go-to partner for turning your tech aspirations into reality.
                            </p>
                            <p class="mt-21">
                                <bold>WMTECHCO Graphical Brilliance: </bold>
                                <span><i class="">&#8595;</i></span>
                            </p>
                            <p class="mt-21">
                                Elevate your brand with visually stunning graphics that captivate and communicate. Our creative minds blend design expertise with artistic finesse, delivering impactful visuals that leave a lasting impression.
                            </p>        

                        </div>
                    </div>
                </div>
            </div>
            <div class="row icon-box-style1">
                <div class="col-md-6 col-lg-4" data-aos="fade-up" data-aos-duration="1100" v-for="service in services.slice(0, 3)" :key="service.id">
                    <ServiceItem :id="service.id" :title="service.libelle_service" :desc="service.service_description" :icon="service.icon_service" />
                </div>
            </div>

            <!-- <p>{{  services }}</p> -->
        </div>
        <div class="layer-shape">
            <img class="layer-shape-one" src="/images/shape/6.png" alt="shape">
            <img class="layer-shape-two" src="/images/shape/7.png" alt="shape">
        </div>
    </section>
</template>

<script>

import data from "~/data/data.json";
    export default {
        
        data() {
            return {
                services: [],
            }
        },
    methods: {
      async getDatas() {
        const ServiceApiLink = data.apiUrl.service_api_link;
        
        const res = await fetch(ServiceApiLink);
        const finalRes = await res.json();
        this.services = finalRes.services;
      },
      // formatDate(date) {
      // const options = { year: 'numeric', month: 'long', day: 'numeric' }
      // return new Date(date).toLocaleDateString('en', options)
    // },
  },
  mounted() {
      this.getDatas()
    },
    };
</script>