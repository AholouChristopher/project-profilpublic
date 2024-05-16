
<template>
  <div>
    <BarreNav/>
    <NuxtPage/>
    <Footer/>
  </div>
</template>

<script>
import BarreNav from '~/components/BarreNav.vue';
import Footer from './components/Footer.vue';

export default {
  components: {
    BarreNav,
    Footer
  }
}
</script>


<style scoped>
</style>
