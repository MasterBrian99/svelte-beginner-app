<script>
  let list = [];
  let item = "";
  function add_Item() {
    if (!item == "") {
      list.push({ id: Date.now(), list_item: item });
      console.log(list);
      list = list;
      item = "";
    }
  }
  function removeItem(id) {
    var removeIndex = list.map((i) => i.id).indexOf(id);
    ~removeIndex && list.splice(removeIndex, 1);
    list = list;
  }
</script>

<section>
  <h1 class="is-size-1 has-text-centered has-text-weight-bold has-text-white">
    TO-DO LIST
  </h1>

  <div class="columns is-mobile is-centered center-div">
    <div class="field has-addons">
      <div class="control">
        <input
          class="input"
          type="text"
          placeholder="Add a new task"
          bind:value={item}
        />
      </div>
      <div class="control">
        <button class="button is-info" on:click={add_Item}> Add </button>
      </div>
    </div>
  </div>
  <div class="columns content is-centered center-div">
    <ol>
      {#each list as items}
        <li on:click={removeItem(items.id)}>
          {items.list_item}
        </li>
      {/each}
    </ol>
  </div>
</section>

<style>
  .center-div {
    margin-top: 30px;
  }
  .center-div input,
  button {
    font-size: 2rem;
  }
  button,
  button:hover,
  button:active,
  button:focus {
    border: 1px solid rgb(39, 8, 122);
  }
  ol {
    margin: 0;
  }
  li {
    font-size: 2rem;
    background-color: #b0e6ff;
    padding: 20px;
    list-style-type: none;
    border-radius: 10px;
  }
  li:hover {
    cursor: pointer;
  }
</style>
