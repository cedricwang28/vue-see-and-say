<template>
  <footer>
      <p>Team Member: Tianwei Wang, Qian Ma, Karan Sandhu</p>
      <p>Sources: Font(Indie Flower, Lakki Reddy from Google Font), Info(Wikipedia)</p>
      <p>Sources: Audio(Youtube), Image(Google)</p>
      <p>Powered by: Vue Application framework</p>
  </footer>
</template>

<script>
export default {
  //naming the component
  name: 'Footer',
  //props get the data from parent component
  props: {
    
  }
}
</script>

<style scoped>
    footer{
        width: 100%;
        height: 120px;
        background-color:#023859;
        color: white;
        position: relative;
        clear:both;
        padding-top: 15px ;
        
    }
</style>