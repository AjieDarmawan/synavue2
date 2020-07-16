<template>
  <div class="home">
      <HeaderSyana/>
      <HeroSyana/>
      <BannerSyana/>
      <InstaSyana/>
      <PartnerSyana/>
      <FooterSyana/>
      
  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from '@/components/HelloWorld.vue'
import HeaderSyana from '@/components/headerSyana.vue'
import HeroSyana from '@/components/heroSyana.vue'
import BannerSyana from '@/components/bannerSyana.vue'
import InstaSyana from '@/components/instaSyana.vue'
import PartnerSyana from '@/components/partnerSyana.vue'
import FooterSyana from '@/components/footerSyana.vue'



export default {
  name: 'Home',
  components: {
   HeaderSyana,
   HeroSyana,
   BannerSyana,
   InstaSyana,
   PartnerSyana,
   FooterSyana

  }
}
</script>
