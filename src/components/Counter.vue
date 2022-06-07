<template>
    <h1>{{ customTitle }}</h1>
    <h3>{{counter}}</h3>
    <p>{{squareCounter }}</p>
    <p>{{squareCounter }}</p>
    <p>{{squareCounter }}</p>
    <p>{{squareCounter }}</p>
    <div>
        <button v-on:click="addValue()">+1</button>
        <button v-on:click="restValue()">-1</button>
    </div>
</template>

<script>
export default {
    props: {
        title: String,
        start: {
            type: Number,
            default: 100,
            // required: true
        }
    },
    data(){
        return{
            counter: this.start
        }
        
    },
    methods:{
        getSquareValue(){
            return this.counter * this.counter
        },
          addValue(){
            this.counter++
        },
        restValue(){
            this.counter--
        }
    },
    computed:{
        squareCounter(){
            return this.counter * this.counter
        },
        customTitle(){
            return this.title || 'Counter'
        }
    }
}
</script>

<style>
button{
    background-color: #64BB87;
    border-radius: 5px;
    border: 1px solid white;
    color: white;
    cursor: pointer;
    margin: 0 5px;
    padding: 5px 15px;
    transition: 0.3s ease-in-out;
}
button:hover{
    background-color: #5aa67b;
    transition: 0.3s ease-in-out;
}
</style>