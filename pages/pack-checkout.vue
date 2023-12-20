<template>
    <div class="service-page-wrapper">
        <Header />
        <OffCanvasMobileMenu />
        <PageTitle title="Pack Checkout" breadcrumbTitle="Pack Checkout" />
        <PacksCheckout />
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
            PacksCheckout: () => import('@/components/PacksCheckout'),
            ContactDevider: () => import('@/components/ContactDevider'),
            Footer: () => import('@/components/Footer'),
        },

        
    };
</script>


