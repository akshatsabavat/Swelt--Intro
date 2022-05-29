<script>
import FeedbackForm from "./component/FeedbackForm.svelte";
import FeedbackList from "./component/FeedbackList.svelte";
import FeedbackStats from "./component/FeedbackStats.svelte";
	const deleteFeedback = (e) => {
		console.log(e.detail)
		const deletionID = e.detail;
		feedBack = feedBack.filter((item) => item.id != deletionID);
	}

	const addFeedback = (e) => {
		console.log(e.detail); //check for incoming feedback data
		const newFeedback = e.detail
		feedBack = [newFeedback, ...feedBack] //spread operator to add the new feed back before the others
	}
</script>

<main class="container">
	<FeedbackForm on:new-feedback={addFeedback}/>
	<FeedbackStats/>
	<!--passing item to prop-->
	<FeedbackList on:delete-feedback={deleteFeedback}/>
</main>

<style>
</style>