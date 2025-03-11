<script setup lang="ts">
const props = defineProps({
    class: {
        type: String,
    },
})
</script>


<template>
    <div class="slidev-layout fact bg-[#E65014] ![&>*]:text-white flex items-center" :class="props.class">
        <viu-template variant="accent">
            <slot />
        </viu-template>
    </div>
</template>