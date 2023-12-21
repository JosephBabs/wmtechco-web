<template>
    <div class="blog-page-wrapper">
        <Header />
        <OffCanvasMobileMenu />
        <!-- <PageTitle title="Finding The Best Business Solution." breadcrumbTitle="Blog" />
        <BlogDetailsWrapper /> -->
        
        <PageTitle :title="pageTitleData.title" :breadcrumbTitle="pageTitleData.breadcrumbTitle" />
        <BlogDetailsWrapper @updatePageTitle="updatePageTitle" />
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
            BlogDetailsWrapper: () => import('@/components/BlogDetailsWrapper'),
            ContactDevider: () => import('@/components/ContactDevider'),
            Footer: () => import('@/components/Footer'),
        }
    };
</script>


