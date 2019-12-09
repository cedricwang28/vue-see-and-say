<template>
    <div class="history">
        <h2>History</h2>
        <ul>
            <!--iterate data in historyImages array -->
            <li v-for="(item,index) in historyImages" :key="index">
                <img :src="item.src" @click="$emit('historyClick',item.number)">

            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        //naming the component
        name: 'Credit',
        //props get the data from parent component
        props: {
            historyImages: {
                type: Array
            }
        }
    }
</script>

<style scoped>
    .history {
        width: 80%;
        height: 160px;
        background-color: beige;
        float: right;

    }

    ul{
        display: grid;
        justify-content: space-around;
        grid-template-columns: repeat(10,1fr);
       
    }

    li {
        list-style: none;
        flex:1;
        height:100px;
        display: block;
       
    }

    li img {
       
        width: 80%;
        margin:10% auto;
       
    }
    h2{
        margin-top: 8px;
        margin-bottom: 5px;
        font-family: 'Luckiest Guy', cursive;
    }
    img:hover{
        cursor: pointer;
    }
</style>