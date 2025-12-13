<script setup lang="js">
import { ref, watchEffect, inject } from 'vue'
import { Sun, Moon, Monitor } from 'lucide-vue-next'

const props = defineProps({
    showLabel: {
        type: Boolean,
        default: true,
    },
})

const colorMode = inject('colorMode')
const selectedColorMode = ref(colorMode?.value || 'auto')

const options = [
    { label: 'Light', value: 'light', icon: Sun },
    { label: 'Dark', value: 'dark', icon: Moon },
    { label: 'System', value: 'auto', icon: Monitor },
]

watchEffect(() => {
    if (colorMode) colorMode.value = selectedColorMode.value
})
</script>

<template>
    <SelectButton
        v-model="selectedColorMode"
        :options="options"
        :allowEmpty="false"
        optionLabel="label"
        optionValue="value"
    >
        <template #option="{ option }">
            <component :is="option.icon" /> <span v-if="props.showLabel">{{ option.label }}</span>
        </template>
    </SelectButton>
</template>
