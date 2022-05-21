<script>
    const minWordLenght = 10
    let text =''
    let btnDisabled = true
    let message

    const lenghtCheck = () => {
        text.trim().length <= 10 ? (message = `Review should be of atleast ${minWordLenght} charecters`, btnDisabled = true ): (message = null, btnDisabled = false)

    }
</script>

<main>
    <header>
        <h2>How would you rate your service with us ?</h2>
    </header>

    <form action="">
        <div class="input-group">
            <input type="text" placeholder="Tell us something">
            <button></button>
        </div>
    </form>
</main>

<style>
</style>