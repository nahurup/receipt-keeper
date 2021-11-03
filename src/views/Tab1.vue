<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Inicio</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <!-- Searchbar with value -->
      <ion-searchbar placeholder="Buscar"></ion-searchbar>
        <ion-list>
          <ion-item>
            <ion-icon slot="end" :icon="trashOutline"></ion-icon>
            <ion-label>Filtrar:</ion-label>
          </ion-item>
          <ion-card-content>
            <ion-chip color="danger">
              <ion-icon :icon="heart"></ion-icon>
              <ion-label>Favoritos</ion-label>
            </ion-chip>
            <ion-chip outline color="danger">
              <ion-icon :icon="heartOutline"></ion-icon>
              <ion-label>Favoritos</ion-label>
            </ion-chip>
            <ion-chip outline color="secondary">
              <ion-icon :icon="pricetagOutline"></ion-icon>
              <ion-label>tag1</ion-label>
            </ion-chip>
            <ion-chip outline color="tertiary">
              <ion-icon :icon="pricetagOutline"></ion-icon>
              <ion-label>tag2</ion-label>
            </ion-chip>
            <ion-chip outline color="warning">
              <ion-icon :icon="pricetagOutline"></ion-icon>
              <ion-label>tag3</ion-label>
            </ion-chip>
            <ion-chip color="secondary">
              <ion-icon :icon="pricetag"></ion-icon>
              <ion-label>tag1</ion-label>
            </ion-chip>
            <ion-chip color="tertiary">
              <ion-icon :icon="pricetag"></ion-icon>
              <ion-label>tag2</ion-label>
            </ion-chip>
            <ion-chip color="warning">
              <ion-icon :icon="pricetag"></ion-icon>
              <ion-label>tag3</ion-label>
            </ion-chip>
          </ion-card-content>
        </ion-list>

      <ion-grid>
        <ion-row>
          <ion-col>
            <ion-card @click="presentActionSheet">
              <img src="https://picsum.photos/200/300" />
              <ion-card-header>
                <ion-card-title>Nombre recibo</ion-card-title>
                <ion-card-subtitle>tag1, tag2, tag3</ion-card-subtitle>
              </ion-card-header>
            </ion-card>
            <ion-card @click="presentActionSheet">
              <img src="https://picsum.photos/200/300" />
              <ion-card-header>
                <ion-card-title>Nombre recibo</ion-card-title>
                <ion-card-subtitle>tag1, tag2, tag3</ion-card-subtitle>
              </ion-card-header>
            </ion-card>
          </ion-col>
          <ion-col>
            <ion-card @click="presentActionSheet">
              <img src="https://picsum.photos/200/300" />
              <ion-card-header>
                <ion-card-title>Nombre recibo</ion-card-title>
                <ion-card-subtitle>tag1, tag2, tag3</ion-card-subtitle>
              </ion-card-header>
            </ion-card>
            <ion-card @click="presentActionSheet">
              <img src="https://picsum.photos/200/300" />
              <ion-card-header>
                <ion-card-title>Nombre recibo</ion-card-title>
                <ion-card-subtitle>tag1, tag2, tag3</ion-card-subtitle>
              </ion-card-header>
            </ion-card>
          </ion-col>
        </ion-row>
      </ion-grid>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonSearchbar, IonCard, IonCardHeader, IonCardSubtitle, IonCardTitle, IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonLabel } from '@ionic/vue';
import { actionSheetController } from '@ionic/vue';
import { defineComponent } from 'vue';
import { folderOpen, trashOutline, caretForwardCircle, close, heart, trash, share, checkmarkCircle, pricetag, heartOutline, pricetagOutline } from 'ionicons/icons';


export default defineComponent({
  components: { IonSearchbar, IonCard, IonCardHeader, IonCardSubtitle, IonCardTitle, IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonLabel },
  setup() {
    return { checkmarkCircle,
      heart,
      heartOutline,
      pricetagOutline,
      pricetag,
      trashOutline,
      folderOpen }
  },
  methods: {
    async presentActionSheet() {
      const actionSheet = await actionSheetController
        .create({
          header: 'Nombre recibo',
          cssClass: 'my-custom-class',
          buttons: [
            {
              text: 'Borrar',
              role: 'destructive',
              icon: trash,
              handler: () => {
                console.log('Delete clicked')
              },
            },
            {
              text: 'Compartir',
              icon: share,
              handler: () => {
                console.log('Share clicked')
              },
            },
            {
              text: 'Abrir',
              icon: folderOpen,
              handler: () => {
                console.log('Play clicked')
              },
            },
            {
              text: 'Favorito',
              icon: heart,
              handler: () => {
                console.log('Favorite clicked')
              },
            },
            {
              text: 'Cancelar',
              icon: close,
              role: 'cancel',
              handler: () => {
                console.log('Cancel clicked')
              },
            },
          ],
        });
      await actionSheet.present();

      const { role } = await actionSheet.onDidDismiss();
      console.log('onDidDismiss resolved with role', role);
    },
  },
});
</script>

<style scoped>
  ion-card {
    margin: 0 !important;
  }
</style>