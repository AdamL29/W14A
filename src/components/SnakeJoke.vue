<template>
    <div class="snake">
        <button @click="newJoke">Snake Jokes</button>
        <div v-for="joke in jokes" :key="joke">
            <h2 ref="snakeFont">{{jokes.joke}}</h2>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: `SnakeJokes`,
    data() {
        return {
            jokes: []
        }
    },
    methods: {
        newJoke() {
            window.location.reload();
        },
        snakeFont(){
            document.querySelector(`h2`).setAttribute.replace(/ /g, '_');
        }
    },
    mounted () {
        axios.request({
            url: 'https://geek-jokes.sameerkumar.website/api?format=json',
            method: 'GET'
        }).then((response)=>{
            this.jokes = response.data;
            console.log(response);
        }).catch((error)=>{
            console.log(error);
        });
        this.snakeFont()
    },
}
</script>

<style scoped>

</style>