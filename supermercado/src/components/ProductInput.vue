<template>
  <!-- Componente de entrada de texto para el nombre del producto -->
  <ion-item>
    <ion-label position="stacked">{{ label }}</ion-label>
    <ion-input v-model="value" :placeholder="placeholder"></ion-input>
  </ion-item>
</template>

<script>
export default {
  name: 'ProductInput',
  props: {
    label: {
      type: String,
      default: 'Nombre del Producto'
    },
    placeholder: {
      type: String,
      default: 'Ingrese el nombre aquí...'
    },
    value: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>
ion-item {
  margin: 10px 0;
}
</style>
