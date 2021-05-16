<template>
  <div>
    <CheckboxFilter @emit="updateCheckbox"/>
    <Projects :checkedNames="checkedNames"/>
  </div>
</template>

<script>
import Projects from './Projects';
import CheckboxFilter from './CheckboxFilter';

export default {
  name: 'ProjectsTab',
  components: {
      CheckboxFilter,
      Projects,
  },
  data: function() {
    return {
      checkedNames: [],
    }
  },
  props: {
  },
  methods: {
    updateCheckbox: function(checkedNames){
      this.checkedNames = checkedNames
    },

  }
}
</script>

<style lang="scss" scoped>

</style>
