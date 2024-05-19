<script>
  export let todo;
  export let addTodo;
  export let handleKeyUp;
</script>

<div>
  <input type="text" placeholder="할일 입력 ..." bind:value={ todo } on:keyup={e => handleKeyUp(e)}/>
  <button on:click={addTodo()}>ADD</button>
</div>