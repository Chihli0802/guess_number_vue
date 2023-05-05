<script>
export default {
    data() {
        return {

            mes: "猜一個數字",
            min: 1,
            max: 100,
            guess: null,
            bomb: Math.floor(Math.random() * 100) + 1,
            res: "-"
        }
    },
    methods: {
        gus() {
            if (this.guess < this.bomb && this.guess > this.min) {
                this.min = this.guess;
            }
            if (this.guess == this.bomb) {
                this.mes = "答對了"
                this.min = null
                this.max = null
                this.res = this.guess

            }
            if (this.guess > this.bomb && this.guess < this.max) {
                this.max = this.guess;

            }
            this.guess = null;
        },
        again() {
            window.location.reload();
        }
    },
    mounted() {

    }
}
</script>

<template>

        <div class="guessNum">
            <h1>{{ mes }}</h1>
            <div class="numarea d-flex">
                <p>{{ min }}</p>
                <p>{{ res }}</p>
                <p>{{ max }}</p>
            </div>
            <div class="inbuarea">
                <input v-model="guess" class="input" type="number">
                <button class="btn" type="button" @click="gus">確定</button>
                <button class="btn btn1" type="button" @click="again">再一次</button>
            </div>
        </div>

</template>

<style lang="scss" scoped>


.guessNum {
    width: 300px;
    height: 300px;
    background-color: #6ba066;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-radius: 10px;

    h1 {
        color: white;
    }

    .numarea {
        p {
            margin: 10px 10px;
            color: white;
            font-size: 24px;
        }
    }

    .inbuarea {
        width: 70%;
        display: flex;
        flex-direction: column;

        .input {
            margin-bottom: 12px;
        }

        .btn {
            background-color: white;
            margin-bottom: 12px;

            &:hover {
                background-color: #b3cfb0;
                color: white;
            }

            &:active {
                transform: scale(0.95);
            }
        }


    }
}</style>