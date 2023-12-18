<template>
    <section class="service-details-area">
        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <div class="service-details-column">
                        <div class="service-details-content">
                            <div class="thumb" data-aos="fade-up" data-aos-duration="1000">
                                <img src="/images/photos/service1.jpg" alt="image">
                            </div>
                            <nuxt-link to="/service" class="category">{{PackDetail.libelle_pack}}</nuxt-link>
                            <h2 class="title">{{PackDetail.libelle_pack}}</h2>
                            <div class="separator-line">
                                <img class="me-1" src="/images/shape/line-s2.png" alt="shape image">
                                <img src="/images/shape/line-s1.png" alt="shape image">
                            </div>
                            <!-- <p v-html="Pa"></p> -->
                            
                            <h2 class="title">Services in this pack</h2>
                            <div class="separator-line">
                                <img class="me-1" src="/images/shape/line-s2.png" alt="shape image">
                                <img src="/images/shape/line-s1.png" alt="shape image">
                            </div>
                            <ul class="list-style2">
                                <li v-for="service in PackDetail.pack_service" :key="service.id"><span class="icon"><i class="icofont-checked"></i></span> <span>{{service.libelle_service}}</span></li>
                            </ul>
                            <p class="mb-34">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry' standard dummy text ever since the 1500s, whean an unknown printer took an galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It wass popularsed in the 1960s with the release of Letraset sheets containing passages, and more recently.</p>
                            <h2 class="title">Find Solution.</h2>
                            <div class="separator-line">
                                <img class="me-1" src="/images/shape/line-s2.png" alt="shape image">
                                <img src="/images/shape/line-s1.png" alt="shape image">
                            </div>
                        </div>
                        
                        <!-- <div class="sidebar-area">
                            <ServiceCategoryWidget />

                            <WidgetVideo />

                            <WidgetSocial />
                        </div> -->

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
      PackDetail: {},
    };
  },
  methods: {

    reloadPage() {
      location.reload(); // Reload the page
    },

      async getData() {
        const apiLink = data.apiUrl.packs_details_api_link;
        
        const res = await fetch(apiLink+this.$route.query.pack);
        const finalRes = await res.json();
        console.log(finalRes.pack);
        const post = finalRes.pack; // Assuming post is an object with properties

        this.PackDetail = post;
        this.$emit('updatePageTitle', { title: post.libelle_pack, breadcrumbTitle: post.libelle_pack });
   
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