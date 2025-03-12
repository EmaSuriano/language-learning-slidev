<script setup lang="ts">
const props = defineProps({
    class: {
        type: String,
    },
    layoutClass: {
        type: String,
    },
})
</script>

<template>
    <viu-template>
        <div class="slidev-layout two-columns p-0 w-full h-full grid grid-cols-2" :class="props.layoutClass">
            <div class="col-left py-10 pl-10" :class="props.class">
                <slot />
            </div>
            <div class="col-right bg-gray-100 py-10 pr-10 flex justify-center items-center" :class="props.class">
                <slot name="right" />
            </div>
        </div>
    </viu-template>
</template>