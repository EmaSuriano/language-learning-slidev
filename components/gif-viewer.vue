<template>
    <img ref="gifImage" :src="gifSrc" :alt="alt" class="gif-responsive" @mouseover="playGif" @mouseout="pauseGif" />
</template>

<script>
export default {
    props: {
        gifSrc: { type: String, required: true },
        alt: { type: String, default: "GIF" }
    },
    data() {
        return {
            firstFrame: null
        };
    },
    methods: {
        async extractFirstFrame() {
            const img = document.createElement("img");
            img.src = this.gifSrc;
            await img.decode(); // Wait until the image loads

            const canvas = document.createElement("canvas");
            canvas.width = img.width;
            canvas.height = img.height;
            const ctx = canvas.getContext("2d");
            ctx.drawImage(img, 0, 0);

            this.firstFrame = canvas.toDataURL("image/png");
            this.$refs.gifImage.src = this.firstFrame; // Set first frame as initial src
        },
        playGif() {
            this.$refs.gifImage.src = this.gifSrc;
        },
        pauseGif() {
            if (this.firstFrame) {
                this.$refs.gifImage.src = this.firstFrame;
            }
        }
    },
    mounted() {
        this.extractFirstFrame();
    }
};
</script>

<style scoped>
.gif-responsive {
    width: 100%;
    height: auto;
    max-width: 100%;
    object-fit: contain;
}
</style>