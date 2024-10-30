<template>
  <ion-list>
    <product-input label="Producto" placeholder="Nombre del producto" v-model="formData.productName"/>
    <ion-item>
      <ion-label position="stacked">SKU</ion-label>
      <ion-input v-model="formData.sku" placeholder="Código SKU"></ion-input>
    </ion-item>
    <ion-item>
      <ion-label position="stacked">Precio (COP)</ion-label>
      <ion-input type="number" v-model="formData.price" placeholder="Precio en pesos"></ion-input>
    </ion-item>
    <ion-button expand="block" @click="submitForm">Guardar Producto</ion-button>
  </ion-list>
</template>

<script>
import ProductInput from './ProductInput.vue';

export default {
  name: 'ProductForm',
  components: { ProductInput },
  data() {
    return {
      formData: {
        productName: '',
        sku: '',
        price: ''
      }
    };
  },
  methods: {
    submitForm() {
      if (this.formData.productName && this.formData.sku && this.formData.price) {
        console.log('Producto guardado:', this.formData);
        this.clearForm();
      } else {
        console.log('Por favor, complete todos los campos.');
      }
    },
    clearForm() {
      this.formData = { productName: '', sku: '', price: '' };
    }
  }
}
</script>

<style scoped>
ion-item {
  margin-bottom: 10px;
}

ion-button {
  margin-top: 15px;
}
</style>
