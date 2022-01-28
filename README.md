# Meme Generator Built with Svelte

Meme generator svelte app that calls imgflip's API and generates different images at the user's request.

## Overview

### The Goal

User should be able to:

-   [x] Customize the meme's text
-   [x] Generate a random image for the meme
-   [x] Choose meme image from a dropdown menu
-   [ ] Download the image with a button

### Demo

[Website Demo](https://svelte-meme-generator.vercel.app/)

## Screenshot

![App Screenshot](https://i.imgur.com/JTk24aD.jpg)

## My process

### Built with

-   Svelte
-   HTML markup
-   CSS
-   Javascript
-   JSX

### What I learned

-   How to work with an API using onMount
-   Binding values to inputs to change an object's property
-   CSS positioning
-   Reactivity declarations for debugging

```jsx
<script>
// You can use the $ to check the state of the object meme changing

    import { onMount } from 'svelte';
    let meme = {
        topText: '',
        bottomText: '',
        randomImage: 'http://i.imgflip.com/1bij.jpg',
    };

// Every time the user types in the input box, the console will log the newly updated object
$: console.log(meme);
</script>

div class="form">
        <input type="text" placeholder="Top Text" bind:value={meme.topText} />
        <input
            type="text"
            placeholder="Bottom Text"
            bind:value={meme.bottomText}
        />
        <button on:click={getMemeImage}>Get a new meme image 🖼</button>
    </div>
```

## Installation

Clone this repository and install the dependencies...

```bash
  git clone https://github.com/kevmok/svelte-meme-generator.git my-app
  cd my-app
  npm install
```

```bash
npm run dev
```

## Author

-   Website - [kevinmok.com](https://kevinmok.com)
-   GitHub - [@kevmok](https://www.github.com/Kevmok)
-   Twitter - [@hustlerBoxer](https://twitter.com/hustlerBoxer)

## Acknowledgements

-   [Scrimba](https://scrimba.com) - For the guidance and incredible courses
-   [imgflip](https://imgflip.com/) - For their awesome meme API
-   [Cl0udi](https://github.com/Cl0udi) - Dropdown menu idea
