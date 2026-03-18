# love 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Love Proposal</title>

<style>
body {
    margin: 0;
    padding: 0;
    font-family: 'Courier New', monospace;
    background: black;
    color: #ff4d6d;
    text-align: center;
    overflow: hidden;
}

/* Canvas */
canvas {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
}

/* Heading */
h1 {
    margin-top: 60px;
    font-size: 2.8rem;
    text-shadow: 0 0 20px #ff4d6d;
}

/* Typing */
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
    50% { border-color: transparent; }
}

/* Heart */
.heart {
    font-size: 110px;
    color: red;
    animation: beat 0.8s infinite, glow 1.5s infinite alternate;
    margin-top: 40px;
}

@keyframes beat {
    0%,100% { transform: scale(1); }
    50% { transform: scale(1.3); }
}

@keyframes glow {
    from { text-shadow: 0 0 10px red; }
    to { text-shadow: 0 0 35px #ff1e4d; }
}

/* Button */
.btn {
    margin-top: 50px;
    padding: 15px 35px;
    font-size: 1.2rem;
    border: none;
    border-radius: 50px;
    background: linear-gradient(45deg, #ff4d6d, #ff1e4d);
    color: white;
    cursor: pointer;
    box-shadow: 0 0 25px #ff4d6d;
    transition: 0.3s;
}

.btn:hover {
    transform: scale(1.15);
    box-shadow: 0 0 40px #ff1e4d;
}

/* Message */
.message {
    margin-top: 30px;
    font-size: 1.8rem;
    color: #fff;
    text-shadow: 0 0 15px pink;
    opacity: 0;
    transition: 1s;
}

.show {
    opacity: 1;
}

</style>
</head>

<body>

<canvas id="matrix"></canvas>

<h1>JITHIN CHOWDARY ❤️ MISS REDDY</h1>

<div class="typing" id="typing"></div>

<div class="heart">❤️</div>

<button class="btn" onclick="showMessage()">💌 Click for Surprise</button>

<h2 id="message1" class="message">
💖 Will You Be Mine Forever MISS REDDY? 💖
</h2>

<h2 id="message2" class="message">
💖 I LOVE YOU FOREVER AND EVER 💖
</h2>

<audio id="music" loop>
    <source src="anitha-o-anitha.mp3" type="audio/mpeg">
</audio>

<script>

// Play music once user clicks
document.body.addEventListener("click", () => {
    document.getElementById("music").play();
}, { once: true });

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

// Show Messages One by One
function showMessage() {
    const msg1 = document.getElementById("message1");
    const msg2 = document.getElementById("message2");

    msg1.classList.add("show");

    setTimeout(() => {
        msg2.classList.add("show");
    }, 2000);
}

// Matrix Effect (Romantic Red)
const canvas = document.getElementById("matrix");
const ctx = canvas.getContext("2d");

canvas.height = window.innerHeight;
canvas.width = window.innerWidth;

const letters = "LOVE❤️";
const fontSize = 16;
const columns = canvas.width / fontSize;

const drops = Array(Math.floor(columns)).fill(1);

function draw() {
    ctx.fillStyle = "rgba(0, 0, 0, 0.07)";
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = "#ff4d6d";
    ctx.font = fontSize + "px monospace";

    for (let i = 0; i < drops.length; i++) {
        const char = letters[Math.floor(Math.random() * letters.length)];
        ctx.fillText(char, i * fontSize, drops[i] * fontSize);

        if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
            drops[i] = 0;
        }

        drops[i]++;
    }
}

setInterval(draw, 33);

// Resize fix
window.addEventListener("resize", () => {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
});

</script>

</body>
</html>
