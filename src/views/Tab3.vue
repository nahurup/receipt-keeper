<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Cuenta</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-list-header>Default</ion-list-header>
      <ion-avatar class="ion-margin-start">
        <img src="https://picsum.photos/200/300">
      </ion-avatar>
      <ion-list>
        <ion-list-header>
          Items with Labels
        </ion-list-header>
        <ion-item>
          <ion-label>Label</ion-label>
        </ion-item>

        <ion-item>
          <ion-icon slot="end" name="logo-ionic"></ion-icon>
          <ion-label>Label with Icon</ion-label>
        </ion-item>
      </ion-list>

      <ion-item>
        <ion-label>Completed</ion-label>
        <ion-badge color="success" slot="end">80</ion-badge>
      </ion-item>

      <ion-list>
        <ion-list-header lines="full">
          <ion-label>
            Cambiar contraseña
          </ion-label>
        </ion-list-header>

        <ion-item>
          <ion-label>Contraseña actual:</ion-label>
          <ion-input type="password"></ion-input>
        </ion-item>

        <ion-item>
          <ion-label>Contraseña nueva:</ion-label>
          <ion-input type="password"></ion-input>
        </ion-item>
        </ion-list>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
export default  {
  name: 'Tab3',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage }
}
</script>