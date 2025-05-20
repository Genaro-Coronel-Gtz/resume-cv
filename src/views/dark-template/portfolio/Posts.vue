<template>
  <v-container
    fluid
    grid-list-xl
    style="background-color: #424242;"
    class="mt-4"
  >
    <h1
      style="color: white; 
      margin-bottom: 1.2rem; 
      text-align:center"
      class="mx-auto"
    >
      Blog
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
        style="border-radius: 15px"
      >
        <v-img
          class="white--text align-end"
          height="200px"
          :src="post.imagen"
        />
        <v-card-text>
          <v-layout row align-center>
            <v-flex xs8>
              <strong> {{ post.titulo }} </strong>
            </v-flex>
            <v-flex xs4 class="text-right" style="text-align: right;">
              <v-icon class="mr-2">mdi-blogger</v-icon>
              <v-icon>mdi-newspaper-variant</v-icon>
            </v-flex>
          </v-layout>
          <div>{{ post.content }}</div>
        </v-card-text>
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
        imagen : 'https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgEqChV-GQ7zkE0LNvH5VI9sHpUnJwT2mxBl19zyNWUCiGpX_Ky7HiEVL6sufMCin8-WvzH44apOOt7XmI0I7-aCYZl2-FtUQk9TuhATuTXucogl1p_QCJv6rv639rui-f2KcM9oqnDahUNTOmY9X69oLgotfKE5iy633Rfx0KsEsUl9qXG7mJhlWpj3Pg-/s1120/Editores_codigo.jpg',
        content: 'En todo proceso de creación es imprescindible el uso de herramientas, tal es el caso de desarrollo de software en el cual la herramienta mas preciada termina siendo nuestro editor de código, éste junto a la gran diversidad de complementos que existen nos hacen la vida mas fácil al momento de escribir software.',
        url    : 'https://medium.com/@genarocoronel917/editores-de-c%C3%B3digo-acb551c8f911',
      },
      {
        titulo : 'Vim <Esquemas de colores>',
        imagen : 'https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgW6Kl6Qs4HGZE3T2JCYTsJEA91hSaB-5YeBmdbPuMoXaYKBIIuTqQeAufYveOjMQUz4d6ryz8vjALUAewLZ5n22vjxCAVYyVXGyyg2betUhhOCaLaKN0s8nM_vtvjD4Nd4IsTRSS9thCVf9liYD7K8OfeH4mzuf35Sps3Xq_5fZfAy871_eL65dFxPaY96/w945-h600-p-k-no-nu/Vim%20-%20Esquema%20de%20colores(1).jpg',
        content: 'Vim al ser un editor el cual se ejecuta desde una terminal en modo texto, resulta realmente útil cuando necesitamos modificar archivos de nuestro proyecto los cuales ya se encuentren en un servidor remoto.',
        url    : 'https://medium.com/@genarocoronel917/vim-esquemas-de-colores-85ee00b97877',
      },
      {
        titulo : 'Coincidencias en arreglo de objetos.',
        imagen : 'https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjT0tJ7RIe-oapT-A8j8dtdDvQQRXUoAaFYz-4R7VtCQ4qYCEIy_06EgGk4Tf9ShlfwAfA-YUaclMlmJhxOL9jrr2nGClSbGSrtkfytNTMivJtWliu1YrssVLflu3L1IKjdp1g8zMbh6mWSN2_u2QCkZkqPBb6l7_8k_Cg8-tvkr32KiOKE-Qz4_m8yJT9h/w945-h600-p-k-no-nu/ChatGPT%20Image%20May%2020,%202025,%2010_51_28%20AM.png',
        content: 'Algunas veces nos encontramos con la problemática de comparar dos arreglos de objetos y verificar si todos los elementos del arreglo 1 existen en el arreglo 2, una vez realizado ese proceso mostramos unicamente los elementos que existen en ambos arreglos.',
        url    : 'https://medium.com/@genarocoronel917/eliminar-duplicados-en-arreglo-de-objetos-301a53662e9d',
      },
      // {
      //   titulo : 'Mikrotik con VirtualBox.',
      //   imagen : 'https://miro.medium.com/max/584/1*9vuNXBrJwixFqq85rrrZKQ.png',
      //   content: 'En ocasiones necesitamos hacer pruebas en diferentes sistemas operativos, tal es el caso del famoso firewall oepn source mikrotik',
      //   url    : 'https://medium.com/@genarocoronel917/eliminar-duplicados-en-arreglo-de-objetos-301a53662e9d',
      // },
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
