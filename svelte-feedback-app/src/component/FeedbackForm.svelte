<script>
import Button from "./Button.svelte";
import Card from "./Card.svelte";

    const minWordLenght = 10
    let text =''
    let btnDisabled = true
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
</script>

<main>
    <Card>
        <header>
            <h2>How would you rate your service with us ?</h2>
        </header>
        <form>
            <div class="input-group">
                <input type="text" placeholder="Tell us something" on:input={lenghtCheck} bind:value={text}> <!--bind value sets the observer and sends the text to our declared variable text-->
                <Button disabled={btnDisabled} type="submit">Post review</Button>
            </div>
        </form>
        {#if message}
            {message}
        {/if}
    </Card>
</main>

<style>
</style>