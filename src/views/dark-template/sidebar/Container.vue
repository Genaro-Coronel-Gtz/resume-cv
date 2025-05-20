<template>
  <v-card
    color="grey darken-3"
    dark
  >
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          Genaro <span style="color: #B2D7E8"> Coronel </span>
        </h1>
        <span>
          Ingeniero en Mecatronica
        </span><br>
        <span>
          Desarrollador Full Stack
        </span>
      </div>

      <sidebar-section :options="sections.info" />
      <sidebar-section :options="sections.socials" />
      <sidebar-section :options="sections.hobbies">
        <template v-slot:item="{item}">
          <v-chip>
            <v-avatar>
              <v-icon>
                {{ item.icon }}
              </v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>
      <sidebar-section :options="sections.languages">
        <template v-slot:items="{items}">
          <v-container pa-0>
            <v-layout
              wrap
              class="text-xs-center"
            >
              <template
                v-for="(item, i) in items"
              >
                <v-flex
                  v-key="i"
                  md3
                  sm4
                  xs6
                >
                  <v-progress-circular
                    rotate="360"
                    size="65"
                    width="2"
                    :value="item.value"
                    color="white"
                    class="ma-2"
                  >
                    {{ item.text }}
                  </v-progress-circular>
                </v-flex>
              </template>
            </v-layout>
          </v-container>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import Avatar from '@/views/dark-template/sidebar/Avatar'
import SidebarSection from '@/views/dark-template/sidebar/Section'
export default {
  name      : 'Sidebar',
  components: { SidebarSection, Avatar },
  data () {
    return {
      sections: {
        info: {
          title: 'INFO',
          items: [
            {
              name: 'Email',
              icon: 'mdi-email',
              text: 'genarocoronel917@gmail.com',
            },
            {
              name: 'Blog',
              icon: 'mdi-web',
              text: 'https://genarocoronel.blogspot.com/',
            },
            {
              name: 'Birth Date',
              icon: 'mdi-cake-variant',
              text: 'Sep 11, 1990',
            },
            {
              name: 'Ubication',
              icon: 'mdi-map-marker',
              text: 'Chiapas, Mex',
            },
            {
              name: 'Curriculm Vitae',
              icon: 'mdi-file-document',
              text: 'https://tinyurl.com/genaro-coronel',
            },
          ],
        },
        socials: {
          title: 'SOCIAL',
          items: [
            {
              icon: 'mdi-github',
              text: 'github.com/Genaro-Coronel-Gtz',
              link: 'https://github.com/Genaro-Coronel-Gtz',
            },
            {
              icon: 'mdi-linkedin',
              text: 'linkedin.com/in/genaro-coronel-066b17122/',
              link: 'https://www.linkedin.com/in/genaro-coronel-066b17122/',
            },
            {
              icon: 'mdi-twitter',
              text: 'twitter.com/GtzCoronel',
              link: 'https://twitter.com/GtzCoronel',
            },
            {
              icon: 'mdi-instagram',
              text: 'instagram.com/genarocoronel',
              link: 'https://instagram.com/genaro_Coronel',
            },
          ],
        },
        hobbies: {
          title: 'HOBBIES',
          items: [

            {
              icon: 'mdi-bike',
              text: 'Cycling',
            },
            {
              icon: 'mdi-auto-fix',
              text: 'Hacking Stuffs',
            },
            {
              icon: 'mdi-teach',
              text: 'Learn new stuff',
            },
            {
              icon: 'mdi-music',
              text: 'Listen music',
            },
            {
              icon: 'mdi-guitar-acoustic',
              text: 'Play ukelele',
            },
            {
              icon: 'mdi-book-open-page-variant',
              text: 'Books',
            },
            {
              icon: 'mdi-android-debug-bridge',
              text: 'Kill Bugs',
            },
          ],
        },
        languages: {
          title: 'IDIOMAS',
          items: [
            {
              text : 'English',
              value: 75,
            },
            {
              text : 'Spanish',
              value: 100,
            },
          ],
        },
      },
    }
  },
}
</script>

<style scoped>
.sidebar{
    background: #2e2e2e;
}
</style>
