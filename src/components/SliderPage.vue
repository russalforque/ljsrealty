<template>
    <div class="relative w-full overflow-hidden">
        <!-- Slider Wrapper -->
        <div class="flex transition-transform duration-500"
            :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
            <div v-for="(image, index) in images" :key="index" class="min-w-full flex-shrink-0">
                <img :src="image" alt="Slide Image" class="w-full h-64 object-cover" />
            </div>
        </div>

        <!-- Navigation Buttons -->
        <button @click="prevSlide"
            class="absolute left-4 top-1/2 transform -translate-y-1/2 text-[#f7f7f7] p-2 rounded-full z-10">
            <i class="fa-solid fa-chevron-left text-4xl"></i>
        </button>

        <button @click="nextSlide" class="absolute right-4 top-1/2 transform -translate-y-1/2 text-[#f7f7f7] z-10">
            <i class="fa-solid fa-chevron-right text-4xl"></i>
        </button>
    </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const images = ref([
    'images/HoTel.jpg',
    'images/spainvilla.jpg',
    'images/smarthouse.jpg'
]);

const currentIndex = ref(0);

const nextSlide = () => {
    currentIndex.value = (currentIndex.value + 1) % images.value.length;
};

const prevSlide = () => {
    currentIndex.value =
        (currentIndex.value - 1 + images.value.length) % images.value.length;
};

let interval;

onMounted(() => {
    interval = setInterval(nextSlide, 5000);
});

onUnmounted(() => {
    clearInterval(interval);
});

</script>

<style scoped>
img {
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    width: 100%;
    height: auto;
    max-height: 75vh;
    object-fit: cover;
}
</style>