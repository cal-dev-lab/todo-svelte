<script>
    import TodoForm from "../components/TodoForm.svelte";
    import {todos} from "../stores/todoStore.js";
    import Todo from "../components/Todo.svelte";
</script>

<main>
    <h1 class="text-2xl font-bold text-center text-white md:text-5xl">
        Todo List
    </h1>
    <TodoForm />
    {#each $todos as todo}
        <Todo todo={todo} index={todo.id} />
    {/each}
</main>