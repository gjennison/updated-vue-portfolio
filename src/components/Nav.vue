<template>
  <div class="nav">
      <div class="tab active projects" @click="projectsClicked">
        <h2>projects</h2>
        <div class="border"></div>
      </div>
      <div  class="tab about" @click="aboutClicked">
        <h2>about</h2>
        <div class="border"></div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Nav',
  props: {
  },
  methods: {
      projectsClicked: function(){
          let tabs = document.querySelectorAll('.tab');

          tabs[0].classList.add('active');
          tabs[1].classList.remove('active');

          this.$emit('projectsClicked');
      },
      aboutClicked: function(){
          let tabs = document.querySelectorAll('.tab');
          
          tabs[0].classList.remove('active')
          tabs[1].classList.add('active')

          this.$emit('aboutClicked');
      }
  }
}
</script>

<style lang="scss" scoped>
.nav{
    display: flex;
    justify-content: center;


    .tab{
        h2{
            cursor: pointer;
            padding: 24px;
            margin: 0px;
            transition: background-color 0.2s;
            border-radius: 4px;

            &:hover{
                background-color: rgba(100,200,255,0.2);
            }
        }
        margin: 8px;

        .border{
            position: relative;
            top: -4px;
            height: 4px;
            transition: all 0.2s;
            background-color: rgb(80,180,255);
            opacity: 0;
            border-radius: 4px;
        }
    }

    .tab.active{
        .border{
            opacity: 0.5;
        }
    }
}
@media screen and (min-width: 800px){
    .nav{
        margin-left: 15%;
        margin-right: 15%;
    }
}
</style>
