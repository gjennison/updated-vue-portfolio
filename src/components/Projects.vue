<template>
  <div class="projects">
      <Project category="vue" v-show="vue"/>
      <Project category="react" v-show="react"/>
      <Project category="bulma" v-show="bulma"/>
      <Project category="wordpress" v-show="wordpress"/>
  </div>
</template>

<script>
import Project from './Project';

export default {
  name: 'Nav',
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
