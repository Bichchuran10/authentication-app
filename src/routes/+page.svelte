<script>
    import user from '../user';
    import Login from '../lib/Login.svelte';

    $: isLoggedIn= $user ===null? false : true;

    const logout=()=>{
        user.update(val=>val=null)
    }
</script>

<h1>Welcome To my webApp</h1>
{#if isLoggedIn}
<h2>Thank You {$user.firstname}  for logging in!</h2>
<input type="button" value="Logout!" on:click={logout}/>
{:else}
<h2>Would you like to log in?</h2>
<Login/> 
{/if}