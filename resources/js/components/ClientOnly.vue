<script setup lang="js">
import { ref, onMounted } from 'vue'

const isMounted = ref(false)

onMounted(() => {
    isMounted.value = true
})
</script>


<template>
    <slot v-if="isMounted" />
</template>