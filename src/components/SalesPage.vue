<template>
  <div class="max-w-6xl mt-[120px] mx-auto py-10">
    <h1 class="text-3xl font-bold text-center text-gray-800 mb-10">LATEST PROPERTIES FOR SALE</h1>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-4 p-4">
      <div v-for="property in forSaleProperties" :key="property.id" class="rounded-lg">
        <img :src="property.mainImage" alt="Property Image" class="w-full h-[50%] object-cover mb-4">
        <div>
          <h2 class="text-xl font-bold text-gray-800 mb-3">{{ property.name }}</h2>
          <p class="text-md text-gray-600 mb-3">{{ property.location }}</p>
          <p class="text-lg text-gray-600 mb-3">{{ property.price }}</p>
          <p class="text-sm text-yellow-600 mb-3">{{ property.bedrooms }} Bedrooms</p>
          <p class="text-gray-500 text-sm mb-5 lowercase">{{ property.description }}</p>
          <button @click="openModal(property)"
            class="border border-black px-4 py-2 uppercase text-sm hover:bg-black hover:text-white transition duration-300">
            Read More
          </button>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <div v-if="showModal" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50 z-50">
  <div class="bg-white w-11/12 md:w-2/3 lg:w-1/2 rounded-lg shadow-lg relative">
    <button @click="closeModal" class="absolute top-0.5 right-2 text-[#333] hover:text-black text-xl">
      <i class="fa-solid fa-xmark"></i>
    </button>

    <div class="flex flex-col md:flex-row">
      <!-- Image Carousel -->
      <div class="relative w-full md:w-1/2 h-60 md:h-auto rounded-l-lg overflow-hidden">
          <img :src="selectedProperty.images[currentImageIndex]" :key="selectedProperty.images[currentImageIndex]" alt="Property Image" class="w-full h-full object-cover rounded-l-lg">

        <!-- Prev Button -->
        <button @click="prevImage" class="absolute top-1/2 left-2 transform -translate-y-1/2 bg-white rounded-full p-1 shadow hover:bg-gray-200">
          <i class="fa-solid fa-chevron-left"></i>
        </button>

        <!-- Next Button -->
        <button @click="nextImage" class="absolute top-1/2 right-2 transform -translate-y-1/2 bg-white rounded-full p-1 shadow hover:bg-gray-200">
          <i class="fa-solid fa-chevron-right"></i>
        </button>
      </div>

      <!-- Property Details -->
      <div class="flex-1 p-6">
        <h2 class="text-2xl font-bold mb-3">{{ selectedProperty.name }}</h2>
        <p class="text-md text-gray-600 mb-2"><strong>Location:</strong> {{ selectedProperty.location }}</p>
        <p class="text-lg text-gray-800 mb-2"><strong>Price:</strong> {{ selectedProperty.price }}</p>
        <p class="text-md text-gray-800 mb-2"><strong>Bedrooms:</strong> {{ selectedProperty.bedrooms }}</p>
        <p class="text-gray-600 mb-4">{{ selectedProperty.description }}</p>
        <router-link to="/contact" class="border border-black px-4 py-2 uppercase text-sm hover:bg-black hover:text-white transition duration-300">
          Arrange Viewing
        </router-link>
      </div>
    </div>
  </div>
</div>


  </div>
</template>

<script>
export default {
  name: 'LatestProperties',
  components: {
  },
  data() {
    return {
      forSaleProperties: [
        {
          id: 1,
          name: 'Noah TownHouse',
          location: 'Pag-utlan Maribago, Lapu-lapu City.',
          price: '₱ 6,800,000+',
          bedrooms: 3,
          mainImage: 'images/PropertyOne.jpg',
          images: [
            'images/PropertyOne.jpg',
            'images/PropertyOne.jpg',
            'images/PropertyOne.jpg'
          ],
          description: "AFFORDABLE POCKET SUBDIVISION NOAH TOWNHOUSE READY FOR OCCUPANCY PERFECT FOR GROWING FAMILY. INVEST IN A PLACE YOU CAN CALL YOUR OWN."
        },
        {
          id: 2,
          name: 'MOANA',
          location: 'Tungkop Minglanilla Cebu',
          price: '₱ 15,139,472',
          bedrooms: 3,
          mainImage: 'images/MoanaProperties.jpg',
          images: [
            'images/MoanaProperties.jpg',
            'images/featuresOne.jpg',
            'images/FeaturesThree.jpg',
            'images/FeatureFive.jpg',
            'images/FeatureSix.jpg'
          ],
          description: "KAHALE RESIDENCES is your secured, convenient, and private paradise perfect for a growing family. 170 meters from the Highway."
        },
        {
          id: 3,
          name: 'Noah Town House',
          location: 'Pag-utlan Maribago, Lapu-lapu City.',
          price: '$790,000',
          bedrooms: 6,
          mainImage: 'images/PropertyOne.jpg',
          images: [
            'images/PropertyOne.jpg',
            'images/PropertyOne-4.jpg',
            'images/PropertyOne-5.jpg'
          ],
          description: "AFFORDABLE POCKET SUBDIVISION NOAH TOWNHOUSE READY FOR OCCUPANCY PERFECT FOR GROWING FAMILY."
        },
      ],
      showModal: false,
      selectedProperty: {},
      currentImageIndex: 0, 
    };
  },
  methods: {
    openModal(property) {
      this.selectedProperty = property;
      this.currentImageIndex = 0; 
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    },
    nextImage() {
      if (this.currentImageIndex < this.selectedProperty.images.length - 1) {
        this.currentImageIndex++;
      } else {
        this.currentImageIndex = 0;
      }
    },
    prevImage() {
      if (this.currentImageIndex > 0) {
        this.currentImageIndex--;
      } else {
        this.currentImageIndex = this.selectedProperty.images.length - 1;
      }
    },
  },
}
</script>

<style scoped>
.modal-enter-active,
.modal-leave-active {
  transition: opacity 0.3s ease-in-out, transform 0.3s ease-in-out;
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
  transform: scale(0.95);
}

.modal-enter-to,
.modal-leave-from {
  opacity: 1;
  transform: scale(1);
}


</style>

