<template>
  <div class="home">
    <ProductView/>
    <ProductCards/>
  </div>
</template>

<script>
import ProductView from '@/components/ProductView.vue'
import ProductCards from '@/components/ProductCards.vue'

export default {
  name: 'Home',
  components: {
    ProductView,
    ProductCards
  }
}
</script>

<style lang="scss" scoped>
  .home {
    display: flex;
    flex-flow: row nowrap;
    width: 100%;
  }
</style>
