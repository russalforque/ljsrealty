<template>
    <div class="flex flex-col items-center justify-center p-5 mt-[120px]">
        <h2 class="text-1xl md:text-2xl lg:text-3xl font-bold mb-10 text-center uppercase">condominiums</h2>

        <!-- Property 1 -->
        <div class="flex flex-col md:flex-row overflow-hidden max-w-screen-sm md:mr-20 lg:mr-40 xl:mr-60">
            <div class="md:w-1/2 h-[43vh] relative overflow-hidden">
                <div class="w-full h-full flex transition-transform duration-700"
                    :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
                    <img v-for="(image, index) in images" :key="index" :src="image" alt="Property"
                        class="w-full h-full object-cover flex-shrink-0" />
                </div>
                <span
                    class="absolute opacity-60 bottom-0.5 left-0.5 bg-black text-white px-5 py-2 text-base md:text-lg">$500,000</span>
            </div>

            <div class="md:w-1/2 p-6 md:mt-0">
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-3">ALTON</h3>
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-6">AVENUE</h3>
                <p class="font-semibold text-sm md:text-base">5 bedrooms</p>
                <p class="text-gray-700 text-sm md:text-base mb-10">
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit. Inventore velit quo ipsam tempore
                    laboriosam laborum beatae, architecto doloremque porro voluptas.
                </p>
                <button
                    class="border border-black px-4 py-2 uppercase text-xs md:text-sm hover:bg-black hover:text-white transition duration-300">
                    Arrange a Viewing
                </button>
            </div>
        </div>

        <!-- Property 2 -->
        <div class="flex flex-col md:flex-row-reverse overflow-hidden max-w-screen-sm mt-20 md:ml-20 lg:ml-40 xl:ml-60">
            <div class="md:w-1/2 h-[43vh] relative">
                <img src="images/unitedstates.jpg" alt="Property" class="w-full h-full object-cover">
                <span
                    class="absolute opacity-60 bottom-0.5 left-0.5 bg-black text-white px-5 py-2 text-base md:text-lg">$500,000</span>
            </div>

            <div class="md:w-1/2 p-6 md:mt-0">
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-3">ALTON</h3>
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-6">AVENUE</h3>
                <p class="font-semibold text-sm md:text-base">5 bedrooms</p>
                <p class="text-gray-700 text-sm md:text-base mb-10">Lorem ipsum dolor sit amet consectetur, adipisicing
                    elit. Inventore velit quo ipsam tempore laboriosam laborum beatae, architecto doloremque porro
                    voluptas.</p>
                <button
                    class="border border-black px-4 py-2 uppercase text-xs md:text-sm hover:bg-black hover:text-white transition duration-300">
                    Arrange a Viewing
                </button>
            </div>
        </div>

        <!-- Property 3 -->
        <div class="flex flex-col md:flex-row overflow-hidden max-w-screen-sm mt-20 md:mr-20 lg:mr-40 xl:mr-60">
            <div class="md:w-1/2 h-[43vh] relative">
                <img src="images/spainvilla.jpg" alt="Property" class="w-full h-full object-cover">
                <span
                    class="absolute opacity-60 bottom-0.5 left-0.5 bg-black text-white px-5 py-2 text-base md:text-lg">$500,000</span>
            </div>

            <div class="md:w-1/2 p-6 md:mt-0">
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-3">ALTON</h3>
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-6">AVENUE</h3>
                <p class="font-semibold text-sm md:text-base">5 bedrooms</p>
                <p class="text-gray-700 text-sm md:text-base mb-10">Lorem ipsum dolor sit amet consectetur, adipisicing
                    elit. Inventore velit quo ipsam tempore laboriosam laborum beatae, architecto doloremque porro
                    voluptas.</p>
                <button
                    class="border border-black px-4 py-2 uppercase text-xs md:text-sm hover:bg-black hover:text-white transition duration-300">
                    Arrange a Viewing
                </button>
            </div>
        </div>
    </div>
    <FooTer></FooTer>
</template>

<script>
import FooTer from './FooTer.vue'

export default {
    components: {
        FooTer,
    },
    data() {
        return {
            images: [
                'images/spainvilla.jpg',
                'images/rome.jpg',
                'images/unitedstates.jpg'
            ],
            currentIndex: 0
        };
    },
    mounted() {
        this.startSlider();
    },
    methods: {
        startSlider() {
            setInterval(() => {
                this.currentIndex = (this.currentIndex + 1) % this.images.length;
            }, 3000); // Slide every 3 seconds
        }
    }
};
</script>

<style scoped>
/* Ensure images line up horizontally */
img {
    width: 100%;
    height: 100%;
}
</style>