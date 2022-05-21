<script>
import FeedbackItem from "./FeedbackItem.svelte";
    export let feedBack = [] //defination of a prop
    console.log(feedBack)
</script>

<main>
    {#each feedBack as fb (fb.id)}
    <FeedbackItem item={fb} on:delete-feedback /> <!--Delete Feedback sends the dispatched state-->
    {/each}
</main>