<script>
    import {addTodo} from "../stores/todoStore.js"
    let todo = '';
    const handleSubmit = () => {
        addTodo(todo);
        todo = '';
        console.log('todo added');
    }
</script>

<form class="my-6" on:submit|preventDefault={handleSubmit}>

    <div class="flex flex-col text-3xl mb-2">
    
        <label class="font-bold mb-2 text-white" for="todo">Todo</label>
        <input bind:value={todo} name="todo" placeholder="Add a todo" class="appearance-none shadow-sm border border-gray-200 p-2 focus:outline-none focus:border-gray-500 rounded-lg" />

    </div>

    <!-- 
        START:
        Only allow todo item to be added if char count is >= 3
    -->
    {#if todo.length < 3}

        <button type="submit" class="w-full shadow-sm rounded bg-gray-500 hover:bg-gray-400 text-white py-2 px-4" disabled>
            Item must contain 3 characters or more
        </button>

    {:else}

        <button type="submit" class="w-full shadow-sm rounded bg-green-500 hover:bg-green-400 text-white py-2 px-4">
            Add item
        </button>

    {/if}
    <!-- 
        END:
        Only allow todo item to be added if char count is >= 3
    -->

</form>