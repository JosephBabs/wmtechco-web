<template>
    <section class="service-details-area">
        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <div class="service-details-column">
                        <div class="service-details-content">
                            <div class="thumb" data-aos="fade-up" data-aos-duration="1000">
                                <img :src="'https://app.wmtechco.com/storage/'+ServiceDetail.image_service" alt="image">
                            </div>
                            <nuxt-link to="/service" class="category">{{ServiceDetail.libelle_service}}</nuxt-link>
                            <h1 class="title">{{ServiceDetail.libelle_service}}</h1>
                            <div class="separator-line">
                                <img class="me-1" src="/images/shape/line-s2.png" alt="shape image">
                                <img src="/images/shape/line-s1.png" alt="shape image">
                            </div>
                            <h2 class="title">About this service</h2>
                            <div class="separator-line">
                                <img class="me-1" src="/images/shape/line-s2.png" alt="shape image">
                                <img src="/images/shape/line-s1.png" alt="shape image">
                            </div>
                            <p v-html="ServiceDetail.service_description"></p>
                            
                            

                            <!-- <p class="mb-0">{{ServiceDetail.libelle_service}}</p> -->
                            <!-- <ul class="list-style2">
                                <li><span class="icon"><i class="icofont-checked"></i></span> <span>Industry' standard dummy text ever since the type book.</span></li>
                                <li><span class="icon"><i class="icofont-checked"></i></span> <span>It is a long established fact that reader will be distracted content.</span></li>
                                <li><span class="icon"><i class="icofont-checked"></i></span> <span>Many desktop publishing packages and web page editors.</span></li>
                                <li><span class="icon"><i class="icofont-checked"></i></span> <span>Variou version have evolved over the year sometimes accident.</span></li>
                            </ul> -->
                            <p class="mb-34">
                                Throughout each service, we maintain open communication channels, ensuring clients are actively involved in the creative process and have ample opportunity for feedback and corrections. Our commitment is to deliver not just a service, but an experience that exceeds expectations.</p>
                            
                            <div class="separator-line">
                                <img class="me-1" src="/images/shape/line-s2.png" alt="shape image">
                                <img src="/images/shape/line-s1.png" alt="shape image">
                            </div>
                            <div class="row" >
                                
                                <div class="col-md-12" style="display: flex;
  justify-content: flex-end;">
                                <nuxt-link :to="'/service-checkout?service_id=' + this.$route.query.service +'&&service_name=' + ServiceDetail.libelle_service +'&&service_price='+ ServiceDetail.price_service" class="btn btn-success btn-lg" >
                                    Purchase Service 
                                    <i class="icon icofont-cart"></i>
                                </nuxt-link>
                            </div>
    </div>
                        </div>
                        
                        <div class="sidebar-area">
                            <!-- <ServiceCategoryWidget /> -->

                            <WidgetVideo />

                            <WidgetSocial />
                        </div>

                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

import data from "~/data/data.json";
    export default {
        components: {
            ServiceCategoryWidget: () => import('@/components/ServiceCategoryWidget'),
            WidgetVideo: () => import('@/components/WidgetVideo'),
            WidgetSocial: () => import('@/components/WidgetSocial'),
        },

        data() {
    return {
      ServiceDetail: {},
    };
  },
  methods: {

    reloadPage() {
      location.reload(); // Reload the page
    },

      async getData() {
        const apiLink = data.apiUrl.service_details_api_link;
        
        const res = await fetch(apiLink+this.$route.query.service);
        const finalRes = await res.json();
        console.log(finalRes.service);
        const post = finalRes.service; // Assuming post is an object with properties

        this.ServiceDetail = post;
        this.$emit('updatePageTitle', { title: post.libelle_service, breadcrumbTitle: post.libelle_service });
   
// Display specific properties in the alert
      // alert("Post Title: " + post.title);
      },

      
      formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    }
    }, 
    mounted() {
      this.getData()
      // Attach a click event listener to the <nuxt-link> element
    // const link = this.$el.querySelector('nuxt-link');
    // link.addEventListener('click', this.reloadPage); cma-B-nin-Web-main
    }
    };
</script>