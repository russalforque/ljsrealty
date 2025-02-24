<template>
  <div class="w-full h-screen bg-cover bg-center">
    <SliderPage></SliderPage>
    <!-- Property Info -->
    <div class="w-[130vh] max-w-full top-80 absolute opacity-100 inset-0 flex flex-col items-center justify-center">
      <div class="bg-[#181A1E] text-[#f7f7f7] p-10 w-full md:max-w-sm opacity-90 h-[65vh] md:h-[45vh]">
        <h1 class="text-xl md:text-3xl font-bold mb-2 text-center md:text-left">STUNNING 6 BED HOUSE IN THE HEART OF THE
          CITY</h1>
        <p class="text-lg md:text-sm mb-4 text-start md:text-left">This beautiful 6-bedroom house offers spacious living
          in a prime city location. Featuring modern interiors, a fully equipped kitchen, and a private garden, it’s
          perfect for families or those who love to entertain.</p>
        <hr class="border-gray-400 mb-4" />
        <p class="text-2xl md:text-xl font-bold mb-4 text-center">$2,000,000</p>
        <div class="flex justify-center">
          <button class="border border-white text-white py-2 px-4 w-full hover:bg-white hover:text-blue-900 transition">
            ALL SALES
          </button>
        </div>
      </div>
    </div>

    <div class="max-w-6xl mt-10 mx-auto py-10">
      <h1 class="text-3xl font-bold text-center text-gray-800 mb-10 mt-60">LATEST PROPERTIES FOR SALE</h1>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-4 p-4">
        <div v-for="property in forSaleProperties" :key="property.id" class="rounded-lg ">
          <img :src="property.image" alt="Property Image" class="w-full h-[50%] object-cover mb-4">
          <div class="">
            <h2 class="text-xl font-bold text-gray-800 mb-3">{{ property.name }}</h2>
            <p class="text-md text-gray-600 mb-3">{{ property.location }}</p>
            <p class="text-lg text-gray-600 mb-3">{{ property.price }}</p>
            <p class="text-sm text-yellow-600 mb-3">{{ property.bedrooms }} Bedrooms</p>
            <p class="text-gray-500 text-sm mb-5">{{ property.description }}</p>
            <button
              class="border border-black px-4 py-2 uppercase text-sm hover:bg-black hover:text-white transition duration-300">
              Read More
            </button>
          </div>
        </div>
      </div>
    </div>

    <RentProperty></RentProperty>

    <TesteMonials></TesteMonials>



    <FooTer></FooTer>
  </div>

</template>



<script>
import SliderPage from './SliderPage.vue';
import FooTer from './FooTer.vue';
import RentProperty from './RentProperty.vue';
import TesteMonials from './TesteMonials.vue';
export default {
  name: 'LatestProperties',
  components: {
    SliderPage,
    FooTer,
    RentProperty,
    TesteMonials
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
          description: "AFFORDABLE POCKET SUBDIVISION NOAH TOWNHOUSE READY FOR OCCUPANCY.INVEST IN A PLACE YOU CAN CALL YOUR OWN."
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
          price: '$790,000',
          bedrooms: 6,
          image: 'images/PropertyOne.jpg',
          description: "I'm a paragraph. Click here to add your own text and edit me. It’s easy. Just click “Edit Text” or double click me to add your own content and make changes to the font. I’m a great place for you to tell a story and let your users know a little more about you."
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
      ]
    }
  },
}
</script>

<style scoped>
/* Optional: Style tweaks for better visuals */
h1 {
  letter-spacing: 1px;
}

button {
  transition: background-color 0.3s ease;
}
</style>
