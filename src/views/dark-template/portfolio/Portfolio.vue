<template>
  <v-container fluid grid-list-xl style="background-color: white;" class="mt-4">
    <h1 style="color: gray; margin-bottom: 1.2rem; text-align: center;" class="mx-auto">Some of my work </h1>
    <v-carousel :show-arrows="false">
        <v-carousel-item
        v-for="(proyecto,i) in proyectos"
        :key="i"
        :interval="8500"
        >
        <div v-if="proyecto.extension == 'imagen'" >
            <img :src="proyecto.imagen" style="width:100%; height:auto;" :alt="proyecto.imagen"/>
        </div>
        <div v-else>    
            <video width="100%" height="auto" controls>
              <source :src="proyecto.imagen" type="video/mp4">
              Your browser does not support the video tag.
            </video>
        </div> 
        </v-carousel-item>
  </v-carousel>

  </v-container>
</template>
<script>
  export default {
    methods:{
        open(url){
            window.open(
            url,
            '_blank'
            );
        }
    },
    data: () => ({
        duracion_imagen: 8500,
        posts: [
            { 
              titulo: 'Editores de código', 
              imagen: 'https://miro.medium.com/max/700/1*MSWyC_kFmIJ7NaHmzH9Jqg.jpeg', 
              content: 'En todo proceso de creación es imprescindible el uso de herramientas, tal es el caso de desarrollo de software en el cual la herramienta mas preciada termina siendo nuestro editor de código, éste junto a la gran diversidad de complementos que existen nos hacen la vida mas fácil al momento de escribir software.',
              url: "https://medium.com/@genarocoronel917/editores-de-c%C3%B3digo-acb551c8f911"
            },
            { 
              titulo: 'Vim <Esquemas de colores>', 
              imagen: 'https://miro.medium.com/max/700/1*y7YkpJXcKrBg8zhl22u_dA.jpeg', 
              content: 'Vim al ser un editor el cual se ejecuta desde una terminal en modo texto, resulta realmente útil cuando necesitamos modificar archivos de nuestro proyecto los cuales ya se encuentren en un servidor remoto.',
              url: "https://medium.com/@genarocoronel917/vim-esquemas-de-colores-85ee00b97877"
            },
            { 
              titulo: 'Coincidencias en arreglo de objetos.', 
              imagen: 'https://miro.medium.com/max/584/1*9vuNXBrJwixFqq85rrrZKQ.png', 
              content: 'Algunas veces nos encontramos con la problemática de comparar dos arreglos de objetos y verificar si todos los elementos del arreglo 1 existen en el arreglo 2, una vez realizado ese proceso mostramos unicamente los elementos que existen en ambos arreglos.',
              url: "https://medium.com/@genarocoronel917/vim-esquemas-de-colores-85ee00b97877"
            },
            { 
            titulo: 'Mini Blog con Vue Js (Parte 1)', 
            imagen: 'https://miro.medium.com/max/700/1*7pGtqgYA0ALYItHrLVSwxA.png', 
            content: 'El día de hoy te traigo el primer post de una miniserie en la cual aprenderás a crear un pequeño blog haciendo uso del Vue js , también tocaremos algunos temas puntuales del framework que muchas veces no encontramos de manera concisa implementarlos.',
            url: "https://medium.com/@genarocoronel917/mini-blog-con-vue-js-parte-1-52385cb60fa1"
            },
        ],
        proyectos : [
            {  imagen: 'img/portafolio/dentalife.png', time: 8500, extension: 'imagen' },
            {  imagen: 'img/portafolio/chat_c4.png', time : 8500, extension: 'imagen' },
            {  imagen: 'img/portafolio/graficas_c4.png', time : 8500, extension: 'imagen' },
            {  imagen: 'img/portafolio/map_c4.png', time : 8500, extension: 'imagen' },
            {  imagen: 'img/portafolio/jensuy.png', time : 8500, extension: 'imagen' },
            {  imagen: 'img/portafolio/jensuy2.png', time : 8500, extension: 'imagen' },
            {  imagen: 'img/portafolio/jensuy_cart.jpg', time : 8500, extension: 'imagen' },
            {  imagen: 'img/portafolio/servidito.png', time : 8500, extension: 'imagen' },
            {  imagen: 'img/portafolio/selector_avatar.jpg', time : 8500, extension: 'imagen' },
            {  imagen: 'img/portafolio/crear_producto_servidito.jpg', time : 8500, extension: 'imagen' },
            // {  imagen: 'img/portafolio/C4-Video.mp4', time: 45000, extension: 'video' },
        ]
    }),
  }
</script>
