<template>
  <div class="my-6 max-w-screen-xl mx-auto mt-40 mb-40 p-2">
    <!-- Header -->
    <div class="max-w-2xl mx-auto text-center">
      <h2 class="text-2xl md:text-3xl font-bold text-gray-800 uppercase">What my clients think</h2>
      <p class="text-sm md:text-base mt-6 leading-relaxed text-gray-500">
        Hear what my clients have to say about their real estate experiences and how I helped them find their dream
        homes.
      </p>
    </div>

    <!-- Slider -->
    <div class="relative overflow-hidden mt-16">
      <div class="flex transition-transform duration-700" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
        <div v-for="(testimonial, index) in testimonials" :key="index"
          class="min-w-full flex flex-col items-center text-center">
          <img :src="testimonial.image" class="w-24 h-24 rounded-full border-2 border-gray-600" />
          <h4 class="text-sm md:text-base font-bold text-gray-800 mt-6">{{ testimonial.name }}</h4>
          <div class="flex justify-center space-x-1 mt-2.5">
            <span class="text-yellow-500 flex space-x-2">
              <i v-for="n in 5" :key="n" class="fa-solid fa-star"></i>
            </span>
          </div>
          <p class="text-sm md:text-base leading-relaxed text-gray-800 mt-4 px-6 md:px-40">
            "{{ testimonial.review }}"
          </p>
        </div>
      </div>

      <!-- Prev & Next Buttons -->
      <button @click="prevSlide" class="absolute top-1/2 left-4 transform -translate-y-1/2">
        <i class="fa-solid fa-chevron-left text-3xl md:text-4xl"></i>
      </button>
      <button @click="nextSlide" class="absolute top-1/2 right-4 transform -translate-y-1/2">
        <i class="fa-solid fa-chevron-right text-3xl md:text-4xl"></i>
      </button>
    </div>

    <!-- Navigation Dots -->
    <div class="flex justify-center mt-6 space-x-2">
      <span v-for="(testimonial, index) in testimonials" :key="'dot-' + index" @click="goToSlide(index)"
        class="w-3 h-3 rounded-full cursor-pointer"
        :class="currentIndex === index ? 'bg-gray-800' : 'bg-gray-400'"></span>
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
          review: "Working with this agent was a fantastic experience. They made the home-buying process smooth and stress-free. I couldn't be happier with my new home!",
          image: "images/stefan.jpg",
        },
        {
          name: "Mark Adair",
          review: "Their market knowledge and attention to detail made selling our home so easy. We sold above asking price in just a week. Highly recommend!",
          image: "images/stefan.jpg",
        },
        {
          name: "Simon Konecki",
          review: "I was nervous about buying my first house, but the team guided me through every step. Their expertise made all the difference. Thank you!",
          image: "images/stefan.jpg",
        },
        {
          name: "Emily Blunt",
          review: "Professional, responsive, and truly invested in finding us the perfect property. We found our dream home thanks to their hard work and dedication.",
          image: "images/stefan.jpg",
        },
      ],
      intervalId: null,
    };
  },
  beforeUnmount() {
    clearInterval(this.intervalId);
  },
  methods: {
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
