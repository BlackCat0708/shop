<template lang="pug">
#home
  b-container
    b-row
      b-col(cols='12')
        h1.text-center.font-weight-bold.text-success 熱門商品
      b-col(cols='12' md='6' lg="4" v-for='product in products' :key='product.id')
        ProductCard(:product='product')

</template>

<script>
import ProductCard from '@/components/ProductCard.vue'

export default {
  components: {
    ProductCard
  },
  computed: {
    products () {
      return this.$store.state.products.slice(0, 3)
    }
  }
}
</script>
