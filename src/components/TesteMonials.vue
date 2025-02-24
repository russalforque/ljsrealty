<template>
    <div class="my-6 max-w-screen-xl mx-auto mt-40 mb-40 p-2">
      <!-- Header -->
      <div class="max-w-2xl mx-auto text-center">
        <h2 class="text-2xl md:text-3xl font-bold text-gray-800 uppercase">What our clients think</h2>
        <p class="text-sm md:text-base mt-6 leading-relaxed text-gray-500">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi, minima accusantium, voluptatum quod temporibus.
        </p>
      </div>
  
      <!-- Slider -->
      <div class="relative overflow-hidden mt-16">
        <div
          class="flex transition-transform duration-700"
          :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
        >
          <div
            v-for="(testimonial, index) in testimonials"
            :key="index"
            class="min-w-full flex flex-col items-center text-center"
          >
            <img :src="testimonial.image" class="w-24 h-24 rounded-full border-2 border-gray-600" />
            <h4 class="text-sm md:text-base font-bold text-gray-800 mt-6">{{ testimonial.name }}</h4>
            <div class="flex justify-center space-x-1 mt-2.5">
              <span class="text-yellow-500">★★★★★</span>
            </div>
            <p class="text-sm md:text-base leading-relaxed text-gray-800 mt-4 px-6 md:px-40">
              "{{ testimonial.review }}"
            </p>
          </div>
        </div>
  
        <!-- Prev & Next Buttons -->
        <button
          @click="prevSlide"
          class="absolute top-1/2 left-4 transform -translate-y-1/2"
        >
          <i class="fa-solid fa-chevron-left text-3xl md:text-4xl"></i>
        </button>
        <button
          @click="nextSlide"
          class="absolute top-1/2 right-4 transform -translate-y-1/2"
        >
          <i class="fa-solid fa-chevron-right text-3xl md:text-4xl"></i>
        </button>
      </div>
  
      <!-- Navigation Dots -->
      <div class="flex justify-center mt-6 space-x-2">
        <span
          v-for="(testimonial, index) in testimonials"
          :key="'dot-' + index"
          @click="goToSlide(index)"
          class="w-3 h-3 rounded-full cursor-pointer"
          :class="currentIndex === index ? 'bg-gray-800' : 'bg-gray-400'"
        ></span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        currentIndex: 0,
        testimonials: [
          {
            name: "John Doe",
            review: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil iusto aliquam, voluptate inventore dignissimos a reprehenderit.",
            image: "images/stefan.jpg",
          },
          {
            name: "Mark Adair",
            review: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil iusto aliquam, voluptate inventore dignissimos a reprehenderit.",
            image: "images/stefan.jpg",
          },
          {
            name: "Simon Konecki",
            review: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil iusto aliquam, voluptate inventore dignissimos a reprehenderit.",
            image: "images/stefan.jpg",
          },
          {
            name: "Emily Blunt",
            review: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil iusto aliquam, voluptate inventore dignissimos a reprehenderit.",
            image: "images/stefan.jpg",
          },
        ],
        intervalId: null,
      };
    },
    mounted() {
      this.startAutoSlide();
    },
    beforeUnmount() {
      clearInterval(this.intervalId);
    },
    methods: {
      startAutoSlide() {
        this.intervalId = setInterval(() => {
          this.nextSlide();
        }, 10000);
      },
      goToSlide(index) {
        this.currentIndex = index;
      },
      nextSlide() {
        this.currentIndex = (this.currentIndex + 1) % this.testimonials.length;
      },
      prevSlide() {
        this.currentIndex =
          (this.currentIndex - 1 + this.testimonials.length) % this.testimonials.length;
      },
    },
  };
  </script>
  
  <style scoped>
  button {
    transition: background-color 0.3s;
  }
  </style>
  