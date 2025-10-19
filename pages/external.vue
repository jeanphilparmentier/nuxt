<script setup>
const id = ref(1)
const {
  data: product,
  pending,
  error,
} = await useFetch(() => `https://dummyjson.com/products/${id.value}`)

/* Same as:
const { data: product, pending, error } = await useAsyncData(() => {
  return $fetch(`https://dummyjson.com/products/${id.value}`)
}, {
  watch: [id]
})
*/
</script>

<template>
  <div class="container px-4 py-5 ml-auto mr-auto">
    <h1 class="text-center text-4xl font-semibold mt-5 mb-10">
      Appel à une API externe
    </h1>
    <div class="div-desc w-6/6 sm:w-4/6 md:w-3/6 lg:w-3/6 ml-auto mr-auto mb-5">
      <p class="mt-5 mb-4">Explications du développeur :</p>
      <ul class="ul-desc">
        <li>
          Ici je vais simplement appeler l&apos;API
          <b>https://dummyjson.com/products/</b> en lui passant un id que je
          peux incrémenter ou décrémenter avec un bouton ou l'input type number
          ci-dessous.
        </li>
        <li>
          Comme j&apos;utilise <b>ref()</b> pour l&apos;id:
          <code>const id = ref(1)</code> tout changement de la valeur de id
          entraîne la mise à jour du composant où il est utilisé. Donc le simple
          fait de changer la valeur de cet id relance automatiquement l'appel à
          l&apos;API. En bonus j&apos;utilise les très pratiques
          <b>pending</b> et <b>error</b> ici:
          <code
            >const { data: product, pending, error } = await
            useFetch(()...</code
          >
          pour gérer les erreurs et le chargement de l&apos;API.
        </li>
      </ul>
    </div>
    <div class="mt-14 w-6/6 sm:w-4/6 md:w-3/6 lg:w-3/6 ml-auto mr-auto mb-5">
      <p>
        Résultat de l'appel à l&apos;API
        <code>https://dummyjson.com/products/</code
        ><input class="w-10" type="number" v-model="id" />
      </p>
      <pre>{{ data }}</pre>
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
      <p v-if="pending" class="mb-3 h-[480px]">Fetching...</p>
      <pre v-else-if="error" class="mb-3 h-[480px]">{{ error }}</pre>
      <pre v-else class="mb-3 h-[480px] overflow-x-auto">{{ product }}</pre>
      <NuxtLink
        to="/"
        class="navbar-style hover:bg-emerald-500 text-white font-bold py-2 px-4 rounded"
        >Back home</NuxtLink
      >
    </div>
  </div>
  <!-- <div>
    <p>Result of <code>https://dummyjson.com/products/</code><input type="number" v-model="id" /></p>
  </div> -->
</template>
