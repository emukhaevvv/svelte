<script lang="ts">
    let isLogIn = false;

    const changeLogIn = () => {
        isLogIn = !isLogIn;
    }

    const fetchPokemon = async () => {
        const data = await fetch("https://pokeapi.co/api/v2/pokemon/ditto");
        const response = await data.json();
        return response;
    }
</script>

{#if !isLogIn}
    <button on:click={changeLogIn}>Login</button>
{:else}
    {#await fetchPokemon()}
        <div></div>
    {:then response} 
        <div>{response.name}</div>
        {#each response.stats as {base_stat}, i (i)}
            <div>{base_stat}</div>
        {/each}
    {/await}
{/if}