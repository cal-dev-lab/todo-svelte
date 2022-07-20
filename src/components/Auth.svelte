<script>
    import { supabase } from "../supabase.js";

    let loading = false;
    let email;

    const handleLogin = async () => {

        try {

            loading = true;
            console.log(email);
            const {error} = await supabase.auth.signIn({email});

            if (error) throw error;
            alert('Check your email for the login link!');

        } catch (error) {

            console.error(err);
            alert(error.error_description || error.message);

        } finally {

            loading = false;

        }

    }
</script>

<h1 class="text-2xl font-bold text-center text-white md:text-3xl">Log in</h1>
<p class="text-center mt-2 text-white">Sign in via Magic Link with your email here.</p>

<form on:submit|preventDefault={handleLogin}>

    <div class="flex flex-col text-sm mb-2">

        <label class="font-bold mb-2 text-white" for="email">Email</label>
        <input type="email" name="email" class="appearance-none shadow-sm border border-indigo-500 p-2 focus:outline-none focus:border-indigo-300 rounded-lg" placeholder="johndoe@doemail.com" bind:value={email} />

    </div>

    <button
        type="submit"
        class="w-full shadow-sm rounded bg-blue-500 hover:bg-blue-600 text-white py-2 px-4"
    >
        Log in
    </button>

</form>