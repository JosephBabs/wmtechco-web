<template>
    <div class="service-page-wrapper">
        <Header />
        <OffCanvasMobileMenu />
        <PageTitle title="Service Checkout" breadcrumbTitle="Service Checkout" />
        <ServicesCheckout />
        <ContactDevider />
        <Footer />
    </div>
</template>

<script>
    export default {
        components: {
            Header: () => import('@/components/Header'),
            OffCanvasMobileMenu: () => import('@/components/OffCanvasMobileMenu'),
            PageTitle: () => import('@/components/PageTitle'),
            ServicesCheckout: () => import('@/components/ServicesCheckout'),
            ContactDevider: () => import('@/components/ContactDevider'),
            Footer: () => import('@/components/Footer'),
        },

        
    };
</script>


