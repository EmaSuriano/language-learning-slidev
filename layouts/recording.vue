<script setup lang="ts">
const props = defineProps({
    image: {
        type: String,
    },
    direction: {
        type: String,
        default: 'right', // Only 'right' or 'left'
    },
    class: {
        type: String,
    },
});

// Dynamic grid placement
const isLeft = props.direction === 'left';
</script>

<template>
    <viu-template hideLogo>
        <div class="grid grid-cols-3 w-full h-full">
            <!-- Left GIF -->
            <div v-if="isLeft" class="w-full h-full flex items-center justify-center col-span-2">
                <gif-viewer :gifSrc="props.image" alt="Recording" class="w-full h-full object-contain" />
            </div>

            <!-- Main Content (2/3) -->
            <div class="col-span-1 slidev-layout default" :class="props.class">
                <slot />
            </div>

            <!-- Right GIF -->
            <div v-if="!isLeft" class="w-full h-full flex items-center justify-center col-span-2">
                <gif-viewer :gifSrc="props.image" alt="Recording" class="w-full h-full object-contain" />
            </div>
        </div>
    </viu-template>
</template>
