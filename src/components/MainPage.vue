<template>
  <div class="main-page" v-if="!mobile">
    <UpperLogos/>
    <CatalogueBod/>
    <CurrentHeats/>
  </div>
  <div v-else>
    <MobilePage/>
  </div>
</template>

<script>
import UpperLogos from "@/components/UpperLogos";
import CatalogueBod from "@/components/Catalogue";
import CurrentHeats from "@/components/CurrentHeats";
import MobilePage from "@/components/MobilePage";
export default {
  name: "MainPage",
  components: {MobilePage, CurrentHeats, CatalogueBod, UpperLogos},
  data() {
    return {
      mobile: false
    }
  },
  onResize() {
    this.mobile = window.innerWidth < 768
  },
  created() {
    window.addEventListener('resize', this.onResize);
    this.onResize();
  },
  unmounted() {
    window.removeEventListener('resize', this.onResize)
  },
  methods: {
    onResize() {
      this.mobile = window.innerWidth < 768
    }
  }
}
</script>

<style scoped>
#app {
  display: flex;
  justify-content: center;
  overflow-x: scroll;
}
  .main-page {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-width: 1440px;
    margin-bottom: 57px;
  }
</style>