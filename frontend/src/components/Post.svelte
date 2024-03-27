<script>
    export let title = ''
    export let desc = ''
    export let post = null

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
        <p>{desc}</p>
        <img alt='img' />
    <div class='post'>
        {post}
    </div>
</div>

<style>
    .container {
        padding: .5rem;
        pointer-events: none;
    }
    .container:hover{
        background-color: rgb(194, 194, 194);
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
    .title {
        margin-bottom: .5rem;
    }
    button:hover .title {
        cursor: pointer;
        text-decoration: underline;
    }
    .post {
        height: 0;
        overflow: hidden;
    }

    .check:checked + .container .post {
        height: fit-content;
    }
</style>