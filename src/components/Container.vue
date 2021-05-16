<template>
  <div class="hello">
    <Nav @projectsClicked="projectsClicked" @aboutClicked="aboutClicked"/>
    <ProjectsTab v-show="showProjects"/>
    <About v-show="!showProjects"/>
  </div>
</template>

<script>
import Nav from './Nav'
import ProjectsTab from './ProjectsTab'
import About from './About'

export default {
  name: 'Container',
  components: {
    Nav,
    ProjectsTab,
    About,
  },
  props: {
    msg: String
  },
  data: function(){
    return{
      showProjects: true,
    }
  },
  methods: {
    projectsClicked: function(){
      this.showProjects = true;
    },

    aboutClicked: function(){
      this.showProjects = false;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
