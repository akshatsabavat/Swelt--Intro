<script>
    import { FeedbackStore } from "../FeedbackStore"
    $: count = $FeedbackStore.lenght
    $: average = $FeedbackStore.reduce((acc, {storeRating}) => {
        acc + storeRating
    },0)
</script>

<main>
    <div class="stats-container">
        <p class="review display">{count} Reviews</p>
        <p class="average-score display">Average Score : {average}</p>
    </div>
</main>

<style>
    .stats-container {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .display{
        font-size: 20px;
        font-weight: 600;
        margin-bottom: 10px;
    }
</style>