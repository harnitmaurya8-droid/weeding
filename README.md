# weeding
happy marrige 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Wedding Celebration - Avneesh & Sakshi</title>

<style>
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    text-align: center;
    color: white;
    background: black;
    overflow-x: hidden;
}

.hero {
    padding: 50px 20px;
}

h1 {
    font-size: 50px;
    color: gold;
}

h2 {
    color: #ffcccc;
}

.section {
    margin: 40px;
}

.card {
    background: rgba(255,255,255,0.1);
    padding: 20px;
    border-radius: 15px;
    margin: 20px auto;
    width: 80%;
}

img {
    width: 250px;
    border-radius: 15px;
    margin: 10px;
}

.footer {
    margin-top: 50px;
    font-size: 18px;
}

/* Fireworks canvas */
canvas {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
}
</style>
</head>

<body>

<canvas id="fireworks"></canvas>

<div class="hero">
    <h1>💍 Avneesh ❤️ Sakshi 💍</h1>
    <h2>Wedding Date: 23/02/2026</h2>

    <p>
        A beautiful journey begins ❤️ <br>
        एक खूबसूरत सफर की शुरुआत ❤️
    </p>
</div>

<div class="section">
    <h2>👰 Bride & 🤵 Groom</h2>
    
    <!-- Replace these with your images -->
    <img src="your-image.jpg" alt="Couple">
</div>

<div class="section card">
    <h2>💖 Message</h2>
    <p>
        Wishing Avneesh & Sakshi a lifetime of love, happiness and success.<br>
        May your new journey be filled with joy.
    </p>

    <p>
        अवनीश और साक्षी को जीवन भर प्यार, खुशी और सफलता की शुभकामनाएं।<br>
        आपका नया जीवन खुशियों से भरा हो।
    </p>
</div>

<div class="section card">
    <h2>👨‍👩‍👧‍👦 Family Members</h2>
    <p>
        Groom Side:<br>
        Father: Mr. Rajesh Kumar<br>
        Mother: Mrs. Sunita Devi
    </p>

    <p>
        Bride Side:<br>
        Father: Mr. Suresh Sharma<br>
        Mother: Mrs. Meena Sharma
    </p>
</div>

<div class="section card">
    <h2>📍 Address</h2>
    <p>
        Prayagraj, Uttar Pradesh, India
    </p>
</div>

<div class="footer">
    🎉 Thank you for visiting and blessing the couple 🎉<br>
    धन्यवाद 🙏
</div>

<script>
// Fireworks Effect
const canvas = document.getElementById("fireworks");
const ctx = canvas.getContext("2d");

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

let particles = [];

function createFirework() {
    let x = Math.random() * canvas.width;
    let y = Math.random() * canvas.height / 2;

    for (let i = 0; i < 50; i++) {
        particles.push({
            x: x,
            y: y,
            dx: (Math.random() - 0.5) * 5,
            dy: (Math.random() - 0.5) * 5,
            life: 100
        });
    }
}

function update() {
    ctx.fillStyle = "rgba(0,0,0,0.2)";
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    particles.forEach((p, index) => {
        p.x += p.dx;
        p.y += p.dy;
        p.life--;

        ctx.fillStyle = "gold";
        ctx.fillRect(p.x, p.y, 3, 3);

        if (p.life <= 0) {
            particles.splice(index, 1);
        }
    });

    requestAnimationFrame(update);
}

setInterval(createFirework, 800);
update();
</script>

</body>
</html>
