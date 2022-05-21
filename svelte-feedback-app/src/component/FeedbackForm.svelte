<script>
import Button from "./Button.svelte";
import Card from "./Card.svelte";
import FeedbackRatings from "./FeedbackRatings.svelte";

    const minWordLenght = 10
    let text =''
    let btnDisabled = true
    let rating = 10
    let message

    const lenghtCheck = () => {
        if(text.trim().length <= minWordLenght){
            message = `Review should be of atleast ${minWordLenght} charecters`
            btnDisabled = true
        }else {
            message = null
            btnDisabled = false
        }
    }

    const postRating = (e) => {
        rating = e.detail
    }

    const postReview = () => {
        const newFeedBack = {
            id: 1,
            rating: +rating,
            text: `${text}`
        }
        console.log(newFeedBack)
    }
</script>

<main>
    <Card>
        <header>
            <h2>How would you rate your service with us ?</h2>
        </header>
        <FeedbackRatings on:rating-select={postRating}/>
        <form on:submit|preventDefault={postReview}>
            <div class="input-group">
                <input type="text" placeholder="Tell us something" on:input={lenghtCheck} bind:value={text}> <!--bind value sets the observer and sends the text to our declared variable text-->
                <Button disabled={btnDisabled} type="submit">Post review</Button>
            </div>
        </form>
        <div class="message">
            {#if message}
            {message}
        {/if}
        </div>
    </Card>
</main>

<style>
      header {
    max-width: 400px;
    margin: auto;
  }
  header h2 {
    font-size: 22px;
    font-weight: 800;
    text-align: center;
  }
  .input-group {
    display: flex;
    flex-direction: row;
    border: 1px solid #ccc;
    padding: 8px 10px;
    border-radius: 8px;
    margin-top: 15px;
  }
  input {
    flex-grow: 2;
    border: none;
    font-size: 16px;
  }
  input:focus {
    outline: none;
  }
  .message{
    padding-top: 10px;
    text-align: center;
    color: rebeccapurple;
  }
</style>