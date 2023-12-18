<template>
    <div class="service-page-wrapper">
        <Header />
        <OffCanvasMobileMenu />
        <PageTitle title="Packs" breadcrumbTitle="Packs" />
        <Packs />
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
            Packs: () => import('@/components/packs'),
            ContactDevider: () => import('@/components/ContactDevider'),
            Footer: () => import('@/components/Footer'),
        },

        
    };
</script>


