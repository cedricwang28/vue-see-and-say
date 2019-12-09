<template>
    <main>
        <div class="background"></div>
        <div class="grid">
            <!--iterate data in imagesArray array -->
            <div v-for="(items,index) in imagesArray" :key="index">
                <!--bind image source with data in item -->
                <img :src="items.imgsrc"  @click="$emit('speciesClick',items.imgsrc,index)">
            </div>
        </div>
        
    </main>
</template>

<script>
    export default {
        name: 'Credit',
        //props get the data from parent component
        props: {
            imagesArray: Array
        }
    }
</script>

<style scoped>
    main {
        width: 80%;
        height: 400px;
        float: right;

    }

    main .grid {
        display: grid;
        justify-content: space-around;
        grid-template-columns: repeat(5,1fr);
        align-content: center;
        /* align-items: center; */
        
        /* display: flex;
        justify-content: space-around;
        flex-wrap: wrap; */
         
    }
    .grid>div{
        flex: 1;
    }

    .grid img{
       width:60%;
       margin:15% auto;
       
       
    }

    

    @keyframes floating {
        50% {
            transform: translateY(20px)
        }

    }

    img:hover {
        cursor: pointer;
        animation: floating infinite 2s ease-in-out alternate;
       
    }
    img:active {
        transform: scale(1.3);
        
       
    }

    .background{
        background-image: url(../assets/undersea.png);
        position: absolute;
        z-index: -3;
        width: 80%;
        height: 400px;
        background-size: cover;
        filter:blur(8px);
        opacity: 0.8;
    }
</style>