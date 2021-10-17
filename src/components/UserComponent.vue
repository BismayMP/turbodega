<template>
  <div class="user-component">
    <div class="user-data">
      <h4>Hola, {{ name }}</h4>
      <h5>Tu venta del dia es de S/ {{ venta.toFixed(2) }}</h5>
    </div>
    <div class="avatar">
      <q-avatar
        size="4rem"
        font-size="4rem"
        color="primary"
        text-color="white"
        icon="account_circle"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'UserWidget',
  props: {
    name: {
      type: String,
      required: true,
    },
    venta: {
      type: Number,
      default: 0,
    },
  },
});
</script>
