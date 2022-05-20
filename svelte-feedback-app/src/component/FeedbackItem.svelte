<script>
import Card from "./Card.svelte";

    export let item
</script>

<main>
    <Card>
        <div class="numberDis">
            {item.rating}
        </div>
        <div class="closeBtn">X</div>
    </Card>
</main>