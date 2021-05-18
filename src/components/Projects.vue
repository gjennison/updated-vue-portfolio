<template>
  <div class="projects">
      <Project category="react" v-show="react" :info="reactSummative"/>
      <Project category="vue" v-show="vue" :info="weather"/>
      <!-- <Project category="wordpress" v-show="wordpress" :info="vueProjects"/> -->
      <Project category="bulma" v-show="bulma" :info="cleaningCompany"/>
      <Project category="vue" v-show="vue" :info="portfolio"/>
      <Project category="vue" v-show="vue" :info="vueProjects"/>
  </div>
</template>

<script>
import Project from './Project';

export default {
  name: 'Projects',
  components: {
    Project
  },
  props: {
    checkedNames: Array
  },
  data: function(){
    return{
      vue: true,
      react: true,
      bulma: true,
      wordpress: true,

      vueProjects: {
        id: "vueProjects",
        title: "Three Small Apps",
        description: "Developed in Vue JS this app collects data from third party API's.<br><br>It consists of three small apps.",
        img: "vue-projects.png",
        github: "https://github.com/gjennison/vue-projects",
        netlify: "https://vue-projects.netlify.app/",
      },

      reactSummative: {
        id: "reactSummative",
        title: "Buy and Sell",
        description: "Developed using React JS and Express. This is a buy and sell mobile app. It performs GET, POST, PUT, DELETE requests from a REST API developed with Express, this server is running on Heroku.  It may take a few seconds for the app to load the data.<br><br>It is best viewed in the mobile view on dev tools.",
        img: "buy-and-sell.png",
        github: "https://github.com/gjennison/summative",
        netlify: "https://summative.netlify.app/",
      },

      cleaningCompany: {
        id: "cleaningCompany",
        title: "Cleaning Company",
        description: "A simple website developed with the Bulma CSS framework.",
        img: "cleaning.png",
        github: "https://github.com/gjennison/gjennison.github.io",
        netlify: "https://gjennison.github.io/",
      },

      portfolio: {
        id: "portfolio",
        title: "This Site!",
        description: "This simple website was developed using Vue JS",
        img: "portfolio.png",
        github: "https://github.com/gjennison/updated-vue-portfolio",
        netlify: "https://jennison.design/",
      },

      weather: {
        id: "weather",
        title: "Simple Weather API app",
        description: "Type any city name into this app and it pulls data from a third party weather API, then displays it on a dashboard.",
        img: "weather.png",
        github: "https://github.com/gjennison/weather-app",
        netlify: "https://weather-app-in-vue.netlify.app/"
      }
    }
  },

  watch: {
    checkedNames: function() {
      if(this.checkedNames.includes('vue')) this.vue = true
      else this.vue = false

      if(this.checkedNames.includes('react')) this.react = true
      else this.react = false

      if(this.checkedNames.includes('bulma')) this.bulma = true
      else this.bulma = false

      if(this.checkedNames.includes('wordpress')) this.wordpress = true
      else this.wordpress = false

      if(this.checkedNames.includes('all')){
        this.vue = true;
        this.react = true;
        this.bulma = true;
        this.wordpress = true;
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.projects{
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 20px;
}

@media screen and (min-width: 750px){
  .projects{
    grid-template-columns: 1fr 1fr;
  }
}
</style>