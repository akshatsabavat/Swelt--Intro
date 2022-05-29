<script>
    import { fade, scale } from 'svelte/transition'
    import FeedbackItem from "./FeedbackItem.svelte";
    export let feedBack = [] //defination of a prop
    console.log(feedBack)
</script>

<main>
    {#each feedBack as fb (fb.id)}
    <div in:scale out:fade={{duration: 500}}>
    <FeedbackItem item={fb} on:delete-feedback /> <!--Delete Feedback sends the dispatched state-->
    </div>
    {/each}
</main>