<template>
  <div class="projects">
      <Project category="wordpress" v-show="wordpress" :info="magicHollow"/>
      <Project category="react" v-show="react" :info="reactSummative"/>
      <Project category="vue" v-show="vue" :info="weather"/>
      <!-- <Project category="wordpress" v-show="wordpress" :info="vueProjects"/> -->
      <Project category="bulma" v-show="bulma" :info="cleaningCompany"/>
      <Project category="vue" v-show="vue" :info="portfolio"/>
      <Project category="react" v-show="react" :info="todo"/>
      <!-- <Project category="vue" v-show="vue" :info="vueProjects"/> -->
      <Project category="vue" v-show="vue" :info="movieSearch"/>
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

      magicHollow: {
        id: "magicHollow",
        title: "Magic Hollow",
        description: "Using Shopify I developed a new theme for the clothing company Magic Hollow. <a href='https://magichollow.co.nz/'>Magic Hollow</a>",
        img: "magichollow.png",
        github: "https://magichollow.co.nz/",
        netlify: "https://magichollow.co.nz/",
      },

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
        description: "Developed using React JS and Express. This is a buy and sell mobile app. It performs GET, POST, PUT, and DELETE requests from a REST API developed using Express, with a server running on Heroku.<br><br> I have two versions: one <a href='https://summative-no-server.netlify.app'>here</a> that uses local data instead of Heroku (this loads faster); and <a href='https://summative.netlify.app'>this one</a> that uses Heroku. It may take a few seconds for the app to load the data.<br><br>It is best viewed in the mobile view on dev tools.",
        img: "buy-and-sell.png",
        github: "https://github.com/gjennison/summative",
        netlify: "https://summative-no-server.netlify.app/",
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
      },

      todo: {
        id: "todo",
        title: "Todo react app",
        description: "A Simple to do list app built in react",
        img: "todo.png",
        github: "https://github.com/gjennison/react-todo",
        netlify: "https://george-todo.netlify.app/",
      },

      movieSearch: {
        id: "movieSearch",
        title: "Movie Database",
        description: "Search for any movie and this app will call a third party API and get all movies which title includes your search query. Developed in Vue",
        img: "movie.png",
        github: "https://github.com/gjennison/movie-search",
        netlify: "https://george-movie-search.netlify.app"
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