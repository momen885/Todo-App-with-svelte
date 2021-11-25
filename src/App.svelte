<script>
  import Todo from "./components/Todo.svelte";
</script>

<main class="container">
  <header class="header">
    <h1>Todo App</h1>
  </header>
  <div class="form-container">
    <Todo />
  </div>
</main>

<style>
  .header {
    border: 1px solid #000;
    border-radius: 15px;
    width: 100%;
    max-width: 700px;
  }
  .header h1 {
    text-align: center;
  }
  .form-container {
    width: 100%;
    margin: 20px 0;
  }
</style>
