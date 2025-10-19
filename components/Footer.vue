<script>
const currYear = new Date().getFullYear()

export default {
  name: 'Contenu',
  data() {
    return {
      currYear,
    }
  },
}
</script>

<template>
  <footer class="navbar-style p-8 relative z-0">
    <div class="flex">
      <div class="flex-grow">
        <span class="text-gray-300 text-sm font-bold">DEV</span>
        <ul class="mt-4 mb-4">
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://nbalovers.fr">Symfony</a>
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://nbalovers.fr/download">React Native</a>
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://jean-phil.gitlab.io/react/">React</a>
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://jean-phil.gitlab.io/vuejs-3/">Vue 3</a>
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://jp-parmentier-next.vercel.app/">Next</a>
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <NuxtLink to="/">Nuxt</NuxtLink>
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://rentacomic.ovh">Symfony (ancien)</a>
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://jean-phil.gitlab.io/react-project/"
              >React (ancien)</a
            >
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://jean-phil.gitlab.io/my-vuejs-project/"
              >Vue 2 (ancien)</a
            >
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://old.nbalovers.fr">Php (ancien)</a>
          </li>
        </ul>
        <span class="text-gray-300 text-sm font-bold">APP</span>
        <ul class="mt-4 mb-6">
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://nbalovers.fr/download">Android</a>
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://nbalovers.fr/download">iOS</a>
          </li>
        </ul>
      </div>
      <div class="flex-grow">
        <span class="text-gray-300 text-sm font-bold">CONTACT</span>
        <ul class="mt-4 mb-4">
          <li class="flex-row text-white font-medium text-sm mb-2">
            <a href="https://www.linkedin.com/in/jean-philippe-parmentier/">
              LinkedIn
            </a>
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            Contact
          </li>
        </ul>
        <span class="text-gray-300 text-sm font-bold">LEGAL</span>
        <ul class="mt-4 mb-6">
          <li class="flex-row text-white font-medium text-sm mb-2">
            Terms of use
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            Privacy policy
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            Cookie policy
          </li>
        </ul>
      </div>
      <!-- <div class="flex-grow">
        <span class="text-gray-300 text-sm font-bold">LEGAL</span>
        <ul class="mt-4 mb-6">
          <li class="flex-row text-white font-medium text-sm mb-2">
            Terms of use
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            Privacy policy
          </li>
          <li class="flex-row text-white font-medium text-sm mb-2">
            Cookie policy
          </li>
        </ul>
      </div> -->
    </div>
    <div class="border-b border-b-gray-100 mb-2"></div>
    <p class="text-white rounded-md py-2 text-md font-medium">
      © {{ currYear }} Jean-Philippe Parmentier - All right reserved
    </p>
  </footer>
</template>
