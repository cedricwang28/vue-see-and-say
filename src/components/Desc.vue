<template>
  <aside>
      <h2>Animal Card</h2>
        <div class="wrapper">
          <!--iterate data in clickedAnimal array -->
          <div v-for="(item,index) in clickedAnimal" :key="index">
                <h1>
                <!--get data from current item -->
                What's {{item.name}} ?
                </h1>
                <p>
                    <!--get data from current item -->
                    {{item.desc}}
                </p>
          </div>
        </div>
        <div class="logo">
          <p>KIDS'</p>
          <p>AQUARIUM</p>
        </div>
  </aside>
</template>

<script>
export default {
  //naming the component
  name: 'Intro',
  //props get the data from parent component
  props: {
    clickedAnimal:{
      type:Array
    }
  }
}
</script>

<style scoped>
    aside{
        width: 20%;
        height: 560px;
        background-color:#50A0BF;
        float: left;
        border-radius: 2%;
        border: black 2px dashed;
        box-sizing: border-box;
    }
    h2{
      font-family: 'Luckiest Guy', cursive;
      margin-top: 28px;
    }
    p{
      margin-top: 0px;
      font-family: 'Indie Flower', cursive;
      font-size: 16px;
    }
    .wrapper{
      background-color: #fff;
      margin-top: 6px;
      margin-left: 8px;
      margin-right: 8px;
      padding: 5px 5px;
      height: 320px;
      border-radius: 10px;
    }
    h1{
      color:#025373;
    }
    .logo{
      background-color: #96C6D9;
      width: 100%;
      height:160px;
      margin-top: 9px;
      border-top: black 2px dashed;
      
    }
    .logo p{
      font-size: 46px;
      line-height: 60px;
      font-family: 'Lakki Reddy', cursive;
    }
    .logo p:first-child{
      padding-top: 30px;
    }
</style>