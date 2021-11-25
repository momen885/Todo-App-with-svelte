<script>
  import { v4 as v4uuid } from "uuid";
  import TodoItem from "./TodoItem.svelte";

  let todoList = [
    {
      id: 1,
      title: "Reading the news",
      completed: true,
    },
    {
      id: 2,
      title: "Go to the Office",
      completed: true,
    },
    {
      id: 3,
      title: "Reading a book",
      completed: false,
    },
  ];
  const removeTodoItem = (id) => {
    const newTodos = todoList.filter((item) => item.id !== id);
    todoList = newTodos;
  };

  let text = "";
  const handleSubmit = () => {
    const newTodos = { id: v4uuid(), title: text };
    todoList = [newTodos, ...todoList];

    text = "";
  };
</script>

<form class="form" on:submit|preventDefault={handleSubmit}>
  <input type="text" class="input" bind:value={text} />
  <div class="btns">
    <button class="btn">Add Task</button>
  </div>
</form>
{#each todoList as todo (todo.id)}
  <TodoItem {todo} {removeTodoItem} />
{/each}

<style>
  .form {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .input {
    padding: 10px;
    border-radius: 5px;
    margin: 5px 20px;
    width: 300px;
    font-size: large;
  }
  .btn {
    background-color: black;
    color: #fff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    font-weight: bolder;
    cursor: pointer;
  }
</style>
