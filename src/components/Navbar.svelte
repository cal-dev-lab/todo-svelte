<script>
    import { supabase } from "../supabase.js";
    import { user } from "../stores/authStore.js";

    const logout = () => {
        supabase.auth.signOut();
    };
</script>

<div class="flex my-4 justify-between items-center space-x-4">
    <p class="text-white text-sm font-bold">{$user.email}</p>
    <button 
        class="shadow-sm rounded bg-blue-500 hover:bg-blue-600 text-white py-2 px-4"
        on:click={logout}
    >
        Log out
    </button>
</div>