<template>
    <img :src="logoSrc" alt="Viu logo" class="absolute top-4 right-2 w-30">
    <slot />
    <footer class="absolute bottom-4 left-4 text-black">SUBTITULO_HERE</footer>
</template>

<script setup>
import { computed } from 'vue';

const props = defineProps({
    variant: {
        type: String,
        default: 'default', // Default variant
        validator: value => ['accent', 'default'].includes(value),
    }
});

const logoSrc = computed(() => {
    return props.variant === 'accent' ? '/assets/viu-logo-accent.png' : '/assets/viu-logo.png';
});
</script>
