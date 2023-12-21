<template>
    <section class="blog-grid-area">
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <div class="blog-content-column">
                        <div class="blog-content-area post-items-style2">
                            <!--== Start Blog Post Item ==-->
                            <div class="post-item" data-aos="fade-up" data-aos-duration="1000" v-for="(blog, index) in blogs" :key="index">
                                <div class="thumb">
                                    <nuxt-link to="/blog-details">
                                        <img :src="blog.imgSrc" :alt="blog.title">
                                    </nuxt-link>
                                </div>
                                <div class="content">
                                    <div class="meta">
                                        <nuxt-link to="/blog" class="post-date">{{ formatDate(blog.created_at) }}</nuxt-link>
                                        <!-- <nuxt-link to="/blog" class="post-comment"><i class="icofont-speech-comments"></i>{{ blog.comment }}</nuxt-link>
                                        <nuxt-link to="/blog" class="post-like"><i class="icofont-heart"></i>{{ blog.like }}</nuxt-link> -->
                                        <nuxt-link to="/blog" class="post-author"><i class="icofont-user-alt-7"></i>{{ blog.author }}</nuxt-link>
                                    </div>
                                    <h4 class="title">
                                        <nuxt-link to="/blog-details">{{ blog.title }}</nuxt-link>
                                    </h4>
                                    <div class="separator-line">
                                        <img class="me-1" src="/images/shape/line-s2.png" alt="shape">
                                        <img src="/images/shape/line-s1.png" alt="shape">
                                    </div>
                                    <p v-html="blog.content.substring(0, 300)"></p>
                                    <nuxt-link :to="'/blog-details?post=' + blog.id" class="btn btn-theme btn-border btn-gray">Read More <i class="icon icofont-long-arrow-right"></i></nuxt-link>
                                </div>
                            </div>
                            <!--== End Blog Post Item ==-->

                            <!-- <Pagination /> -->
                        </div>

                        <div class="sidebar-area">
                            <WidgetSearch />

                            <!-- <ServiceCategoryWidget /> -->

                            <!-- <WidgetVideo /> -->

                            <WidgetSocial />

                            <!-- <WidgetRecentPost /> -->

                            <!-- <WidgetTags /> -->
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
        props: {
    desc: {
      type: String,
    //   required: true,
    },
    
    
  },
        components: {
            Pagination: () => import('@/components/Pagination'),
            WidgetSearch: () => import('@/components/WidgetSearch'), 
            ServiceCategoryWidget: () => import('@/components/ServiceCategoryWidget'),
            WidgetVideo: () => import('@/components/WidgetVideo'),
            WidgetSocial: () => import('@/components/WidgetSocial'),
            WidgetRecentPost: () => import('@/components/WidgetRecentPost'),
            WidgetTags: () => import('@/components/WidgetTags'),
        },

        data() {
            return {
                
                blogs: []
            }
        },
    methods: {
      async getData() {
        const apiLink = data.apiUrl.posts_api;
        
        const res = await fetch(apiLink);
        const finalRes = await res.json();
        this.blogs = finalRes.posts;
      },
      formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    },
    truncatedDescription(description) {
      if (description) {
        // Truncate the description to the first 100 characters
        return description.substring(0, 300);
      }
      // If the description is empty, you can provide a default value or handle it accordingly
      return "No description available";
    }
    },
    mounted() {
      this.getData()
    },
    computed: {
    
  }
    };
</script>