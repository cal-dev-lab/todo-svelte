<script>
    import {addTodo} from "../stores/todoStore.js"
    let todo = '';
    const handleSubmit = () => {
        addTodo(todo);
        todo = '';
        console.log('todo added');
    }

    if (todo.length <= 10) {
        console.log('todo is too short');
    }
</script>

<form class="my-6" on:submit|preventDefault={handleSubmit}>

    <div class="flex flex-col text-3xl mb-2">
    
        <label class="font-bold mb-2 text-gray-800" for="todo">Todo</label>
        <input bind:value={todo} name="todo" placeholder="Add a todo" class="appearance-none shadow-sm border border-gray-200 p-2 focus:outline-none focus:border-gray-500 rounded-lg" />

    </div>

    {#if todo.length <= 10}

    <button type="submit" class="w-full shadow-sm rounded bg-gray-500 hover:bg-gray-400 text-white py-2 px-4" disabled>
        Item must contain 10 characters or more
    </button>

    {:else}

    <button type="submit" class="w-full shadow-sm rounded bg-green-500 hover:bg-green-400 text-white py-2 px-4">
        Add item
    </button>

    {/if}

</form>