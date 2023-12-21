<template>
  <div class="icon-box-item">
    <div class="icon-box">
      <img class="icon-img" src="/images/icons/s1.png" alt="Icon" />
    </div>
    <div class="content">
      <div class="separator-line">
        <img src="/images/shape/line-s1.png" alt="Image" />
      </div>
      <h4>{{ title }}</h4>
      <p>{{ desc }}</p>
      <nuxt-link :to="'/packs-details?pack=' + id" class="btn-link"
        >Read More <i class="icon icofont-arrow-right"></i
      ></nuxt-link>
    </div>
    <div class="icon-shape">
      <img class="shape-img1" src="/images/shape/s1.png" alt="Icon" />
      <img class="shape-img2" src="/images/shape/s2.png" alt="Icon" />
      <img class="shape-img3" src="/images/shape/s3.png" alt="Icon" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    id: {
      type: Number, // Change the type to Number
      required: true, // Add this line if the id is required
    },
    title: {
      type: String,
      required: true,
    },
    desc: {
      type: String,
      required: true,
    },
    icon: {
      type: String,
      required: true,
    },
  },
};
</script>
