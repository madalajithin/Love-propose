# Love-propose

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Love Proposal</title><style>
body {
    margin: 0;
    padding: 0;
    font-family: 'Courier New', monospace;
    background: black;
    color: #ff4d6d;
    text-align: center;
    overflow: hidden;
}

canvas {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
}

h1 {
    margin-top: 60px;
    font-size: 2.8rem;
    text-shadow: 0 0 15px #ff4d6d;
}

.typing {
    font-size: 1.6rem;
    margin-top: 25px;
    border-right: 3px solid #ff4d6d;
    display: inline-block;
    white-space: nowrap;
    overflow: hidden;
    animation: blink 0.7s infinite;
}

@keyframes blink {
    0% { border-color: transparent; }
    50% { border-color: #ff4d6d; }
    100% { border-color: transparent; }
}

.heart {
    font-size: 100px;
    color: red;
    animation: beat 0.8s infinite;
    margin-top: 40px;
    text-shadow: 0 0 25px red;
}

@keyframes beat {
    0% { transform: scale(1); }
    25% { transform: scale(1.25); }
    50% { transform: scale(1); }
    75% { transform: scale(1.25); }
    100% { transform: scale(1); }
}

.btn {
    margin-top: 50px;
    padding: 15px 35px;
    font-size: 1.2rem;
    border: none;
    border-radius: 50px;
    background: #ff4d6d;
    color: white;
    cursor: pointer;
    box-shadow: 0 0 20px #ff4d6d;
    transition: 0.3s;
}

.btn:hover {
    transform: scale(1.1);
    box-shadow: 0 0 30px #ff1e4d;
}

#message {
    margin-top: 30px;
    font-size: 1.8rem;
    color: #fff;
    text-shadow: 0 0 10px pink;
}

.hidden {
    display: none;
}
</style></head><body><canvas id="matrix"></canvas>

<h1>JITHIN CHOWDARY ❤️ MISS REDDY</h1><div class="typing" id="typing"></div><div class="heart">❤️</div><button class="btn" onclick="showMessage()">💌 Click for Surprise</button>

<h2 id="message" class="hidden">💖 Will You Be Mine Forever MISS REDDY? 💖</h2><audio autoplay loop>
    <source src="anitha-o-anitha.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
</audio><script>
// Typing Effect
const text = "I Love You MISS REDDY ❤️";
let i = 0;
function typeEffect() {
    if (i < text.length) {
        document.getElementById("typing").innerHTML += text.charAt(i);
        i++;
        setTimeout(typeEffect, 70);
    }
}
typeEffect();

// Button Message
function showMessage() {
    document.getElementById("message").classList.remove("hidden");
}

// Matrix Rain Effect
const canvas = document.getElementById("matrix");
const ctx = canvas.getContext("2d");

canvas.height = window.innerHeight;
canvas.width = window.innerWidth;

const letters = "01LOVEYOU❤️";
const fontSize = 16;
const columns = canvas.width / fontSize;

const drops = [];
for (let x = 0; x < columns; x++) {
    drops[x] = 1;
}

function draw() {
    ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = "#0F0";
    ctx.font = fontSize + "px monospace";

    for (let i = 0; i < drops.length; i++) {
        const text = letters[Math.floor(Math.random() * letters.length)];
        ctx.fillText(text, i * fontSize, drops[i] * fontSize);

        if (drops[i] * fontSize > canvas.height && Math.random() > 0.975)
            drops[i] = 0;

        drops[i]++;
    }
}

setInterval(draw, 33);
</script></body>
</html>
