<template>
  <IonPage>
    <IonContent class="ion-padding">
      <IonSegment v-model="activeSegment">
        <IonSegmentButton value="page-a">Page A</IonSegmentButton>
        <IonSegmentButton value="page-b">Page B</IonSegmentButton>
        <IonSegmentButton value="page-c">Page C</IonSegmentButton>
      </IonSegment>

      <PageA v-if="activeSegment === 'page-a'" />
      <PageB v-else-if="activeSegment === 'page-b'" />
      <PageC v-else />
    </IonContent>
  </IonPage>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { IonPage, IonContent, IonSegment, IonSegmentButton } from "@ionic/vue";
import PageA from "@/views/UserPage/PageA.vue";
import PageB from "@/views/UserPage/PageB.vue";
import PageC from "@/views/UserPage/PageC.vue";

const activeSegment = ref("page-a");
</script>
