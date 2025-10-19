<script setup>
const { data } = await useFetch('/api/hello')
</script>

<template>
  <div class="container px-4 py-5 ml-auto mr-auto">
    <h1 class="text-center text-4xl font-semibold mt-5 mb-10">
      Appel à une API simple
    </h1>
    <div class="div-desc w-6/6 sm:w-4/6 md:w-3/6 lg:w-3/6 ml-auto mr-auto mb-5">
      <p class="mt-5 mb-4">Explications du développeur :</p>
      <ul class="ul-desc">
        <li>
          Ici je vais simplement appeler l&apos;API interne /server/api/hello
          avec <b>useFetch()</b>.
        </li>
        <li>
          Une API qui a pour seule fonction de retourner un objet qui a pour la
          propriété hello la valeur "world".
        </li>
      </ul>
    </div>
    <div class="mt-14 w-6/6 sm:w-4/6 md:w-3/6 lg:w-3/6 ml-auto mr-auto mb-5">
      <p>Résultat de l'appel à l&apos;API <code>/api/hello</code>:</p>
      <pre>{{ data }}</pre>
    </div>
  </div>
</template>
