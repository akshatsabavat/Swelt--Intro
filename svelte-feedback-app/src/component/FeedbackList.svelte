<script>
import FeedbackItem from "./FeedbackItem.svelte";
    export let feedBack = [] //defination of a prop
    console.log(feedBack)
</script>

<main>
    <h2>This is the FeedbackList below</h2>
    {#each feedBack as fb (fb.id)}
    <FeedbackItem item={fb} on:delete-feedback /> <!--Delete Feedback sends the dispatched state-->
    {/each}
</main>