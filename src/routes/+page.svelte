<script>
    import { onMount } from "svelte";

    let phrases = [
        "Believe you can and you're halfway there.",
        "The future belongs to those who believe in the beauty of their dreams.",
        "Success is not final, failure is not fatal: it is the courage to continue that counts.",
        "The only way to do great work is to love what you do.",
        "Strive not to be a success, but rather to be of value.",
        "There’s something poetic about a 39 year old man winning new artist of the year. I don’t know where you’re at in your life, or what you’re going through, But I want to tell you to keep goin, baby! I want to tell you that success is in the other side! I want to tell you that everything’s gunna be okay! That the windshield is bigger than the rearview for a reason! And what’s in front of you is much more important than what’s behind you!",
    ];

    let currentPhrase = "";
    let audio;

    function getRandomPhrase() {
        const randomIndex = Math.floor(Math.random() * phrases.length);
        currentPhrase = phrases[randomIndex];
    }

    onMount(() => {
        getRandomPhrase();
        audio = new Audio("https://www.youtube.com/watch?v=9Ws_6U-Jl2g");
    });

    function toggleAudio() {
        if (audio.paused) {
            audio.play();
        } else {
            audio.pause();
        }
    }
</script>

<main>
    <div class="glass-container">
        <h1>Daily Motivation</h1>
        <p>{currentPhrase}</p>
        <div class="buttons">
            <button on:click={getRandomPhrase}>New Quote</button>
            <button on:click={toggleAudio}>
                {#if audio && !audio.paused}
                    Pause Music
                {:else}
                    Play Music
                {/if}
            </button>
        </div>
    </div>
</main>

<style>
    :global(body) {
        margin: 0;
        padding: 0;
        font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
            Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
            background: linear-gradient(120deg, #ffffff 0%, #72003e 100%);
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    main {
        text-align: center;
    }

    .glass-container {
        background: rgba(255, 255, 255, 0.25);
        backdrop-filter: blur(10px);
        border-radius: 20px;
        padding: 40px;
        box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
        border: 1px solid rgba(255, 255, 255, 0.18);
        max-width: 80%;
        margin: 0 auto;
    }

    h1 {
        color: #333;
        font-size: 2.5rem;
        margin-bottom: 20px;
    }

    p {
        color: #444;
        font-size: 1.5rem;
        line-height: 1.6;
        margin-bottom: 30px;
    }

    .buttons {
        display: flex;
        justify-content: center;
        gap: 20px;
    }

    button {
        background-color: rgba(255, 255, 255, 0.3);
        border: none;
        padding: 10px 20px;
        font-size: 1rem;
        color: #333;
        border-radius: 30px;
        cursor: pointer;
        transition: all 0.3s ease;
    }

    button:hover {
        background-color: rgba(255, 255, 255, 0.5);
    }
</style>
