<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const props = defineProps({
    beforeImage: {
        type: String,
        required: true,
    },
    afterImage: {
        type: String,
        required: true,
    },
});

const beforeWidth = ref('50%');
const isSliding = ref(false);
const sliderWrapper = ref(null);
const sliderHandle = ref(null);

const startSlide = () => {
    isSliding.value = true;
    document.addEventListener('mousemove', onSlide);
    document.addEventListener('mouseup', stopSlide);
};

const onSlide = (event) => {
    if (!isSliding.value) return;
    const rect = sliderWrapper.value.getBoundingClientRect();
    const offsetX = event.clientX - rect.left;
    const width = rect.width;
    beforeWidth.value = `${(offsetX / width) * 100}%`;
};

const stopSlide = () => {
    isSliding.value = false;
    document.removeEventListener('mousemove', onSlide);
    document.removeEventListener('mouseup', stopSlide);
};

onMounted(() => {
    sliderHandle.value.addEventListener('mousedown', startSlide);
});

onBeforeUnmount(() => {
    sliderHandle.value.removeEventListener('mousedown', startSlide);
    document.removeEventListener('mousemove', onSlide);
    document.removeEventListener('mouseup', stopSlide);
});
</script>

<template>
    <div class="slider-container">
        <div class="slider-wrapper" ref="sliderWrapper">
            <div class="slider-img slider-img-before" :style="{ width: beforeWidth }">
                <img :src="beforeImage" alt="Before">
            </div>
            <div class="slider-img slider-img-after">
                <img :src="afterImage" alt="After">
            </div>
            <div class="slider-handle" ref="sliderHandle" @mousedown="startSlide"></div>
        </div>
    </div>
</template>

<style scoped>
.slider-container {
    position: relative;
    width: 100%;
    max-width: 800px;
    margin: auto;
    overflow: hidden;
}

.slider-wrapper {
    position: relative;
    display: flex;
    align-items: center;
}

.slider-img {
    display: flex;
    align-items: center;
    justify-content: center;
}

.slider-img img {
    display: block;
    max-width: none;
    width: 100%;
}

.slider-img-before {
    overflow: hidden;
    white-space: nowrap;
}

.slider-handle {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 50%;
    width: 4px;
    background-color: #fff;
    cursor: ew-resize;
    transform: translateX(-50%);
    z-index: 1;
}
</style>