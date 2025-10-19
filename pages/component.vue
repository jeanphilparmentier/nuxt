<script setup>
const id = ref(1)
</script>

<template>
  <div class="container px-4 py-5 ml-auto mr-auto">
    <h1 class="text-center text-4xl font-semibold mt-5 mb-10">
      Composant enfant
    </h1>
    <div class="div-desc w-6/6 sm:w-4/6 md:w-3/6 lg:w-3/6 ml-auto mr-auto mb-5">
      <p class="mt-5 mb-4">Explications du développeur :</p>
      <ul class="ul-desc">
        <li>
          Ici c&apos;est presque la même chose, je vais appeler l&apos;API
          <b>https://dummyjson.com/quotes/</b> en lui passant un id que je peux
          incrémenter ou décrémenter avec un bouton. Et j'utilise
          <b>ref()</b> pour l'id.
        </li>
        <li>
          Sauf que cette fois ci c'est un composant enfant qui va appeler
          l&apos;API. C&apos;est donc un exemple de passage de paramètre à un
          composant enfant. Au niveau de l'enfant on va récupérer la variable
          avec <b>defineProps()</b>:
          <code>const props = defineProps({ id: Number })</code> Le simple fait
          de changer la valeur de cet id au niveau du parent relance
          automatiquement l'appel à l&apos;API chez l&apos;enfant.
        </li>
      </ul>
      <div>
        <p>
          <button
            class="navbar-style hover:bg-emerald-500 text-white font-bold py-2 px-4 rounded"
            @click="id--"
          >
            Previous
          </button>
          -
          <button
            class="navbar-style hover:bg-emerald-500 text-white font-bold py-2 px-4 rounded"
            @click="id++"
          >
            Next
          </button>
        </p>
        <TheQuote :id="id" />
        <NuxtLink
          class="navbar-style hover:bg-emerald-500 text-white font-bold py-2 px-4 rounded"
          to="/"
          >Back home</NuxtLink
        >
      </div>
    </div>
  </div>
</template>
