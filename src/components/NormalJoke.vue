<template>
    <div class="normal">
        <button @click="newJoke">Normal Jokes</button>
        <div v-for="joke in jokes" :key="joke">
            <h2>{{jokes.joke}}</h2>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: `NormalJokes`,
    data() {
        return {
            jokes: []
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

</style>