<template>
  <q-card class="my-card">
    <q-card-section horizontal>
      <div class="card-image" v-if="product?.icon" avatar>
        <q-icon :name="product?.icon" />
      </div>
      <q-card-section>
        <span style="opacity: 0.7;">{{ product?.name }}</span>
        <br />
        <span style="color: green; font-weight: bolder;"
          >S/ {{ product?.price }}</span
        >
        x
        {{ product?.unit }}
        <br />
        <span
          ><q-icon name="info" /> Disponible {{ product?.available }}
          {{ product?.unit }}</span
        >
      </q-card-section>
    </q-card-section>
  </q-card>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import { Product } from './models';

export default defineComponent({
  name: 'ProductCard',
  props: {
    product: {
      type: Object as PropType<Product>,
      required: true,
    },
  },
  setup(props) {
    return { ...props };
  },
});
</script>
