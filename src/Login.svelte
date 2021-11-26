<script>
    export let user = {loggedIn: false};

    const toggleLogin = () => {
        user.loggedIn = !user.loggedIn;
    } 
</script>

<div>
    {#if user.loggedIn}
    <button on:click={toggleLogin}>
        Log Out
    </button>
    {:else}
    <button on:click={toggleLogin}>
        Log in
    </button>
    {/if}
</div>
