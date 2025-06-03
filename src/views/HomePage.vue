<template>
  <IonPage>
    <IonContent class="ion-padding">
      <IonSegment v-model="activeSegment">
        <IonSegmentButton value="page-a">Page A</IonSegmentButton>
        <IonSegmentButton value="page-b">Page B</IonSegmentButton>
        <IonSegmentButton value="page-c">Page C</IonSegmentButton>
      </IonSegment>

      <KeepAlive>
        <component :is="currentPage" />
      </KeepAlive>
    </IonContent>
  </IonPage>
</template>

<script setup lang="ts">
import { computed, ref } from "vue";
import { IonPage, IonContent, IonSegment, IonSegmentButton } from "@ionic/vue";
import PageA from "@/views/PageA.vue";
import PageB from "@/views/PageB.vue";
import PageC from "@/views/PageC.vue";

const activeSegment = ref<"page-a" | "page-b" | "page-c">("page-a");

const pages = {
  "page-a": PageA,
  "page-b": PageB,
  "page-c": PageC,
};

const currentPage = computed(() => pages[activeSegment.value]);
</script>
