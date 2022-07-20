<script>
    import {addTodo} from "../stores/todoStore.js"
    let todo = '';
    const handleSubmit = () => {
        addTodo(todo);
        todo = '';
        console.log('Submitting');
    }
</script>

<form class="my-6" on:submit|preventDefault={handleSubmit}>
    <div class="flex flex-col text-sm mb-2">
        <label class="font-bold mb-2 text-gray-800" for="todo">Todo</label>
        <input bind:value={todo} name="todo" placeholder="Add a todo" class="appearance-none shadow-sm border border-gray-200 p-2 focus:outline-none focus:border-gray-500 rounded-lg" />
    </div>
    <button type="submit" class="w-full shadow-sm rounded bg-green-500 hover:bg-green-400 text-white py-2 px-4">Add</button>
</form>