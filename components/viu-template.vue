<script setup lang="ts">
const props = defineProps({
    variant: {
        type: String,
        default: 'default',
    },
    hideLogo: {
        type: Boolean,
        default: false,
    }
});

// Dynamic grid placement
const isLeft = props.direction === 'left';
</script>

<template>
    <!-- <img :src="logoSrc" alt="Viu logo" class="absolute top-4 right-2 w-30"> -->

    <img v-if="!props.hideLogo && props.variant === 'accent'" src="/assets/viu-logo-accent.png" alt="Viu Logo"
        class="absolute top-4 right-2 w-30">
    <img v-if="!props.hideLogo && props.variant === 'default'" src="/assets/viu-logo.png" alt="Viu Logo"
        class="absolute top-4 right-2 w-30">

    <slot />
    <footer class="absolute bottom-4 left-4 text-black">{{ $slidev.configs.title }}</footer>
</template>