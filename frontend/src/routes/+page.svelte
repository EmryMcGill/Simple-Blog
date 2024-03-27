<script>
    import '../app.css'
    import Post from '../components/Post.svelte';
</script>

<div class="container">
    <div class="header">
        <h1>Emry Mcgill Blog</h1>
    </div>
    <div class='post-container'>
        <Post 
        title='Mt. Liverpool, New Zealand' 
        desc='A cool mountain trip in Aspiring National Park'
        />
    </div>
</div>

<style>
    .container {
        background-color: white;
        width: 80%;
        height: 100vh;
        padding: 1rem;
        margin-top: 1rem;
        box-shadow: -10px 5px 5px blue;
    }
    .header {
        border-bottom: 1px solid grey;
        padding-bottom: .5rem;
        margin-bottom: 1rem;
    }
</style>