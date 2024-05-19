<script>
  export let todo;
  export let removeTodo;
</script>

<div>
  <input type="checkbox" checked={ todo.completed }/>
  <p>{ todo.text }</p>
  <button on:click={removeTodo(todo.id)}>X</button>
</div>

<style>
  div {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 10px 0;
  }
</style>