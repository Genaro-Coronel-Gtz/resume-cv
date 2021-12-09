<template>
  <v-container
    fluid
    grid-list-xl
    style="background-color: white;"
    class="mt-4"
  >
    <h1
      style="color: gray; margin-bottom: 1.2rem; text-align: center;"
      class="mx-auto"
    >
      Some of my work
    </h1>
    <v-carousel
      :show-arrows="false"
      style="height: 900px;"
    >
      <v-carousel-item
        v-for="(proyecto,i) in proyectos"
        :key="i"
        :interval="8500"
        style="height: 900px;"
      >
        <div v-if="proyecto.extension == 'imagen'">
          <img
            :src="proyecto.imagen"
            style="width:100%; height:900px;"
            :alt="proyecto.imagen"
          >
        </div>
        <div v-else>
          <video
            width="100%"
            height="900px"
            controls
            muted
          >
            <source
              :src="proyecto.imagen"
              type="video/mp4"
            >
            Your browser does not support the video tag.
          </video>
        </div>
      </v-carousel-item>
    </v-carousel>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    duracion_imagen: 8500,
    proyectos      : [
      {
        imagen   : 'img/portafolio/dentalife.png', time     : 8500, extension: 'imagen',
      },
      {
        imagen   : 'img/portafolio/chat_c4.png', time     : 8500, extension: 'imagen',
      },
      {
        imagen   : 'img/portafolio/graficas_c4.png', time     : 8500, extension: 'imagen',
      },
      {
        imagen   : 'img/portafolio/map_c4.png', time     : 8500, extension: 'imagen',
      },
      {
        imagen   : 'img/portafolio/jensuy.png', time     : 8500, extension: 'imagen',
      },
      {
        imagen   : 'img/portafolio/jensuy2.png', time     : 8500, extension: 'imagen',
      },
      {
        imagen   : 'img/portafolio/jensuy_cart.jpg', time     : 8500, extension: 'imagen',
      },
      {
        imagen   : 'img/portafolio/servidito.png', time     : 8500, extension: 'imagen',
      },
      {
        imagen   : 'img/portafolio/selector_avatar.jpg', time     : 8500, extension: 'imagen',
      },
      {
        imagen   : 'img/portafolio/crear_producto_servidito.jpg', time     : 8500, extension: 'imagen',
      },
      // {  imagen: 'img/portafolio/C4-Video.mp4', time: 45000, extension: 'video' },
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
