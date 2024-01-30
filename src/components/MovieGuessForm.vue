<template>
    <div class="containerTest">
        <img :src="movie.url" :alt="movie.title">
        <form @submit.prevent="submitGuess" class="form">

            <input type="text" v-model="guess" placeholder="Guess the title...">
            <button type="submit">Submit</button>


        </form>
    </div>
</template>
<script>
export default {
    props: ['movie'],
    data() {
        return {
            guess: '',
        };
    },
    methods: {
        submitGuess() {
            if (this.guess.toLowerCase() === this.movie.title.toLowerCase()) {
                alert('Correct!');
            } else {
                alert('Try again!');
            };
            this.guess = '';
        },
    },
}
</script>

<style>
.containerTest {
    width: 100vw;
    background-color: black;
}

img {
    width: 100%;
    max-height: 400px;
}

.form {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto 10px auto;
}

.form input {
    border: 0;
    border-bottom: 1px solid white;
    margin-right: 50px;
    background-color: black;
}

input::placeholder {
    color: white;
}
</style>