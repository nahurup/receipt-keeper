<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Agregar Recibo</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-list>
        <ion-item>
          <ion-label>Nombre:</ion-label>
          <ion-input placeholder="Recibo de extraccion..." type="text"></ion-input>
        </ion-item>
        <ion-item-divider>
          <ion-label>Selecciona las fotos:</ion-label>
        </ion-item-divider>
        <ion-card-content>
          <ion-button color="success" shape="round" size="medium">
            <input id="uploadBtn" type="file" class="upload" />
          </ion-button>
        </ion-card-content>
        <ion-card-content>
          <div>
            Progress: 30/100%
            <ion-progress-bar value="30/100"></ion-progress-bar>
          </div>
          <div>
            File Size: 230 bytes Transfered:
            100 bytes
          </div>
        </ion-card-content>


        <ion-item>
          <ion-label>Fecha</ion-label>
          <ion-datetime value="1990-02-20" placeholder="Select Date"></ion-datetime>
        </ion-item>
        <ion-list-header>Categorias:</ion-list-header>
        <ion-item>
          <ion-label>Tag1</ion-label>
          <ion-checkbox color="primary" checked slot="start"></ion-checkbox>
        </ion-item>
        <ion-item>
          <ion-checkbox color="dark" checked slot="start"></ion-checkbox>
          <ion-label>Tag2</ion-label>
        </ion-item>
        <ion-item>
          <ion-checkbox color="secondary" slot="start"></ion-checkbox>
          <ion-label>Tag3</ion-label>
        </ion-item>
        <ion-item>
          <ion-checkbox color="danger" checked slot="start"></ion-checkbox>
          <ion-label>Tag4</ion-label>
        </ion-item>
      </ion-list>
      
      <div class="save-button-container">
        <ion-button color="secondary" float-right @click="openToast">Guardar</ion-button>
      </div>
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
  name: 'Tab2',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage },
  methods: {
    async openToast() {
      const toast = await toastController
        .create({
          message: 'El recibo ha sido guardado con exito.',
          duration: 2000,
          position: 'bottom'
        })
      return toast.present();
    },
  },
}
</script>

<style scoped>
.save-button-container {
  float: right;
  padding-right: 6px;
}
</style>