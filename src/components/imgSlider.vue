<template>
    <div class="slider-container">
        <div class="slider-content">
            <button @click="prevImage" class="nav-arrow left-arrow">‹</button>
            <div class="image-wrapper">
                <img :src="images[currentImage].src" alt="Slider Image" class="slider-image" />
                <h2 class="image-title">{{ images[currentImage].title }}</h2>
            </div>
            <button @click="nextImage" class="nav-arrow right-arrow">›</button>
        </div>
    </div>
</template>
  
<script>
export default {
    props: {
        images: {
            type: Array,
            required: true,
            default: () => []
        }
    },
    data() {
        return {
            currentImage: 0
        };
    },
    methods: {
        prevImage() {
            this.currentImage = (this.currentImage > 0) ? this.currentImage - 1 : this.images.length - 1;
        },
        nextImage() {
            this.currentImage = (this.currentImage < this.images.length - 1) ? this.currentImage + 1 : 0;
        }
    }
};
</script>
  
<style scoped>
.slider-container {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    width: 100%;
    height: 100%;

}

.slider-content {
    display: flex;
    align-items: center;
    position: relative;
}

.image-wrapper {
    position: relative;
    text-align: center;
}

.slider-image {
    max-width: 100%;
    height: auto;
}

.image-title {
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
    color: white;
    background-color: rgba(0, 0, 0, 0.5);
    padding: 5px 10px;
    border-radius: 5px;
}

.nav-arrow {
    background: none;
    border: none;
    font-size: 7rem;
    cursor: pointer;
    color: #606C38;
    padding: 10px;
    user-select: none;
}

.left-arrow {
    position: absolute;
    left: -50px;
}

.right-arrow {
    position: absolute;
    right: -50px;
}
</style>