<script>
    let logo = '../assets/troll-face.png';
</script>

<header>
    <img src={logo} alt="" />
    <h2>Meme Generator</h2>
    <h4>Svelte Meme Generator</h4>
</header>

<style>
    header {
        display: flex;
        align-items: center;
        height: 65px;
        background: linear-gradient(90deg, #672280 1.18%, #a626d3 100%);
        color: white;
        padding: 20px;
    }

    img {
        height: 100%;
        margin-right: 6px;
    }

    h2 {
        font-size: 1.25rem;
        margin-right: auto;
    }

    h4 {
        font-size: 0.9rem;
        font-weight: 700;
    }
</style>
