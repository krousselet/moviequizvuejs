<template>
    <div class="containerTest">
        <img :src="serie.url" :alt="serie.title">
        <form @submit.prevent="submitGuess" class="form">
            <div id="answerHandler container">
                <input type="text" v-model="guess" placeholder="Guess the title...">
                <button type="submit">Submit</button>
            </div>

        </form>
    </div>
</template>
<script>
export default {
    props: ['serie'],
    data() {
        return {
            guess: '',
        };
    },
    methods: {
        submitGuess() {
            if (this.guess.toLowerCase() === this.serie.title.toLowerCase()) {
                alert('Correct!');
            } else {
                alert('Try again!');
            };
            this.guess = '';
        },
    },
}
</script>

<style scoped></style>