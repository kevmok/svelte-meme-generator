<script>
    import Header from './components/Header.svelte';
    import Meme from './components/Meme.svelte';
</script>

<main>
    <Header />
    <Meme />
</main>

<style>
    :global(body) {
        font-family: 'Karla', sans-serif;
        margin: 0;
        padding: 0;
    }

    /* :global(*) {
        box-sizing: border-box;
    } */
</style>
