<template>
    <div id="webviewer" ref="viewer">
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted, defineProps } from 'vue';
  import WebViewer from "@pdftron/webviewer";
  
  // Definir las props esperadas
  const props = defineProps({
    initialDoc: {
      type: String
    }
  });
  
  const viewer = ref(null);
  
  onMounted(() => {
    const path = `${import.meta.env.BASE_URL}webviewer`;
    WebViewer({ path, initialDoc: props.initialDoc }, viewer.value);
  });
  
  console.log(props.initialDoc);
  console.log(viewer);
  
  </script>
  
  <style>
  #webviewer {
    height: 800px;
  }
  </style>
  