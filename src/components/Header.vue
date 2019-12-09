<template>
  <header id='header'>
    <!--get the data from props -->
    <h1>{{title}}</h1>
  </header>
</template>

<script>
  export default {
    //naming the component
    name: 'Title',
    //props get the data from parent component
    props: {
      title: String
    }
  }
</script>

<style scoped>
  #header {
    width: 100%;
    height: 72px;
    font-size: 30px;
    background-color: #96C6D9;
    line-height: 80px;
    padding: 0;
    margin: 0;
    font-family: 'Luckiest Guy', cursive;
    padding-top: 8px;

  }

  

</style>