<script setup lang="ts">

interface ThankYouProps {
    rating: number
}

const { rating } = defineProps<ThankYouProps>()

</script>

<template>
    <div class="">
        <div class="icon-wrapper">
            <img class="wrapper" src="/images/illustration-thank-you.svg" alt="" />
        </div>
        <div class="rating-wrapper">
            <div class="rating">You selected {{ rating }} out of 5</div>
        </div>
        <h1>Thank you!</h1>
        <p>We appreciate youtaking the time to give a rating. If you ever need more support, don't hesitate to get in
            touch </p>


    </div>
</template>

<style scoped>
.icon-wrapper {
    margin-top: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
}

img {
    max-height: 96px;
}

.rating-wrapper {
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 100%;
    margin-top: 25px;
}

.rating {
    background-color: var(--neutral-400);
    padding: 7px 20px 4px 20px;
    color: #ab7857;
    border-radius: 30px;
    font-size: 0.9rem;
    margin-bottom: 6px;
}




h1 {
    text-align: center;
}

p {
    text-align: center;
    font-size: 0.95rem;
    margin-bottom: 10px;
}

@media (min-width: 480px) {



    .rating-wrapper {
        margin-top: 25px;
    }

    img {
        max-height: 110px;
    }

    .rating-wrapper {
        display: flex;
        flex-direction: row;
        justify-content: center;
        width: 100%;
        margin-top: 30px;
    }

    .rating {
        background-color: var(--neutral-400);
        padding: 7px 20px 4px 20px;
        color: #ab7857;
        border-radius: 30px;
        font-size: 1rem;
        margin-bottom: 6px;
    }




    h1 {
        text-align: center;
    }

    p {
        text-align: center;
        font-size: 1rem;
        margin-bottom: 10px;
    }


}
</style>