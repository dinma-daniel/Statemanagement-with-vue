<template>
    <div class="main">
<h1 class="counter">{{ counter }}</h1>
<button class="side" @click="(subtractToCounter(parseInt(value)))">-</button>
<input type="number" v-model="value">
<button class="side" @click="addToCounter(parseInt(value))">+</button>
    </div>
    <button class="random" @click="addRandomNumber">Add random number</button>
</template>

<script>
import { mapState, mapMutations, mapActions } from "vuex"

export default {
    name: 'Counter',
    components: {
      
    },
    data()
    {
        return{
            value: 0,
           
        }
    },
    computed: {
        ...mapState(["counter"])
    },
    methods: {
        ...mapMutations(["addToCounter", "subtractToCounter"]),
        ...mapActions(["addRandomNumber"])
    }
}
</script>

<style >

.side{
    border: none;
    border-radius: 100%;
    height: 2rem;
    width: 2rem;
    background-color: #42b983;
    color: white;
}

.random{
     border: none;
     border-radius: 7px;
     margin: 1rem 0.5rem;
     background-color: #42b983;
     color: white;
     padding: 0.4rem 2rem;
}

input{
    padding: 0.4rem;
    margin: 0 0.5rem;
    text-align: center;
    border-radius: 7px;
    border: 1px solid black;
}
</style>