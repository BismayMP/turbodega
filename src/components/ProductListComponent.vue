<template>
  <div class="card-list">
    <ProductCardComponent
      v-for="product in products"
      :key="product.id"
      :product="product"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import { Product } from './models';
import ProductCardComponent from 'components/ProductCardComponent.vue';

export default defineComponent({
  name: 'ProductList',
  components: { ProductCardComponent },
  props: {
    products: {
      type: Array as PropType<Product[]>,
      required: true,
    },
  },
  setup(props) {
    return { ...props };
  },
});
</script>
