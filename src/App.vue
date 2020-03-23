<template>
  <div id="app" class="min-h-screen bg-gray-300">
    <nav class="flex flex-row h-20 items-center justify-between bg-teal-800 select-none">
      <router-link class="flex flex-row" to="/">
        <span>
          <img class="object-scale-down h-12 pl-8" src="./assets/logo-fit.png" alt />
        </span>

        <span class="text-4xl ml-6 text-gray-200 font-semibold">jSonFitness</span>
      </router-link>
      <router-link to="/">
        <button
          class="transition duration-300 ease-in-out mr-6 p-2 rounded-md bg-teal-800 hover:bg-teal-900 outline-none"
        >
          <font-awesome-icon
            id="plus-icon"
            class="mr-2 transition duration-300 text-orange-500"
            icon="plus"
          />
          <span class="mr-1 font-semibold font-sans font-family:roboto text-gray-200">New Training</span>
        </button>
      </router-link>
    </nav>
    <router-view />
  </div>
</template>

<style>
button:hover #plus-icon {
  transform: rotate(90deg);
  color: black;
}

/* Remove blue border from css custom-styled button in Chrome
https://stackoverflow.com/questions/20340138/remove-blue-border-from-css-custom-styled-button-in-chrome */

button:active {
  outline: none;
  border: none;
}

button:focus {
  outline: none !important;
  border: none !important;
}
</style>
