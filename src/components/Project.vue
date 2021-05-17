<template>
  <div class="project">
    <img :src="info.img"/>
    <div class="content">
      <h3>{{info.title}}</h3>
    <a @click="displayModal" class="view-more">view more</a>
    </div>
    <div class="modal" :id="info.id" @click="closeModal">
      <div class="modal-content">
        <p v-html="info.description">
        </p>
        <a :href="info.github">
          <img src="github.svg" alt="">
        </a>
        <a :href="info.netlify">
          <img src="netlify.png" alt="">
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Project',
  props: {
    info: Object,
  },
  data: function(){
    return {
      // category: this.category
    }
  },

  methods: {
    displayModal: function(){
      let modal = document.querySelector(`#${this.info.id}`);
      modal.style.display = "flex";
    },

    closeModal: function(e){
      if(e.target.classList.contains('modal')){
        e.target.style.display = "none";
      }
    }
  }
}
</script>

<style lang="scss" scoped>

@media screen and (min-width: 750px){
  .project{
    grid-template-columns: 1fr 1fr;
    justify-content: center;
  }
}

.project{
  display: flex;
  align-items: center;

  img{
    object-fit: cover;
    width: 50%;
    // height: 200px;
    border-radius: 8px;
    padding: 12px;
  }

  .view-more{
    cursor: pointer;
    padding: 6px;
    border-bottom: 1px solid rgba(100,200,255,0.5);

    &:hover{
      border-radius: 4px;
      background-color: rgba(100,200,255,0.5);
    }
  }

  .modal{
    display: none;
    position: fixed;
    background-color: rgba(0,0,0,0.2);
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    justify-content: center;
    align-items: center;
  
    .modal-content{
      background-color: rgba(210,210,255,1);
      padding: 32px;
      margin-left: 20px;
      margin-right: 20px;
      width: 90%;
      max-width: 780px;
      line-height: 1.5em;
      

      a img{
        width: 48px;
      }

      ul{
        list-style: none;
        li{
          font-weight: bold;
        }
      }
    }
  }
}
</style>
