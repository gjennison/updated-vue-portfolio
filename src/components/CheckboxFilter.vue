<template>
  <div class="checkboxFilter">
    <div class="active filter all" @click="emit('all')">
      all
    </div>
    <div class="filter vue" @click="emit('vue')">
      vue
    </div>
    <div class="filter react" @click="emit('react')">
      react
    </div>
    <div class="filter bulma" @click="emit('bulma')">
      bulma
    </div>
    <div class="filter wordpress" @click="emit('wordpress')">
      wordpress
    </div>
  </div>

</template>

<script>
export default {
  name: 'CheckboxFilter',
  data: function() {
    return {
      checkedNames: ["all"]
    }
  },
  props: {
  },
  methods: {
    emit: function(tech){
      if(this.checkedNames.includes('all')) {
        this.checkedNames = []
      }
      if(this.checkedNames.includes(tech)) this.checkedNames.splice(this.checkedNames.indexOf(tech), 1);
      else this.checkedNames.push(tech)

      console.log(this.checkedNames)
      console.log(tech)
      this.$emit('emit',this.checkedNames);


      let tab = document.querySelector(`.checkboxFilter .${tech}`)


      let tabs = document.querySelectorAll('.filter');
      if(tech === 'all'){
        for (let index = 0; index < tabs.length; index++) {
          let element = tabs[index];
          element.classList.remove('active')
        }
        tabs[0].classList.add('active')
      }
      else{
        tabs[0].classList.remove('active');
        tab.classList.toggle('active');
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.checkboxFilter{
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 24px;
  margin-bottom: 24px;

  .filter{
    cursor: pointer;
    padding: 12px;
    border-radius: 5px;
    margin: 4px;
    &:hover{
      background-color: rgba(200,150,250,0.2);
    }
  }

  .active{
    background-color: rgba(200,100,250,0.5);
  }
}
</style>
