<template>
  <div class="project">
    <img src="../assets/logo.png"/>
    <p>this is project built on vue

      <br>
      category = {{category}}
    </p>
  </div>
</template>

<script>
export default {
  name: 'Project',
  props: {
    category: String,
  },
  data: function(){
    return {
      // category: this.category
    }
  }
}
</script>

<style lang="scss" scoped>
.project{
  display: flex;
  align-items: center;
}
</style>
