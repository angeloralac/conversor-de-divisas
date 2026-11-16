<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="primary">
        <ion-title>DivisApp 1210086</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
      <div style="display: flex; flex-direction: column; gap: 1rem; margin-top: 2rem;">
        <ion-input
          v-model.number="quetzales"
          type="number"
          label="Cantidad en Quetzales (Q)"
          label-placement="floating"
          fill="outline"
          placeholder="1210086"
        ></ion-input>

        <ion-card>
          <ion-card-header>
            <ion-card-subtitle>Equivalente en Dólares ($)</ion-card-subtitle>
            <!-- Limitamos a 2 decimales para que se vea limpio -->
            <ion-card-title>${{ dolares.toFixed(2) }}</ion-card-title> 
          </ion-card-header>
        </ion-card>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup>
import { ref, computed } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonInput, IonCard, IonCardHeader, IonCardSubtitle, IonCardTitle } from '@ionic/vue';

const quetzales = ref(0);

// Tasa de conversión: 8 GTQ = 1 USD
const dolares = computed(() => {
  return quetzales.value / 8;
});
</script>
