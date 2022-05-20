<script>
import Card from "./Card.svelte";

    export let item
    const handleDelete = (itemID) => {
        console.log(itemID);
    }
</script>

<main>
    <Card>
        <div class="numberDis">
            {item.rating}
        </div>
        <div class="closeBtn" on:click={() => handleDelete(item.id)}>X</div>
        <div class="containerText">
            {item.text}
        </div>
    </Card>
</main>

<style>
  .numberDis {
    position: absolute;
    top: -10px;
    left: -10px;
    width: 50px;
    height: 50px;
    background: #ff6a95;
    color: #fff;
    font-weight: 700;
    border: 1px #eee solid;
    border-radius: 50%;
    padding: 10px;
    text-align: center;
    font-size: 19px;
  }
  .closeBtn {
    position: absolute;
    top: 10px;
    right: 20px;
    cursor: pointer;
    background: none;
    font-weight: 700;
    border: none;
  }
</style>