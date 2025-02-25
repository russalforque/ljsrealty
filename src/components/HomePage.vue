<template>
  <div class="w-full h-screen bg-cover bg-center">
    <SliderPage></SliderPage>
    <!-- Property Info -->
    <div class="w-[130vh] max-w-full top-80 absolute opacity-100 inset-0 flex flex-col items-center justify-center">
      <div class="bg-[#181A1E] text-[#f7f7f7] p-10 w-full md:max-w-sm opacity-90 h-[65vh] md:h-[46vh]">
        <h1 class="text-xl md:text-2xl font-bold mb-2 text-center md:text-left">STUNNING 6 BED HOUSE IN THE HEART OF THE
          CITY</h1>
        <p class="text-lg md:text-sm mb-4 text-start md:text-left">This beautiful 6-bedroom house offers spacious living
          in a prime city location. Featuring modern interiors, a fully equipped kitchen, and a private garden, it’s
          perfect for families or those who love to entertain.</p>
        <hr class="border-gray-400 mb-4" />
        <p class="text-2xl md:text-3xl font-bold mb-4 text-center">$2,000,000</p>
        <div class="flex justify-center">
          <button class="border border-white text-white py-2 px-4 w-full hover:bg-white hover:text-blue-900 transition">
            ALL SALES
          </button>
        </div>
      </div>
    </div>
    <SalesPage></SalesPage>
    <!--CONDOS-->
    <div class="flex flex-col items-center justify-center p-5">
        <h2 class="text-1xl md:text-2xl lg:text-3xl font-bold mb-20 text-center uppercase">condominiums</h2>

        <!-- Property 1 -->
        <div class="flex flex-col md:flex-row overflow-hidden max-w-screen-sm md:mr-20 lg:mr-40 xl:mr-60">
            <div class="md:w-1/2 h-[43vh] relative">
                <img src="images/spainvilla.jpg" alt="Property" class="w-full h-full object-cover">
                <span class="absolute opacity-60 bottom-0.5 left-0.5 bg-black text-white px-5 py-2 text-base md:text-lg">$500,000</span>
            </div>

            <div class="md:w-1/2 p-6 md:mt-0">
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-3">ALTON</h3>
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-6">AVENUE</h3>
                <p class="font-semibold text-sm md:text-base">5 bedrooms</p>
                <p class="text-gray-700 text-sm md:text-base mb-10">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Inventore velit quo ipsam tempore laboriosam laborum beatae, architecto doloremque porro voluptas.</p>
                <button class="border border-black px-4 py-2 uppercase text-xs md:text-sm hover:bg-black hover:text-white transition duration-300">
                    Read More
                </button>
            </div>
        </div>

        <!-- Property 2 -->
        <div class="flex flex-col md:flex-row-reverse overflow-hidden max-w-screen-sm mt-20 md:ml-20 lg:ml-40 xl:ml-60">
            <div class="md:w-1/2 h-[43vh] relative">
                <img src="images/unitedstates.jpg" alt="Property" class="w-full h-full object-cover">
                <span class="absolute opacity-60 bottom-0.5 left-0.5 bg-black text-white px-5 py-2 text-base md:text-lg">$500,000</span>
            </div>

            <div class="md:w-1/2 p-6 md:mt-0">
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-3">ALTON</h3>
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-6">AVENUE</h3>
                <p class="font-semibold text-sm md:text-base">5 bedrooms</p>
                <p class="text-gray-700 text-sm md:text-base mb-10">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Inventore velit quo ipsam tempore laboriosam laborum beatae, architecto doloremque porro voluptas.</p>
                <button class="border border-black px-4 py-2 uppercase text-xs md:text-sm hover:bg-black hover:text-white transition duration-300">
                    Read More
                </button>
            </div>
        </div>

        <!-- Property 3 -->
          <div class="flex flex-col md:flex-row overflow-hidden max-w-screen-sm mt-20 md:mr-20 lg:mr-40 xl:mr-60">
            <div class="md:w-1/2 h-[43vh] relative">
                <img src="images/spainvilla.jpg" alt="Property" class="w-full h-full object-cover">
                <span class="absolute opacity-60 bottom-0.5 left-0.5 bg-black text-white px-5 py-2 text-base md:text-lg">$500,000</span>
            </div>

            <div class="md:w-1/2 p-6 md:mt-0">
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-3">ALTON</h3>
                <h3 class="text-3xl md:text-4xl lg:text-5xl font-bold mb-6">AVENUE</h3>
                <p class="font-semibold text-sm md:text-base">5 bedrooms</p>
                <p class="text-gray-700 text-sm md:text-base mb-10">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Inventore velit quo ipsam tempore laboriosam laborum beatae, architecto doloremque porro voluptas.</p>
                <button class="border border-black px-4 py-2 uppercase text-xs md:text-sm hover:bg-black hover:text-white transition duration-300">
                   Read More
                </button>
            </div>
        </div>
    </div>
    <FooTer></FooTer>
  </div>
</template>



<script>
import SliderPage from './SliderPage.vue';
import FooTer from './FooTer.vue';
import SalesPage from './SalesPage.vue';

export default {
  name: 'LatestProperties',
  components: {
    SliderPage,
    FooTer,
    SalesPage,
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
          image: 'images/PropertyOne.jpg',
          description: "AFFORDABLE POCKET SUBDIVISION NOAH TOWNHOUSE READY FOR OCCUPANCY PERFECT FOR GROWING FAMILY HERE TO ENJOYS LIFE MOST CHERISHED AND MEANINGFUL MOMENTS.INVEST IN A PLACE YOU CAN CALL YOUR OWN."
        },
        {
          id: 2,
          name: 'MOANA',
          location: 'Tungkop Minglanilla Cebu',
          price: '₱ 15,139,472',
          bedrooms: 3,
          image: 'images/MoanaProperties.jpg',
          description: "KAHALE RESIDENCES is your secured, convemient and private paradise perfect for a growing family here to enjoy life’s most cherished and meaningful moments.170 meters from the Highway"
        },
        {
          id: 3,
          name: 'Noah Town House',
          location: 'Tungkop Minglanilla Cebu',
          price: '$790,000',
          bedrooms: 6,
          image: 'images/PropertyOne.jpg',
          description: "KAHALE RESIDENCES is your secured, convemient and private paradise perfect for a growing family here to enjoy life’s most cherished and meaningful moments.170 meters from the Highway"
        }
      ],
      rentalProperties: [
        {
          id: 4,
          name: 'CHASE AVENUE',
          price: '$500/per week',
          bedrooms: 4,
          image: 'https://via.placeholder.com/400x300',
          description: "I'm a paragraph. Click here to add your own text and edit me. It's easy."
        },
        {
          id: 5,
          name: 'KINGS CLOSE',
          price: '$450/per week',
          bedrooms: 3,
          image: 'https://via.placeholder.com/400x300',
          description: "I'm a paragraph. Click here to add your own text and edit me. It's easy."
        }
      ],
      showModal: false,
      selectedProperty: {},
    }
  },
  methods: {
    openModal(property) {
      this.selectedProperty = property;
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    },
  },
}
</script>

<style scoped>
h1 {
  letter-spacing: 1px;
}

button {
  transition: background-color 0.3s ease;
}
</style>
