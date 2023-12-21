<template>
    <section class="service-area">
        <div class="container">
            <div class="row icon-box-style1">
                <div class="col-md-6 col-lg-4" data-aos="fade-up" data-aos-duration="1100" v-for="(service, index) in services" :key="index">
                    <ServiceItem :id="service.id" :title="service.libelle_service" :desc="service.service_description" :icon="service.icon_service" />
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