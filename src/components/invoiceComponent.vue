<template>
  <div>
    <h1>Invoice</h1>
    <div class="subtotal">
        <label for="">Subtotal</label>
        <input type="number" v-model="subtotal">
    </div>

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

div {
  max-width: 400px;
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  background-color: #f9f9f9;
  text-align: center;
}

h1 {
  font-size: 24px;
  margin-bottom: 10px;
  color: #333;
}

label {
  display: block;
  font-weight: bold;
  margin-bottom: 5px;
  color: #555;
}

input {
  width: 100%;
  padding: 8px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 4px;
  text-align: center;
  margin-bottom: 15px;
}

h3 {
  font-size: 18px;
  color: #007bff;
}

.subtotal {
    display: flex;
    justify-items: center;
    align-items: center;
    gap: 10px;
}

</style>