<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section
        title="¿Quien soy?"
      >
        Ingenierio en Mecatronica y desarrollador de Software Méxicano.<br>
        Estoy interesado en diferentes temas de IT incluidas por supuesto programacion, desrraollo web , desarrollo de videojuegos y IoT.
      </content-section>
      <content-section
        v-if="prouds"
        title="¿Orgulloso de?"
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
        title="Educación"
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
        title="Habilidades"
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
        text  : 'Desarrollo de aplicacion para denunciar delitos en la ciudad de Naucalpan de Juárez',
        source: '(C4-24 App - Projecto de Gobierno de México)',
      },
      {
        icon  : 'mdi-truck-delivery-outline',
        text  : 'Desarrollo de aplicaciòn para pedidos a domicilio en San Cristóbal, Chiapas',
        source: '(Servidito  - Proyecto personal)',
      },
      {
        icon  : 'mdi-code-tags-check',
        text  : 'Desarrollo codigo limpio ',
        source: '(Si, leei al tio Bob, El libro de codigo limpio.)',
      },
      {
        icon  : 'mdi-human-greeting',
        text  : 'Siempre se profesional, siempre se amable',
        source: '(No importa que suceda - Se profesional!)',
      },
    ],
    educations: [
      {
        from       : '2009',
        to         : '2014',
        title      : 'Ingenierio en Mecatronica',
        location   : 'Tecnologico Nacional de Mexico (Campus Veracruz)',
        description: 'Antorcha y luz de fuego permanente.',
      },
      {
        from       : '2015',
        to         : '2015',
        title      : 'Curso de seguridad informatica y computo forense',
        location   : 'Duriva',
        description: '',
      },
      {
        from       : '2017',
        to         : '2017',
        title      : 'Diplomado en prótesis biomédicas 3d avanzadas',
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
      {
        title: 'React Framework',
        icon : 'mdi-react',
        value: 95,
      },
      {
        title: 'Ember.js Framework',
        icon : 'mdi-ember',
        value: 80,
      },
      {
        title: 'Ruby on Rails',
        icon : 'mdi-language-ruby-on-rails',
        value: 90,
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
        value: 40,
      },
      {
        title: 'Continuous Integration / Continuous Delivery',
        icon : 'mdi-source-branch-refresh',
        value: 50,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 85,
      },
      { divider: true },
      {
        title: 'Python',
        icon : 'mdi-language-python',
        value: 90,
      },
      {
        title: 'Docker Containers',
        icon : 'mdi-docker',
        value: 75,
      },
      {
        title: 'Mysql',
        icon : 'mdi-database-search',
        value: 80,
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
