<template>
    <section class="blog-area blog-default-area">
        <div class="container">
            <div class="row">
                <div class="col-lg-6 m-auto">
                    <div class="section-title text-center" data-aos="fade-up" data-aos-duration="1000">
                        <h2 class="title">Journey Through Ideas</h2>
                        <div class="separator-line mt-14">
                            <img class="me-1" src="/images/shape/line-s2.png" alt="image">
                            <img src="/images/shape/line-s1.png" alt="image">
                        </div>
                        <div class="desc">
                            <p class="mt-21">Explore a realm of thought-provoking articles</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="row " data-aos="fade-up" data-aos-duration="1100">
                <div class="col-md-6 col-lg-4" v-for="(blog, index) in blogs.slice(0, 3)" :key="index">
                    <div class="post-item mb-md-50">
                        <div class="thumb">
                            <nuxt-link to="/blog-details">
                                <img :src="blog.cover" :alt="blog.title">
                            </nuxt-link>
                            <div class="meta">
                                <nuxt-link to="/blog" class="post-date">{{ formatDate(blog.created_at) }}</nuxt-link>
                                <!-- <button class="post-comment"><i class="icofont-speech-comments"></i> {{ blog.comment }}</button>
                                <button class="post-like"><i class="icofont-heart"></i>{{ blog.like }}</button> -->
                            </div>
                        </div>
                        <div class="content">
                            <div class="category-inner">
                                <img src="/images/shape/line-s1.png" alt="image">
                                <!-- <nuxt-link to="/blog" class="category">{{ blog.category }}</nuxt-link> -->
                            </div>
                            <h4 class="title">
                                <nuxt-link to="/blog-details">{{ blog.title }}</nuxt-link>
                            </h4>
                            <!-- <p>{{ blog.excerpt }}</p> -->
                            <nuxt-link :to="'/blog-details?post=' + id" class="btn btn-theme btn-border btn-gray">
                                Read More <i class="icon icofont-long-arrow-right"></i>
                            </nuxt-link>
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
    }
    },
    mounted() {
      this.getData()
    },
    computed: {
    truncatedDescription(description) {
      if (description) {
        // Truncate the description to the first 100 characters
        return description.substring(0, 100);
      }
      // If the description is empty, you can provide a default value or handle it accordingly
      return "No description available";
    }
  }
    };
</script>
