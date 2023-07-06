<script setup>
  import {defineProps} from 'vue'
  const props = defineProps(["colored"])

  const copyURL = async (url) =>
    await navigator.clipboard.writeText(url)

</script>


<template>
  <VCard class="pa-6">
    <VRow>
      <VCol
        cols="6"
        sm="4"
        md="2"
        v-for="n in 200"
      >
        <VCard @click="copyURL(`https://picsum.photos/id/${n + 23}/500/500${props.colored ? '' : '?grayscale'}`)">
          <VImg
              :src="`https://picsum.photos/id/${n + 23}/500/500${props.colored ? '' : '?grayscale'}`"
              :lazy-src="`https://picsum.photos/id/${n*3 + 23}/500/500?blur=4${props.colored ? '' : '&grayscale'}`"
              aspect-ratio="1"
          >
            <template v-slot:placeholder>
              <VRow justify="center" align="center" class="ma-0 fill-height">
                <VProgressCircular
                    indeterminate
                />
              </VRow>
            </template>
          </VImg>
        </VCard>
      </VCol>
    </VRow>
  </VCard>
</template>