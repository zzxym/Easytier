<script setup lang="ts">
import { getSdwanVersion } from '~/composables/network'

const { t } = useI18n()

const sdwanVersion = ref('')

onMounted(async () => {
  sdwanVersion.value = await getSdwanVersion()
})
</script>

<template>
  <Card>
    <template #title>
      SDWAN - {{ t('about.version') }}: {{ sdwanVersion }}
    </template>
    <template #content>
      <p class="mb-1">
        {{ t('about.description') }}
      </p>
    </template>
  </Card>
</template>

<style scoped lang="postcss">
</style>
