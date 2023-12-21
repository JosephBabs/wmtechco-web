<template>
    <div class="service-details-page-wrapper">
        <Header />
        <OffCanvasMobileMenu />
        <PageTitle :title="pageTitleData.title" :breadcrumbTitle="pageTitleData.breadcrumbTitle" />
    <PackDetailsWrapper @updatePageTitle="updatePageTitle" />
        <ContactDevider />
        <Footer />
    </div>
</template>

<script>
    export default {
   data() {
    return {
      pageTitleData: {
        title: '',
        breadcrumbTitle: 'loading pack details....',
      },
    };
  },
  methods: {
    updatePageTitle({ title, breadcrumbTitle }) {
      this.pageTitleData.title = title;
      this.pageTitleData.breadcrumbTitle = breadcrumbTitle;
    },
  },
        components: {
            Header: () => import('@/components/Header'),
            OffCanvasMobileMenu: () => import('@/components/OffCanvasMobileMenu'),
            PageTitle: () => import('@/components/PageTitle'),
            PackDetailsWrapper: () => import('@/components/PackDetailsWrapper'),
            ContactDevider: () => import('@/components/ContactDevider'),
            Footer: () => import('@/components/Footer'),
        },
    };
</script>


