<script setup>
  import {defineEmits} from "vue"
  const emits = defineEmits(['select-option'])

  const selectOption = (isColor) => emits("select-option", isColor)
</script>

<template>
  <VNavigationDrawer expand-on-hover rail="true">
    <VList>
      <VListItem
        prepend-avatar="https://randomuser.me/api/portraits/men/85.jpg"
        title="Can Durmus"
        subtitle="namelian01@gmail.com"
      ></VListItem>
    </VList>
    <VDivider />
    <VList density="compact" nav>
      <VListItem
        prepend-icon="mdi-image"
        title="Color Gallery"
        value="color"
        @click="selectOption(true)"
      />
      <VListItem
        prepend-icon="mdi-dialpad"
        title="Grayscale Gallery"
        value="grayscale"
        @click="selectOption(false)"
      />
    </VList>
  </VNavigationDrawer>
</template>

<style scoped>

</style>