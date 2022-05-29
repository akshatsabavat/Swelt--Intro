<script>
    import { fade, scale } from 'svelte/transition'
    import FeedbackItem from "./FeedbackItem.svelte";
    import { FeedbackStore } from "../FeedbackStore"
    console.log(feedBack)
</script>

<main>
    {#each $FeedbackStore as fb (fb.id)}
    <div in:scale out:fade={{duration: 500}}>
    <FeedbackItem item={fb} on:delete-feedback /> <!--Delete Feedback sends the dispatched state-->
    </div>
    {/each}
</main>