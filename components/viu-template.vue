<template>
    <!-- <img :src="logoSrc" alt="Viu logo" class="absolute top-4 right-2 w-30"> -->

    <img v-if="variant === 'accent'" src="/assets/viu-logo-accent.png" alt="Viu Logo"
        class="absolute top-4 right-2 w-30">
    <img v-else src="/assets/viu-logo.png" alt="Viu Logo" class="absolute top-4 right-2 w-30">

    <slot />
    <footer class="absolute bottom-4 left-4 text-black">SUBTITULO_HERE</footer>
</template>