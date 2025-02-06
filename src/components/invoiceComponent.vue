<template>
  <div>
    <h1>Invoice</h1>
    <label for="">Subtotal</label>
    <input type="number" v-model="subtotal">

    <h3>Total impuestos a pagar: {{ totalIva }} € ({{ iva }}%)</h3>
  </div>
</template>

<script lang="ts" setup>

import { computed, Ref, ref } from 'vue';
    const iva = 21
    let subtotal:Ref<number> = ref(0)
    
    const totalIva = computed(() => (iva*subtotal.value / 100))

</script>

<style scoped>

</style>