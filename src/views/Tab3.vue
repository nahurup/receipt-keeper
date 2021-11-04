<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Cuenta</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-card style="box-shadow: none;">
        <ion-card-content>
          <ion-row class="ion-justify-content-center">
            <ion-avatar>
              <img src="https://picsum.photos/300/300">
            </ion-avatar>
          </ion-row>
            <ion-card-title class="ion-text-center" style="padding-top: 6px">Nahuel Ruppel</ion-card-title>
        </ion-card-content>
      </ion-card>

      <ion-list>
        <ion-list-header>
          Información
        </ion-list-header>
        <ion-item>
          <ion-label>Recibos guardados</ion-label>
          <ion-badge color="success" slot="end">80</ion-badge>
        </ion-item>

        <ion-item>
          <ion-label>Usuario</ion-label>
          <ion-note slot="end">nahurup</ion-note>
        </ion-item>
        <ion-item>
          <ion-label>Email</ion-label>
          <ion-note slot="end">nahuelruppel10@gmail.com</ion-note>
        </ion-item>
      </ion-list>

      <ion-card>
        <ion-card-header>
          <ion-card-title>Cambiar contraseña</ion-card-title>
        </ion-card-header>
        <ion-card-content>
          <ion-list>
            <ion-item>
              <ion-label>Contraseña actual:</ion-label>
              <ion-input type="password"></ion-input>
            </ion-item>

            <ion-item>
              <ion-label>Contraseña nueva:</ion-label>
              <ion-input type="password"></ion-input>
            </ion-item>
          </ion-list>
          <div class="save-button-container">
            <ion-button color="secondary" float-right @click="openToast">Guardar</ion-button>
          </div>
        </ion-card-content>
      </ion-card>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { 
  IonPage, 
  IonHeader, 
  IonToolbar, 
  IonTitle, 
  IonContent, 
  toastController 
} from '@ionic/vue';

export default  {
  name: 'Tab3',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage },
  methods: {
    async openToast() {
      const toast = await toastController
        .create({
          message: 'El cambio de contraseña fue exitoso.',
          duration: 2000,
          position: 'bottom'
        })
      return toast.present();
    },
  },
}
</script>

<style scoped>
ion-avatar  {
  width:100% !important;
  height : 100% !important;
  max-width: 100px !important;
  max-height: 100px !important;
}

.save-button-container {
  float: right;
  padding-right: 6px;
}
</style>