<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Gestión de Productos</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
      <ion-list>

        
        <ion-item>
          <ion-label position="stacked">Producto</ion-label>
          <ion-input v-model="formData.productName" placeholder="Nombre del producto"></ion-input>
        </ion-item>

      
        <ion-item>
          <ion-label position="stacked">SKU</ion-label>
          <ion-input v-model="formData.sku" placeholder="Código SKU"></ion-input>
        </ion-item>

        
        <ion-item>
          <ion-label position="stacked">Stock</ion-label>
          <ion-input type="number" v-model="formData.stock" placeholder="Cantidad en stock"></ion-input>
        </ion-item>

       
        <ion-item>
          <ion-label position="stacked">Precio (COP)</ion-label>
          <ion-input type="number" v-model="formData.price" placeholder="Precio en pesos"></ion-input>
        </ion-item>

        
        <ion-item>
          <ion-label position="stacked">Descripción</ion-label>
          <ion-textarea v-model="formData.description" placeholder="Detalles del producto"></ion-textarea>
        </ion-item>

       
        <ion-item>
          <ion-label position="stacked">Categoría</ion-label>
          <ion-select v-model="formData.category" placeholder="Seleccionar">
            <ion-select-option value="Electrónica">Electrónica</ion-select-option>
            <ion-select-option value="Ropa">Ropa</ion-select-option>
            <ion-select-option value="Alimentos">Alimentos</ion-select-option>
          </ion-select>
        </ion-item>

        
        <ion-radio-group v-model="formData.status">
          <ion-list-header>
            <ion-label>Estado del Producto</ion-label>
          </ion-list-header>
          <ion-item>
            <ion-label>Activo</ion-label>
            <ion-radio slot="start" value="activo"></ion-radio>
          </ion-item>
          <ion-item>
            <ion-label>Inactivo</ion-label>
            <ion-radio slot="start" value="inactivo"></ion-radio>
          </ion-item>
        </ion-radio-group>

        
        <ion-item>
          <ion-label>Disponible en tienda</ion-label>
          <ion-toggle v-model="formData.isAvailable"></ion-toggle>
        </ion-item>

      </ion-list>

      
      <div class="button-container">
        <ion-button expand="block" @click="handleSave">Guardar</ion-button>
        <ion-button expand="block" color="medium" @click="handleCancel">Cancelar</ion-button>
      </div>
    </ion-content>
  </ion-page>
</template>

<script>
export default {
  name: 'ComponentCrud',
  data() {
    return {
      formData: {
        productName: '',
        sku: '',
        stock: '',
        price: '',
        description: '',
        category: '',
        status: '',
        isAvailable: false,
      }
    };
  },
  methods: {
    handleSave() {
      if (
        this.formData.productName &&
        this.formData.sku &&
        this.formData.stock &&
        this.formData.price &&
        this.formData.description &&
        this.formData.category &&
        this.formData.status
      ) {
        console.log('Datos del producto guardados:', this.formData);
        this.clearForm(); 
      } else {
        console.log('Por favor, completa todos los campos requeridos.');
      }
    },
    handleCancel() {
      this.clearForm();
    },
    clearForm() {
      this.formData = {
        productName: '',
        sku: '',
        stock: '',
        price: '',
        description: '',
        category: '',
        status: '',
        isAvailable: false,
      };
    }
  }
}
</script>

<style scoped>
ion-item {
  margin-bottom: 15px;
}

.button-container {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 20px;
}
</style>

