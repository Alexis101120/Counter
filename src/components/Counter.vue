<template>
  <h2>{{titleComputed}}</h2>
  <p> {{counter}} <sup>2</sup> = {{ squareCounter}} </p>
  <div>
      <button v-on:click="decreaseCounter">-1</button>
      <button v-on:click="increaseCounter">+1</button>
  </div>

</template>

<script>
import { computed } from '@vue/reactivity'
export default {
    //Esta es una forma de definir properties
    //props:['title','start']
    //Esta es otra manera
    props:{
        title: String,
        start: {
            type: Number,
            required: true,
            default : 1,
            validator(value){
                return value>100 
            }
        }
    }
    ,
    data(){
        return {
            counter : this.start

        }
    },
    //Aqui van los metodos que podemos mandar llamar
    methods :{
        squareCounterMethod(){
            return this.counter * this.counter
        },
        increaseCounter(){
            this.counter++
        },
        decreaseCounter(){
            this.counter--
        }
    },
    //Las propiedadesc omputadas se guardan en cache
    computed :{
        squareCounter(){
            console.log('squareCounter')
            return this.counter * this.counter
        },
        titleComputed(){
            return this.title || 'Counter'
        }
    }
}
</script>

<style>

button{
    background-color: #64bb87;
    border-radius: 5px;
    border: 1px solid white;
    cursor: pointer;
    margin:0 5px;
    padding: 5px 15px;
    transition: 0.3s ease-in-out;
}

button:hover{
    background-color: #5aa67b;
    transition: 00.3s ease-in-out;
}
</style>
