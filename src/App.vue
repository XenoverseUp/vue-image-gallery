<script setup>
  import Sidebar from "@/components/Sidebar.vue";
  import ImageGallery from "@/components/ImageGallery.vue";
  import {ref} from "vue";

  const colored = ref(false)
  const onSelectOption = (isColor) => colored.value = isColor;
</script>

<template>
  <VApp>
    <Sidebar @select-option="onSelectOption" />
    <VMain>
      <ImageGallery :colored="colored" />
    </VMain>
  </VApp>
</template>
