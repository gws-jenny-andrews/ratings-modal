<script setup lang="ts">
import { ref } from 'vue';

const rating = ref<number>(0)
const emit = defineEmits(["updateRating"])

const updateRating = (newRating: number) => {
    rating.value = newRating
}

const submitRating = () => {
    if (rating.value === 0) {
        alert("You need to select a rating")
        return
    }
    emit("updateRating", rating)
}
</script>

<template>
    <div class="">
        <div class="icon-wrapper">
            <img src="/images/icon-star.svg" alt="" />
        </div>
        <h1>How did we do?</h1>
        <p>Please let us know how we did with your support request. All feedback is appreciated
            to help us improve our offering!</p>
        <div class="ratings-wrapper">
            <button @click="() => updateRating(index)" class="rating-button" v-for="index in 5">
                {{ index }}
            </button>
        </div>

        <button @click="submitRating" class="submit">Submit</button>

    </div>
</template>

<style scoped>

.icon-wrapper {
    height: 40px;
    width: 40px;
    border-radius: 100%;
    background-color: var(--neutral-400);
    display: flex;
    justify-content: center;
    align-items: center;
}

.ratings-wrapper {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    width: 100%;
    margin-top: 25px;
}


.rating-button {
    border-radius: 100%;
    border: none;
    background: var(--neutral-400);
    padding: 0px 20px;
    width: 42px;
    height: 42px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: var(--neutral-200);
    cursor: pointer;
}

.rating-button:hover {
    background-color: var(--primary-100);
    color: var(--neutral-100);
}

.rating-button:focus {
    background-color: var(--neutral-300);
    color: var(--neutral-100);
}

button.submit {
    margin-top: 25px;
    background-color: var(--primary-100);
    width: 100%;
    border: none;
    color: var(--neutral-100);
    padding: 14px 0 12px 0;
    border-radius: 30px;
    text-transform: uppercase;
    letter-spacing: 2px;
    font-size: 1.0rem;
}

button.submit:hover {
    background-color: var(--neutral-100);
    color: var(--primary-100);
}



@media (min-width: 480px) {

    .icon-wrapper {
        height: 50px;
        width: 50px;
    }

    .ratings-wrapper {
        margin-top: 25px;
    }

    .rating-button {  
        padding: 0px 20px;
        width: 52px;
        height: 52px;
    }

    button.submit {
        margin-top: 30px;
        padding: 12px 0 10px 0;
        border-radius: 30px;
        letter-spacing: 2px;
        font-size: 1.1rem;
    }
}
</style>