<script>
  import Input from "./components/Input.svelte";
  import Todos from "./components/Todos.svelte";

  let todo = "";
  let todoList = [
    {
      id: 1,
      text: "Learn Svelte",
      completed: false,
    },
    {
      id: 2,
      text: "Build a Svelte app",
      completed: false,
    },
    {
      id: 3,
      text: "Share it with the world",
      completed: true,
    },
  ];

  let lastId = todoList[todoList.length-1]['id']

  function addTodo() {
    if (!todo) return;

    const todos = todoList[todoList.length - 1];
    const nextId = todos ? todos.id + 1 : 1;

    todoList = [
      ...todoList,
      {
        id: nextId,
        text: todo,
        completed: false,
      },
    ];

    todo = "";
    console.log(todoList);
  }

  function removeTodo(id) {
    todoList = todoList.filter(todo => todo.id !== id);
    console.log(todoList);
  }

  let handleKeyUp = e => {
		todo = e.target.value;
		if(e.keyCode === 13) {
			addTodo();
		}
	}
</script>

<main>
  <div>
    <p>Todo List</p>
    <Input { todo } { addTodo } { handleKeyUp }/>
    <Todos { todoList }  { removeTodo }/>
  </div>
</main>