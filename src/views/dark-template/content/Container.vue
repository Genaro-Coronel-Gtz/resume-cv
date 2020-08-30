<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section
        title="Who am I?"
      >
        I'm a Mechatronic Enginner and software developer born in Mexico, co-founder of <a href="http://www.dim3nsoft.com">Dim3nsoft</a> and <a href="http://servidito.com"> Servidito </a>.<br><br>
        I'm interested and skilled in different topics of Information Technology including programming, web development, and IoT.
      </content-section>
      <content-section
        v-if="prouds"
        title="Proud of?"
      >
        <v-layout
          v-for="(proud, i) in prouds"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ proud.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ proud.text }}</strong><br>
              <small>{{ proud.source }}</small>
            </p>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="educations"
        title="Education"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md4>
            {{ education.from }} - {{ education.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="skills"
        id="to-timeline"
        title="Skills"
      >
        <template slot="actions">
          (% are relative not absolute)
        </template>
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div
                class="mr-2 ml-2"
              >
                <div class="align-center">
                  <v-icon
                    small
                  >
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }}
                </div>
                <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="skill.value"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    prouds: [
      {
        icon  : 'mdi-police-badge',
        text  : 'Development of application to report crimes in the city of Naucalpan!',
        source: '(C4-24 App - Government project)',
      },
      {
        icon  : 'mdi-truck-delivery-outline',
        text  : 'Development of application for home orders in San Cristóbal, Chiapas',
        source: '(Servidito  - Personal project )',
      },
      {
        icon  : 'mdi-code-tags-check',
        text  : 'Develop clean code ',
        source: '(Yes, i read uncle bob, clean code book!)',
      },
      {
        icon  : 'mdi-human-greeting',
        text  : 'Always be profesional, always be kind!',
        source: '(No matters what happend - Be profesional!)',
      },
    ],
    educations: [
      {
        from       : '2009',
        to         : '2014',
        title      : 'Bachelor\'s degree, Mechatronic enginner',
        location   : 'Tecnologico Nacional de Mexico (Campus Veracruz)',
        description: 'Antorcha y luz de fuego permanente.',
      },
      {
        from       : '2015',
        to         : '2015',
        title      : 'Computer security course and forensic computing',
        location   : 'Duriva',
        description: '',
      },
      {
        from       : '2017',
        to         : '2017',
        title      : 'Diploma in advanced 3d biomedical prostheses',
        location   : 'P4H',
        description: '',
      },
    ],
    skills: [
      {
        title: 'PHP',
        icon : 'mdi-language-php',
        value: 87,
      },
      {
        title: 'JavaScript',
        icon : 'mdi-language-javascript',
        value: 90,
      },
      {
        title: 'Laravel Framework',
        icon : 'mdi-laravel',
        value: 95,
      },
      {
        title: 'Vue.js Framework',
        icon : 'mdi-vuejs',
        value: 95,
      },
      { divider: true },
      {
        title: 'Ionic Framework',
        icon : 'mdi-ionic',
        value: 90,
      },
      {
        title: 'Slim Framework',
        icon : 'mdi-linux',
        value: 80,
      },
      {
        title: 'Angular',
        icon : 'mdi-angular',
        value: 80,
      },
      {
        title: 'Test Driven Development',
        icon : 'mdi-test-tube',
        value: 26,
      },
      {
        title: 'Continuous Integration / Continuous Delivery',
        icon : 'mdi-source-branch-refresh',
        value: 30,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 75,
      },
      { divider: true },
      {
        title: 'Python',
        icon : 'mdi-language-python',
        value: 70,
      },
      {
        title: 'Docker Containers',
        icon : 'mdi-docker',
        value: 32,
      },
      {
        title: 'Mysql',
        icon : 'mdi-database-search',
        value: 56,
      },
      {
        title: 'Css',
        icon : 'mdi-language-css3',
        value: 70,
      },
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
