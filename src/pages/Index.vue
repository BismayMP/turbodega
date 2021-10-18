<template>
  <q-page class="row page-container">
    <UserWidget :name="`Yulisa Torres`" :venta="245.0"></UserWidget>
    <div class="product-list">
      <h4>Mis Productos</h4>
      <ProductList :products="list" />
    </div>
  </q-page>
</template>

<script lang="ts">
import UserWidget from 'components/UserComponent.vue';
import ProductList from 'components/ProductListComponent.vue';
import { defineComponent } from 'vue';

const productList = [
  {
    id: 1,
    name: 'Galleta de soda Field paquete 6 und',
    price: 2.3,
    available: 4,
    unit: 'unid',
    icon: 'school',
  },
  {
    id: 2,
    name: 'Arroz extra Costeño bolsa 5kg',
    price: 15.5,
    available: 8,
    unit: 'unid',
    icon: 'code',
  },
  {
    id: 3,
    name: 'Galleta de soda Field paquete 6 und',
    price: 2.3,
    available: 4,
    unit: 'unid',
    icon: 'school',
  },
  {
    id: 4,
    name: 'Arroz extra Costeño bolsa 5kg',
    price: 15.5,
    available: 8,
    unit: 'unid',
    icon: 'code',
  },
  {
    id: 5,
    name: 'Galleta de soda Field paquete 6 und',
    price: 2.3,
    available: 4,
    unit: 'unid',
    icon: 'school',
  },
  {
    id: 6,
    name: 'Arroz extra Costeño bolsa 5kg',
    price: 15.5,
    available: 8,
    unit: 'unid',
    icon: 'code',
  },
  {
    id: 7,
    name: 'Galleta de soda Field paquete 6 und',
    price: 2.3,
    available: 4,
    unit: 'unid',
    icon: 'school',
  },
  {
    id: 8,
    name: 'Arroz extra Costeño bolsa 5kg',
    price: 15.5,
    available: 8,
    unit: 'unid',
    icon: 'code',
  },
];

export default defineComponent({
  name: 'PageIndex',
  components: { UserWidget, ProductList },

  setup() {
    return { list: productList };
  },
});
</script>
