<script>
  let list = [];
  let list_item = "";
  function clickable() {
    list.push({ item: list_item });
    list = list;
  }
  function remove_item(item) {
    list.splice(item, 1);
    list = list;
  }
</script>

<section>
  <h1>TO-DO LIST</h1>

  <div>
    <input
      type="text"
      placeholder="New task"
      class="text-input"
      bind:value={list_item}
    />
    <input type="submit" class="btn-submit" on:click={clickable} />
  </div>

  <div class="main-list">
    <ul>
      {#each list as { item }}
        <li>
          <i class="fas fa-trash" on:click={remove_item(item)} />{item}
        </li>
        <hr />
      {/each}
    </ul>
  </div>
</section>

<style>
  section {
    text-align: center;
  }
  h1 {
    font-size: 3.5rem;
    color: #fff;
    margin: 0;
    margin-bottom: 20px;
    font-style: normal;
  }

  div {
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
    margin-top: 30px;
    background-color: #fff;
    border-radius: 10px;
    width: 42rem;
    padding: 20px 0;
  }
  input {
    font-size: 2rem;
    border: none;
  }
  input:focus {
    outline: none;
  }
  .btn-submit {
    background-color: #3c6ffb;
    padding: 8px 15px;
    font-size: 1.8rem;
    color: #fff;
    border-radius: 10px;
  }

  .main-list {
    text-align: left;
  }

  hr {
    margin: 0;
    width: 90%;
  }
  ul {
    list-style: none;
    font-size: 2rem;
  }

  i {
    float: right;
    margin: 5px 10%;
  }
</style>
