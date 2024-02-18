<script lang='ts'>
    let count = 0;

    function updateCount() {
        count += 1;
    }
</script>

<p>Clicked {count} {count === 1 ? "time" : "times"}</p>
<button on:click={updateCount}>Increment</button>

<style>
    p {
        color: teal;
    }
</style>