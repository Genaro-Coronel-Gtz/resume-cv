<template>
  <v-container
    fluid
    grid-list-xl
    style="background-color: white;"
    class="mt-4"
  >
    <h1
      style="color: gray; margin-bottom: 1.2rem; text-align:center"
      class="mx-auto"
    >
      Some of my articles
    </h1>
    <v-layout
      row
      wrap
    >
      <v-card
        v-for="(post,i) in posts"
        :key="i"
        class="mx-auto mb-5"
        max-width="400"
        @click="open(post.url)"
      >
        <v-img
          class="white--text align-end"
          height="200px"
          :src="post.imagen"
        />

        <v-card-title> <strong> {{ post.titulo }} </strong> </v-card-title>
        <v-card-title> {{ post.content }} </v-card-title>
      </v-card>
    </v-layout>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    posts: [
      {
        titulo : 'Editores de código',
        imagen : 'https://miro.medium.com/max/700/1*MSWyC_kFmIJ7NaHmzH9Jqg.jpeg',
        content: 'En todo proceso de creación es imprescindible el uso de herramientas, tal es el caso de desarrollo de software en el cual la herramienta mas preciada termina siendo nuestro editor de código, éste junto a la gran diversidad de complementos que existen nos hacen la vida mas fácil al momento de escribir software.',
        url    : 'https://medium.com/@genarocoronel917/editores-de-c%C3%B3digo-acb551c8f911',
      },
      {
        titulo : 'Vim <Esquemas de colores>',
        imagen : 'https://miro.medium.com/max/700/1*y7YkpJXcKrBg8zhl22u_dA.jpeg',
        content: 'Vim al ser un editor el cual se ejecuta desde una terminal en modo texto, resulta realmente útil cuando necesitamos modificar archivos de nuestro proyecto los cuales ya se encuentren en un servidor remoto.',
        url    : 'https://medium.com/@genarocoronel917/vim-esquemas-de-colores-85ee00b97877',
      },
      {
        titulo : 'Coincidencias en arreglo de objetos.',
        imagen : 'https://miro.medium.com/max/584/1*9vuNXBrJwixFqq85rrrZKQ.png',
        content: 'Algunas veces nos encontramos con la problemática de comparar dos arreglos de objetos y verificar si todos los elementos del arreglo 1 existen en el arreglo 2, una vez realizado ese proceso mostramos unicamente los elementos que existen en ambos arreglos.',
        url    : 'https://medium.com/@genarocoronel917/eliminar-duplicados-en-arreglo-de-objetos-301a53662e9d',
      },
    ],
  }),
  methods: {
    open (url) {
      window.open(
        url,
        '_blank'
      )
    },
  },
}
</script>
