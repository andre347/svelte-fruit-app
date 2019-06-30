<script>
  let newFruit = "";
  let fruit = ["Apple", "Banana"];

  function addFruit() {
    console.log("Adding a new fruit...");
    fruit = [newFruit, ...fruit];
    newFruit = "";
  }

  function removeFruit(fruitToRemove) {
    console.log("removing..");
    console.log(fruitToRemove);
    fruit = fruit.filter(f => f !== fruitToRemove);
  }
</script>

<style>
  h1 {
    color: purple;
  }

  h4 {
    font-style: italic;
  }

  li {
    text-decoration: none;
    margin: 10px;
  }
</style>

<h1>List of Fruit</h1>
<h4>Click fruit to remove..</h4>

<input type="text" placeholder="Add Fruit..." bind:value={newFruit} />
<button on:click={addFruit}>Add Fruit</button>

<ul>
  {#each fruit as f}
    <li on:click={() => removeFruit(f)}> {f} </li>
  {/each}
</ul>
