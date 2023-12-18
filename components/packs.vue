<template>
    <section class="service-area service-default-area">
        <div class="container">
            <div class="row">
                <div class="col-lg-8 col-xl-6 m-auto">
                    <div class="section-title text-center" data-aos="fade-up" data-aos-duration="1000">
                        <h2 class="title">OUR PACKS</h2>
                        <div class="separator-line mt-14">
                            <img class="me-1" src="/images/shape/line-s2.png" alt="Images">
                            <img src="/images/shape/line-s1.png" alt="Images">
                        </div>
                        
                    </div>
                </div>
            </div>
            <div class="row icon-box-style1">
                <div class="col-md-6 col-lg-4" data-aos="fade-up" data-aos-duration="1100" v-for="packs in packs.slice(0, 3)" :key="packs.id">
                    <ServicePacks :id="packs.id" :title="packs.libelle_pack" :desc="packs.libelle_pack" />
                </div>
            </div>

            <!-- <p>{{  packs }}</p> -->
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
                packs: [],
            }
        },
    methods: {
      async getDatas() {
        const packsApiLink = data.apiUrl.packs_api_link;
        
        const res = await fetch(packsApiLink);
        const finalRes = await res.json();
        this.packs = finalRes.packs;
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