<script setup lang="ts">
import { ref } from 'vue';
import RatingsPanel from './RatingsPanel.vue';
import ThankYouPanel from './ThankYouPanel.vue';

const rating = ref<number>(0)

const updateRating = (newRating: number) => {
    rating.value=newRating
}

</script>


<template>
    <div class="panel">
    <RatingsPanel v-if="rating===0"
        @updateRating="updateRating"
    />
    <ThankYouPanel v-else 
        :rating="rating"
    />
    </div>
</template>

<style scoped>
.panel {
    width: 100%;
    max-width: 410px;
    background: linear-gradient(#222933, #171e28);
    border-radius: 20px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 25px 25px;
    padding-bottom: 30px;
    text-align: start;
}


:deep(h1) {
    margin-top: 15px;
    font-size: 1.6rem;
}

:deep(p) {
    margin-top: 6px;
    color: var(--neutral-200);
    font-size: 0.93rem;
    line-height: 1.6;
}



@media (min-width: 480px) {

    .panel {
        border-radius: 30px;
        padding: 35px 35px;
        padding-bottom: 35px;
    }

    :deep(h1) {
        margin-top: 25px;
        font-size: 1.86rem;
    }

    :deep(p) {
        margin-top: 5px;
        font-size: 1rem;
        line-height: 1.6;
    }
}
</style>