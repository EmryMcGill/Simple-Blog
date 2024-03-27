<script>
    export let title = ''
    export let desc = ''
    export let date = ''
    export let post = null
    import bird from '$lib/assets/liverpool/bird.jpg'

    let checked = false

    const handleCheck = () => {
        checked = !checked
    }
</script>

<input class='check' type='checkbox' checked={checked} />
<div class='container'>
    <button on:click={handleCheck}>
        <h2 class='title'>{title}</h2>
    </button>
    <p class="date">{date}</p>
    {#if !checked}
    <p>{desc}</p>
    <img class='cover-image' alt='img' src={bird} />
    {:else}
    <div class='post'>
        <svelte:component this={post} />
    </div>
    {/if}
</div>

<style>
    .container {
        padding: .5rem;
    }
    .container:hover{
        background-color: rgb(194, 194, 194);
    }
    .check:checked + .container:hover{
        background: none;
    }
    .check {
        display: none;
    }
    button {
        border: none;
        background: none;
        font-family:'Times New Roman', Times, serif;
        display: flex;
        flex-direction: column;
        align-items: start;
        padding: 0;
        margin: 0;
        pointer-events: auto;
    }
    .date {
        font-style: italic;
        font-weight: bold;
        color: red;
    }
    button:hover .title {
        cursor: pointer;
        text-decoration: underline;
    }
    .post {
        height: 0;
        overflow: hidden;
    }
    .cover-image {
        max-width: 40vw;
        max-height: 40vh;
    }
    .check:checked + .container .post {
        height: fit-content;
    }
</style>