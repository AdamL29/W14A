<template>
    <div class="loud">
        <button @click="newJoke">Loud Joke</button>
        <div v-for="joke in jokes" :key="joke">
            <h2>{{jokes.joke}}</h2>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: `LoudJokes`,
    data() {
        return {
            jokes: [],
        }
    },
    methods: {
        newJoke() {
            window.location.reload();
        },
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
    },
}
</script>

<style scoped>
    .loud{
        font-variant-caps: all-petite-caps;
    }
</style>