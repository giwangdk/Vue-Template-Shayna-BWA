<template>
  <div class="home">
    <HeaderShayna/>
    <Hero/>
    <Banner/>
    <InstaShayna/>
    <PartnerLogo/>
    <Footer/>
  </div>
</template>

<script>
// // @ is an alias to /src


import HeaderShayna from "@/components/HeaderShayna.vue";
import Hero from "@/components/Hero.vue";
import Banner from "@/components/Banner.vue";
import InstaShayna from "@/components/InstaShayna.vue";
import PartnerLogo from "@/components/PartnerLogo.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "Home",
  components: {
    HeaderShayna,
    Hero,
    Banner,
    InstaShayna,
    PartnerLogo,
    Footer
  },
};
</script>
