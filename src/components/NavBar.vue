<template>
  <nav class="bg-white fixed w-full z-20 top-0 h-[90px] start-0 border-b shadow-xl">
    <div class="max-w-screen-lg flex flex-wrap items-center justify-between mx-auto p-4">
      <a href="" class="flex items-center space-x-3 rtl:space-x-reverse mt-2">
        <img src="images/ljsLogos.png" class="h-10" alt="Logo">
      </a>
      <div class="flex md:order-2 space-x-3 md:space-x-0 rtl:space-x-reverse">
        <a class="mt-4 text-sm font-semibold">+63 9562860511</a>
        <button data-collapse-toggle="navbar-sticky" type="button" class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200">
          <span class="sr-only">Open main menu</span>
          <svg class="w-5 h-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
          </svg>
        </button>
      </div>
      <div class="items-end justify-between hidden w-full md:flex md:w-auto md:order-1 mt-4" id="navbar-sticky">
        <ul class="flex flex-col p-4 md:p-0 mt-4 uppercase text-sm font-normal border border-gray-100 rounded-lg bg-gray-50 md:space-x-10 rtl:space-x-reverse md:flex-row md:mt-0 md:border-0 md:bg-white">
          <li>
            <router-link to="/" class="nav-link" exact>home</router-link>
          </li>
          <li>
            <router-link to="/sales" class="nav-link">sales</router-link>
          </li>
          <li>
            <router-link to="/rentals" class="nav-link">condos</router-link>
          </li>
          <li>
            <router-link to="/contact" class="nav-link">contact</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.nav-link {
  position: relative;
  transition: color 0.6s ease;
  padding: 0.5rem 1rem;
  text-transform: uppercase;
}


.nav-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: 0px;
  left: 0;
  background-color: #333;
  transition: width 0.6s ease;
}

.nav-link:hover::after {
  width: 100%;
}


.router-link-active::after {
  width: 50%;
}
</style>
