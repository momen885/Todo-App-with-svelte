<script>
  export let todo = [];
  export let removeTodoItem;
</script>

<div class="list-container">
  <h3>{todo.title}</h3>
  <div class="btns">
    <button
      class={todo.completed ? "green" : ""}
      on:click={() => (todo.completed = !todo.completed)}>Completed</button
    >
    <button class="remove" on:click={() => removeTodoItem(todo.id)}
      >Remove</button
    >
  </div>
</div>

<style>
  .list-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    border: 1px solid;
    margin: 20px 0;
    border-radius: 15px;
  }
  h3 {
    border: 1px solid;
  }
  .btns {
    padding: 20px;
  }
  .btns button {
    margin: 0 10px;
  }
  button {
    border: none;
    padding: 10px;
    border-bottom: 2px solid #000;
    cursor: pointer;
  }
  button:hover {
    border-bottom: none;
  }
  .remove {
    background: #ff334eaa;
    color: #ffffff;
    font-weight: bold;
  }
  .green {
    background: #44ff33aa;
    color: #0a0a0a;
  }
</style>
