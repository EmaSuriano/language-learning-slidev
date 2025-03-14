<script setup lang="ts">
const props = defineProps({
    image: {
        type: String,
    },
    class: {
        type: String,
    },
});
</script>

<template>
    <div class="grid grid-cols-3 w-full h-full">
        <!-- Main Content (2/3) -->
        <div class="col-span-1 slidev-layout default p-10" :class="props.class">
            <slot />
        </div>

        <!-- Right GIF -->
        <div v-if="!isLeft" class="h-full flex items-center justify-center col-span-2 w-[95%] ml-auto">
            <slot name="recording" class="w-full h-full object-contain" />
        </div>
    </div>
</template>
