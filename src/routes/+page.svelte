<script>
    import { onMount } from "svelte";

    let phrases = [
    "Believe you can and you're halfway there.",
    "The future belongs to those who believe in the beauty of their dreams.",
    "Success is not final, failure is not fatal: it is the courage to continue that counts.",
    "The only way to do great work is to love what you do.",
    "Strive not to be a success, but rather to be of value.",
    "Don't watch the clock; do what it does. Keep going.",
    "Your limitation—it's only your imagination.",
    "Push yourself, because no one else is going to do it for you.",
    "Great things never come from comfort zones.",
    "Dream it. Wish it. Do it.",
    "Success doesn’t just find you. You have to go out and get it.",
    "The harder you work for something, the greater you’ll feel when you achieve it.",
    "Dream bigger. Do bigger.",
    "Don’t stop when you’re tired. Stop when you’re done.",
    "Wake up with determination. Go to bed with satisfaction.",
    "Do something today that your future self will thank you for.",
    "Little things make big days.",
    "It’s going to be hard, but hard does not mean impossible.",
    "Don’t wait for opportunity. Create it.",
    "Sometimes we’re tested not to show our weaknesses, but to discover our strengths.",
    "The key to success is to focus on goals, not obstacles.",
    "Don’t be afraid to give up the good to go for the great.",
    "It always seems impossible until it’s done.",
    "Success is the sum of small efforts, repeated day-in and day-out.",
    "The way to get started is to quit talking and begin doing.",
    "You don’t have to be great to start, but you have to start to be great.",
    "Act as if what you do makes a difference. It does.",
    "The only limit to our realization of tomorrow is our doubts of today.",
    "Believe in yourself and all that you are. Know that there is something inside you that is greater than any obstacle.",
    "Success is not how high you have climbed, but how you make a positive difference to the world.",
    "Your time is limited, don’t waste it living someone else’s life.",
    "You are never too old to set another goal or to dream a new dream.",
    "The only way to achieve the impossible is to believe it is possible.",
    "Everything you’ve ever wanted is on the other side of fear.",
    "The best way to predict the future is to create it.",
    "The only person you are destined to become is the person you decide to be.",
    "It does not matter how slowly you go as long as you do not stop.",
    "Hardships often prepare ordinary people for an extraordinary destiny.",
    "The secret of getting ahead is getting started.",
    "Start where you are. Use what you have. Do what you can.",
    "What we achieve inwardly will change outer reality."
];


    let currentPhrase = "";

    function getRandomPhrase() {
        const randomIndex = Math.floor(Math.random() * phrases.length);
        currentPhrase = phrases[randomIndex];
    }

    onMount(getRandomPhrase);
</script>

<main>
    <div class="glass-container">
        <h1>Daily Motivation</h1>
        <p>{currentPhrase}</p>
        <div class="buttons">
            <button on:click={getRandomPhrase}>New Quote</button>
        </div>
    </div>
    <iframe style="border-radius:12px" src="https://open.spotify.com/embed/playlist/37i9dQZF1DX6aTaZa0K6VA?utm_source=generator" width="100%" height="152" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
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

    iframe{
        position: fixed;
        width: 39em;
        bottom: 5px;
    }
    .TrackListWidget_trackListGridContainer__GZGxh{
        background-color: transparent;
    }


    main {
        display: flex;
        text-align: center;
        align-items: center;
        flex-direction: column;
        justify-content: center;
        height: 100vh;
        width: 100vw;
        position: relative;
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
        width: 100%;
        max-width: 450px;
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
