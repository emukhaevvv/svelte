<script lang="ts">
    let list = [{id: 1, title: "Title for Item"}];

    const addNewItem = () => {
        list = [...list, {id: list.length + 1, title: "Title for Item"}]
    }

    $: amount = list.length;
</script>

<div class="content">
    <ul>
        {#each list as item}
            <li>
                <div>id: {item.id}</div>
                <p>{item.title}</p>
            </li>
        {/each}
    </ul>

    <div class="right">
        <button on:click={addNewItem}>Add new Item</button>
        <div>Total items amount: {amount}</div>
    </div>
</div>

<style>
    .content {
        display: flex;
        align-items: start;
        gap: 40px;
    }
    li {
        display: flex;
        align-items: center;
        gap: 20px;
    }
</style>