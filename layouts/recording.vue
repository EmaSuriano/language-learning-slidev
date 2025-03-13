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
    <div class="grid grid-cols-3 w-full h-full">
        <!-- Left GIF -->
        <div v-if="isLeft" class="h-full flex items-center justify-center col-span-2 w-[95%]">
            <gif-viewer :gifSrc="props.image" alt="Recording" class="w-full h-full object-contain " />
        </div>

        <!-- Main Content (2/3) -->
        <div class="col-span-1 slidev-layout default p-10" :class="props.class">
            <slot />
        </div>

        <!-- Right GIF -->
        <div v-if="!isLeft" class="h-full flex items-center justify-center col-span-2 w-[95%] ml-auto">
            <gif-viewer :gifSrc="props.image" alt="Recording" class="w-full h-full object-contain" />
        </div>
    </div>
</template>
