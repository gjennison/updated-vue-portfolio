<template>
  <div class="about">
    <img class="me" src="me.jpg" alt="">
    <div class="content">
      <p>I'm George, a Front End Developer based in Christchurch. <br><br>
      I am proficient in various Front End technologies such as Vue, React, Typescript, Sass, and more.<br><br>
      I have exprience with basic back end applications in Express JS. Currently I'm learning Django.
      </p>

      <div class="links">
        <p class="link"><a href="https://github.com/gjennison"><img src="github.svg" alt=""><span>gjennison</span></a></p>
        <p class="link"><a href="tel:0212512773"><img src="phone.svg" alt=""><span>021 251 2773</span></a></p>
        <p class="link"><a href="mailto:georjennison@gmail.com"><img src="mail.svg" alt=""><span>georjennison@gmail.com</span></a></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
  props: {
  },
  methods: {
      
  }
}
</script>

<style lang="scss" scoped>
.about{
  margin-top: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-left: 50px;
  margin-right: 50px;
  .me{
    width: 40%;
    border-radius: 50%;
    // box-shadow: 0px 0px 10px springgreen;
    box-shadow: 0px 0px 10px rgba(200,100,250,0.5);
    margin-bottom: 30px;
    max-width: 400px;
    min-width: 100px;
  }

  .content{
    .links{
        font-size: 0.8em;
    }
    .link{
        // width: auto;
        margin-top: 8px;
        margin-bottom: 8px;
        border-radius: 4px;
      a{
        display: flex;
        align-items: center;
        justify-content: center;
        text-decoration: none;
        img{
          width: 30px;
          padding: 8px;
        }
      }

      &:hover{
        background-color: rgba(100, 200, 255, 0.5);
      }
    }
  }
}

@media screen and (min-width: 900px){
  .about{
    flex-direction: row;
    .me{
      margin-right: 5%;
    }

    .content{
      position: relative;
      top: 35px;

      .links{
        display: flex;
        justify-content: space-evenly;
        .link{
          padding: 8px;
        }
      }
    }
  }
}

@media screen and (min-width: 1000px){
  .about{
    .me{
      width: 35%;
    }

    .content{
      top: 30px;

      .links{
        .link{
          // padding: 8px;
        }
      }
    }
  }
}

@media screen and (min-width: 1200px){
  .about{
    .me{
      width: 30%;
    }
  }
}
</style>
