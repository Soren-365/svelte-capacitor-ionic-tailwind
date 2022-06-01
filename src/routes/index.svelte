
<script lang="ts">


import { Camera, CameraResultType, CameraSource, type Photo } from '@capacitor/camera';
import { Filesystem, Directory } from '@capacitor/filesystem';
import { Storage } from '@capacitor/storage';
import { Capacitor } from '@capacitor/core';
import Photo from '$lib/components/Photo.svelte';

export function usePhotoGallery() {
  const takePhoto = async () => {
    const photo = await Camera.getPhoto({
      resultType: CameraResultType.Uri,
      source: CameraSource.Camera,
      quality: 100,
    });
  };

  return {
    takePhoto,
  };
}
const { takePhoto } = usePhotoGallery();

let photos: any[] = []

const handleClick = () => {
    alert("photo taken!")
    console.log("takes photo")
    photos.push(takePhoto())
 
}
</script>


<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<ion-button color="primary" on:click={()=> handleClick()}>Take Photo</ion-button>
   

<ion-content>
    <ion-grid>
      <ion-row>
        {#each photos as photo}
        <Photo photo={photo}/>
        {/each}

   
      </ion-row>
    </ion-grid>
  
  </ion-content>
