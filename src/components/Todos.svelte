<script>
  import TodoItem from "./TodoItem.svelte";
  export let todoList;
  export let removeTodo;
</script>

<div>
    { #each todoList as todo }
        <TodoItem {todo} { removeTodo } />
    { /each }
</div>