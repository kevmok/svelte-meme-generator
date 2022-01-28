<script>
    import { onMount } from 'svelte';
    let meme = {
        topText: '',
        bottomText: '',
        randomImage: 'http://i.imgflip.com/1bij.jpg',
    };

    let allMemes = [];

    onMount(async () => {
        const res = await fetch('https://api.imgflip.com/get_memes');
        const data = await res.json();
        allMemes = data.data.memes;
    });

    const getMemeImage = () => {
        const randomNumber = Math.floor(Math.random() * allMemes.length);
        const url = allMemes[randomNumber].url;
        meme = {
            ...meme,
            randomImage: url,
        };
    };

    $: console.log(meme);
</script>

<main>
    <div class="form">
        <input type="text" placeholder="Top Text" bind:value={meme.topText} />
        <input
            type="text"
            placeholder="Bottom Text"
            bind:value={meme.bottomText}
        />
        <button on:click={getMemeImage}>Get a new meme image 🖼</button>
    </div>
    <div class="meme">
        <img src={meme.randomImage} value="test" alt="meme" />
        <h2 class="top">{meme.topText}</h2>
        <h2 class="bottom">{meme.bottomText}</h2>
    </div>
</main>

<style>
    main {
        padding: 36px;
        max-width: 800px;
        margin: 0 auto;
    }

    .form {
        display: grid;
        grid-template: 40px 40px /1fr 1fr;
        gap: 17px;
        margin-bottom: 17px;
    }

    input {
        font-family: 'Karla', sans-serif;
        border-radius: 5px;
        border: 1px solid #d5d4d8;
        text-indent: 5px;
    }

    button {
        grid-column: 1 / -1;
        font-family: 'Karla', sans-serif;
        border-radius: 5px;
        background: linear-gradient(90.41deg, #711f8d 1.14%, #a818da 100%);
        color: white;
        border: none;
        cursor: pointer;
        height: fit-content;
    }

    .meme {
        position: relative;
    }
    img {
        max-width: 100%;
        border-radius: 3px;
        margin: 0 auto;
        display: block;
    }

    h2 {
        position: absolute;
        width: 80%;
        text-align: center;
        left: 50%;
        transform: translateX(-50%);
        margin: 15px 0;
        padding: 0 5px;
        font-family: impact, sans-serif;
        font-size: 2em;
        text-transform: uppercase;
        color: white;
        letter-spacing: 1px;
        text-shadow: 2px 2px 0 #000, -2px -2px 0 #000, 2px -2px 0 #000,
            -2px 2px 0 #000, 0 2px 0 #000, 2px 0 0 #000, 0 -2px 0 #000,
            -2px 0 0 #000, 2px 2px 5px #000;
    }

    .bottom {
        bottom: 0;
    }

    .top {
        top: 0;
    }
</style>
