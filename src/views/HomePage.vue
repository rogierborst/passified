<template>
    <ion-page>
        <ion-header :translucent="true">
            <ion-toolbar>
                <ion-title class="p-3">Passified</ion-title>
            </ion-toolbar>
        </ion-header>

        <ion-content :fullscreen="true">
            <ion-header collapse="condense">
                <ion-toolbar>
                    <ion-title size="large">Passified!</ion-title>
                </ion-toolbar>
            </ion-header>

            <div id="container">
                <ion-grid>
                    <ion-row>
                        <ion-col size="6" v-for="photo in photos" :key="photo.filepath">
                            <ion-img :src="photo.webviewPath"></ion-img>
                        </ion-col>
                    </ion-row>
                </ion-grid>

                <strong class="text-amber-500">Shiiiit!</strong>
                <ion-fab-button @click="takePhoto()">
                    <ion-icon :icon="camera"></ion-icon>
                </ion-fab-button>
            </div>
        </ion-content>
    </ion-page>
</template>

<script setup lang="ts">
import { camera } from 'ionicons/icons';
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonIcon, IonFabButton } from '@ionic/vue';
import { usePhotoGallery, UserPhoto } from '@/composables/usePhotoGallery';

const { photos, takePhoto } = usePhotoGallery();
</script>

<style scoped>
#container {
    text-align: center;

    position: absolute;
    left: 0;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
}

#container strong {
    font-size: 20px;
    line-height: 26px;
}

#container p {
    font-size: 16px;
    line-height: 22px;

    color: #8c8c8c;

    margin: 0;
}

#container a {
    text-decoration: none;
}
</style>
