<template>
   <!--CONTACT US SECTION -->
   <div class="max-w-screen-xl max-lg:max-w-3xl mx-auto bg-white my-6 mt-40 mb-10">
      <div class="text-center px-6">
        <h2 class="text-gray-800 text-3xl font-bold uppercase">Contact Me</h2>
        <p class="text-base text-gray-500 mt-4">Searching for your dream home, or planning to invest or sell?</p>
      </div>

      <div class="grid lg:grid-cols-3 items-start gap-4 p-2 shadow-[0_2px_10px_-3px_rgba(6,81,237,0.3)] rounded-lg mt-12">

        <div class="bg-[#181A1E] rounded-lg p-6 h-full max-lg:order-1">
          <h2 class="text-xl text-white">Contact Information</h2>
          <p class="text-sm text-gray-300 mt-4">Searching for your dream home, or planning to invest or sell?</p>

          <ul class="mt-16 space-y-8">
            <li class="flex items-center">
              <EmailIcon></EmailIcon>
              <a href="javascript:void(0)" class="text-sm text-gray-300 ml-4">
                angelicayap320@gmail.com 
              </a>
            </li>
            <li class="flex items-center">
              <PhoneIcon></PhoneIcon>
              <a href="javascript:void(0)" class="text-sm text-gray-300 ml-4">
                +63 9562860511
              </a>
            </li>
            <li class="flex items-center">
              <LocationIcon></LocationIcon>
              <a href="javascript:void(0)" class="text-sm text-gray-300 ml-4">
                Nazareth StCebu City, 6000 Cebu
              </a>
            </li>
          </ul>

          <ul class="flex flex-wrap gap-4 mt-16">
            <li class="bg-gray-800 hover:bg-gray-900 h-10 w-10 rounded-full flex items-center justify-center shrink-0">
              <a href="javascript:void(0)">
                <FacebookIcon></FacebookIcon>
              </a>
            </li>
            <li class="bg-gray-800 hover:bg-gray-900 h-10 w-10 rounded-full flex items-center justify-center shrink-0">
              <a href="javascript:void(0)">
                <LinkidInIcon></LinkidInIcon>
              </a>
            </li>
            <li class="bg-gray-800 hover:bg-gray-900 h-10 w-10 rounded-full flex items-center justify-center shrink-0">
              <a href="javascript:void(0)">
                <InstagramIcon></InstagramIcon>
              </a>
            </li>
          </ul>
        </div>

        <div class="p-4 lg:col-span-2">
          <form>
            <div class="grid sm:grid-cols-2 gap-8">
              <div class="relative flex items-center">
                <input type="text" placeholder="First Name"
                  class="px-2 py-3 bg-white w-full text-sm text-gray-800 border-b border-gray-300 focus:border-gray-500 outline-none" />
                    <FirstNameIcon></FirstNameIcon>
              </div>

              <div class="relative flex items-center">
                <input type="text" placeholder="Last Name"
                  class="px-2 py-3 bg-white w-full text-sm text-gray-800 border-b border-gray-300 focus:border-gray-500 outline-none" />
                    <LastNameIcon></LastNameIcon>
              </div>

              <div class="relative flex items-center">
                <input type="number" placeholder="Phone No."
                  class="px-2 py-3 bg-white w-full text-sm text-gray-800 border-b border-gray-300 focus:border-gray-500 outline-none" />
                    <PhoneNumberIcon></PhoneNumberIcon>
              </div>

              <div class="relative flex items-center">
                <input type="email" placeholder="Email"
                  class="px-2 py-3 bg-white  w-full text-sm text-gray-800 border-b border-gray-300 focus:border-gray-500 outline-none" />
                    <GmailIcon></GmailIcon>
              </div>

              <div class="relative flex items-center sm:col-span-2">
                <textarea placeholder="Write Message"
                  class="px-2 pt-3 bg-white w-full text-sm text-gray-800 border-b border-gray-300 focus:border-gray-500 outline-none"></textarea>
                    <MessageIcon></MessageIcon>
              </div>

              <div class="col-span-full">
                <h6 class="text-sm text-gray-800">Select Subject</h6>
                <div class="flex max-lg:flex-col gap-6 mt-4">
                  <div class="flex items-center">
                    <input id="radio1" type="radio" name="value1" class="hidden peer" checked />
                    <label for="radio1"
                      class="relative p-0.5 flex items-center justify-center shrink-0 peer-checked:before:hidden before:block before:absolute before:w-full before:h-full before:bg-white w-5 h-5 cursor-pointer border-2 border-[#011c2b] rounded-full overflow-hidden">
                      <span class="border-[4px] border-[#011c2b] rounded-full w-full h-full"></span>
                    </label>
                    <p class="text-sm text-gray-500 ml-4">General Inquiry</p>
                  </div>

                  <div class="flex items-center">
                    <input id="radio3" type="radio" name="value1" class="hidden peer" />
                    <label for="radio3"
                      class="relative p-0.5 flex items-center justify-center shrink-0 peer-checked:before:hidden before:block before:absolute before:w-full before:h-full before:bg-white w-5 h-5 cursor-pointer border-2 border-[#011c2b] rounded-full overflow-hidden">
                      <span class="border-[4px] border-[#011c2b] rounded-full w-full h-full"></span>
                    </label>
                    <p class="text-sm text-gray-500 ml-4">Website Feedback</p>
                  </div>
                </div>
              </div>
            </div>

            <button type="button"
              class="mt-12 flex items-center justify-center text-sm lg:ml-auto max-lg:w-full rounded-lg px-4 py-3 tracking-wide text-white bg-gray-800 hover:bg-gray-600">
                <SendIcon></SendIcon>
              Send Message
            </button>
          </form>
        </div>
      </div>
    </div>
    <FooTer></FooTer>
</template>

<script>
import FooTer from './FooTer.vue';
import EmailIcon from './Icons/EmailIcon.vue';
import PhoneIcon from './Icons/PhoneIcon.vue';
import LocationIcon from './Icons/LocationIcon.vue';
import FacebookIcon from './Icons/FacebookIcon.vue'
import InstagramIcon from './Icons/InstagramIcon.vue'
import LinkidInIcon from './Icons/LinkedInIcon.vue'
import FirstNameIcon from './Icons/FirstNameIcon.vue'
import LastNameIcon from './Icons/LastNameIcon.vue'
import PhoneNumberIcon from './Icons/PhoneNumberIcon.vue'
import GmailIcon from './Icons/GmailIcon.vue'
import MessageIcon from './Icons/MessageIcon.vue'
import SendIcon from './Icons/SendIcon.vue'



export default {
  components: {
    FooTer,
    EmailIcon,
    PhoneIcon,
    LocationIcon,
    FacebookIcon,
    InstagramIcon,
    LinkidInIcon,
    FirstNameIcon,
    LastNameIcon,
    PhoneNumberIcon,
    GmailIcon,
    MessageIcon,
    SendIcon,
  }
}
</script>

<style>
</style>