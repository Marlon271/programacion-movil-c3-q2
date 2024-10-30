<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Gestión de Supermercado</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true" class="ion-padding">
      
      <div class="welcome-container">
        <h2>¡Bienvenido al Supermercado!</h2>
        <p>Administra tus productos de supermercado de forma eficiente.</p>
      </div>
    
      <component-crud></component-crud>
      
    </ion-content>
  </ion-page>
</template>

<script setup>
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import ComponentCrud from '@/components/ComponentCrud.vue';
</script>

<style scoped>
.welcome-container {
  text-align: center;
  margin-top: 30px;
}

.welcome-container h2 {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

.welcome-container p {
  font-size: 16px;
  color: #666;
}

.ion-padding {
  padding: 20px;
}
</style>

