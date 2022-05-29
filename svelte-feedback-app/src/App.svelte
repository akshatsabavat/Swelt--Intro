<script>
import FeedbackForm from "./component/FeedbackForm.svelte";
import FeedbackList from "./component/FeedbackList.svelte";
import FeedbackStats from "./component/FeedbackStats.svelte";
</script>

<main class="container">
	<FeedbackForm/>
	<FeedbackStats/>
	<!--passing item to prop-->
	<FeedbackList/>
</main>

<style>
</style>