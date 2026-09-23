<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>OCTANE | Premium Writing Experience</title>

<style>
/* =========================
   GLOBAL STYLES
========================= */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    background: #05070b;
    color: white;
    overflow-x: hidden;
}

/* Animated background */
body::before {
    content: "";
    position: fixed;
    width: 600px;
    height: 600px;
    background: radial-gradient(circle, rgba(255,70,0,.18), transparent 70%);
    top: -200px;
    left: -200px;
    z-index: -2;
    animation: backgroundMove 8s infinite alternate ease-in-out;
}

body::after {
    content: "";
    position: fixed;
    width: 500px;
    height: 500px;
    background: radial-gradient(circle, rgba(255,150,0,.12), transparent 70%);
    bottom: -200px;
    right: -150px;
    z-index: -2;
    animation: backgroundMove2 10s infinite alternate ease-in-out;
}

@keyframes backgroundMove {
    from {
        transform: translate(0,0);
    }
    to {
        transform: translate(250px,180px);
    }
}

@keyframes backgroundMove2 {
    from {
        transform: translate(0,0);
    }
    to {
        transform: translate(-200px,-150px);
    }
}

/* =========================
   NAVBAR
========================= */

nav {
    width: 100%;
    height: 75px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 7%;
    position: fixed;
    top: 0;
    z-index: 1000;
    background: rgba(5,7,11,.75);
    backdrop-filter: blur(15px);
    border-bottom: 1px solid rgba(255,255,255,.08);
}

.logo {
    font-size: 28px;
    font-weight: 900;
    letter-spacing: 5px;
    color: #fff;
}

.logo span {
    color: #ff5a00;
}

.nav-links {
    display: flex;
    gap: 35px;
    list-style: none;
}

.nav-links a {
    text-decoration: none;
    color: #bbb;
    font-size: 14px;
    transition: .3s;
}

.nav-links a:hover {
    color: #ff6500;
}

/* =========================
   HERO
========================= */

.hero {
    min-height: 100vh;
    padding: 120px 7% 50px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 50px;
}

.hero-content {
    width: 50%;
}

.tag {
    display: inline-block;
    padding: 8px 16px;
    border: 1px solid rgba(255,90,0,.5);
    border-radius: 30px;
    color: #ff6a00;
    font-size: 12px;
    letter-spacing: 2px;
    margin-bottom: 25px;
    background: rgba(255,90,0,.06);
}

.hero h1 {
    font-size: clamp(55px, 8vw, 105px);
    line-height: .9;
    font-weight: 900;
    letter-spacing: -5px;
}

.hero h1 span {
    color: #ff5a00;
    text-shadow: 0 0 30px rgba(255,80,0,.5);
}

.hero p {
    color: #999;
    max-width: 520px;
    line-height: 1.8;
    margin: 30px 0;
    font-size: 16px;
}

.buttons {
    display: flex;
    gap: 15px;
}

.btn {
    padding: 15px 28px;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    font-weight: bold;
    transition: .3s;
}

.primary {
    background: #ff5a00;
    color: white;
    box-shadow: 0 10px 30px rgba(255,70,0,.3);
}

.primary:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 40px rgba(255,70,0,.5);
}

.secondary {
    background: transparent;
    color: white;
    border: 1px solid #333;
}

.secondary:hover {
    border-color: #ff5a00;
    color: #ff5a00;
}

/* =========================
   3D PEN AREA
========================= */

.product-area {
    width: 50%;
    min-height: 520px;
    display: flex;
    align-items: center;
    justify-content: center;
    perspective: 1200px;
    position: relative;
}

/* Glow behind pen */

.product-area::before {
    content: "";
    position: absolute;
    width: 380px;
    height: 380px;
    border-radius: 50%;
    background: radial-gradient(
        circle,
        rgba(255,75,0,.3),
        transparent 65%
    );
    filter: blur(20px);
    animation: pulseGlow 3s infinite alternate;
}

@keyframes pulseGlow {
    from {
        transform: scale(.85);
        opacity: .5;
    }
    to {
        transform: scale(1.2);
        opacity: .9;
    }
}

/* =========================
   PEN
========================= */

.pen-wrapper {
    width: 500px;
    height: 170px;
    position: relative;
    transform-style: preserve-3d;
    transform: rotate(-18deg) rotateY(-15deg);
    animation: floatingPen 4s ease-in-out infinite;
    z-index: 2;
}

@keyframes floatingPen {
    0%,100% {
        transform: rotate(-18deg) rotateY(-15deg) translateY(0);
    }

    50% {
        transform: rotate(-13deg) rotateY(12deg) translateY(-18px);
    }
}

/* Main barrel */

.pen-body {
    position: absolute;
    left: 60px;
    top: 45px;
    width: 330px;
    height: 80px;
    border-radius: 45px;
    background:
        linear-gradient(
            90deg,
            #111,
            #333,
            #080808,
            #444,
            #101010
        );
    box-shadow:
        inset 0 8px 12px rgba(255,255,255,.18),
        inset 0 -10px 20px rgba(0,0,0,.8),
        0 25px 30px rgba(0,0,0,.6);
    transform-style: preserve-3d;
}

/* Orange highlight */

.pen-body::before {
    content: "";
    position: absolute;
    width: 230px;
    height: 5px;
    top: 14px;
    left: 40px;
    border-radius: 10px;
    background: #ff5a00;
    box-shadow: 0 0 15px #ff5a00;
}

/* Pen grip */

.grip {
    position: absolute;
    left: 20px;
    top: 50px;
    width: 65px;
    height: 70px;
    border-radius: 25px 5px 5px 25px;
    background:
        linear-gradient(
            90deg,
            #222,
            #555,
            #111
        );
    box-shadow:
        inset 0 8px 10px rgba(255,255,255,.1),
        0 15px 20px rgba(0,0,0,.7);
}

/* Grip rings */

.grip::after {
    content: "";
    position: absolute;
    inset: 10px 12px;
    border-left: 4px solid #ff5a00;
    border-right: 4px solid #ff5a00;
    opacity: .7;
}

/* Pen tip */

.pen-tip {
    position: absolute;
    right: -15px;
    top: 62px;
    width: 0;
    height: 0;
    border-top: 22px solid transparent;
    border-bottom: 22px solid transparent;
    border-left: 70px solid #aaa;
    filter: drop-shadow(10px 10px 10px rgba(0,0,0,.6));
}

.pen-tip::after {
    content: "";
    position: absolute;
    right: 0;
    top: -4px;
    width: 15px;
    height: 8px;
    background: #111;
}

/* Back cap */

.pen-cap {
    position: absolute;
    left: 355px;
    top: 38px;
    width: 90px;
    height: 95px;
    border-radius: 15px 40px 40px 15px;
    background:
        linear-gradient(
            90deg,
            #111,
            #444,
            #151515
        );
    box-shadow:
        inset 0 8px 15px rgba(255,255,255,.12),
        15px 20px 25px rgba(0,0,0,.6);
}

/* Clip */

.clip {
    position: absolute;
    top: 18px;
    left: 395px;
    width: 12px;
    height: 110px;
    border-radius: 10px;
    background: linear-gradient(#777,#ddd,#555);
    transform: rotate(7deg);
    box-shadow: 5px 5px 10px #000;
}

/* OCTANE branding */

.pen-name {
    position: absolute;
    left: 145px;
    top: 78px;
    font-size: 14px;
    letter-spacing: 5px;
    font-weight: bold;
    color: #ddd;
    transform: rotate(0deg);
}

/* =========================
   FEATURES
========================= */

.features {
    padding: 100px 7%;
    background: rgba(255,255,255,.015);
}

.section-title {
    text-align: center;
    margin-bottom: 60px;
}

.section-title span {
    color: #ff5a00;
}

.section-title h2 {
    font-size: 45px;
    margin-bottom: 15px;
}

.section-title p {
    color: #888;
}

.feature-grid {
    display: grid;
    grid-template-columns: repeat(4,1fr);
    gap: 20px;
}

.feature-card {
    padding: 35px 25px;
    border: 1px solid #222;
    border-radius: 18px;
    background: linear-gradient(
        145deg,
        rgba(255,255,255,.06),
        rgba(255,255,255,.015)
    );
    transition: .4s;
    transform-style: preserve-3d;
}

.feature-card:hover {
    transform: translateY(-12px) rotateX(4deg);
    border-color: #ff5a00;
    box-shadow: 0 20px 50px rgba(255,70,0,.15);
}

.icon {
    font-size: 35px;
    margin-bottom: 20px;
}

.feature-card h3 {
    margin-bottom: 12px;
}

.feature-card p {
    color: #888;
    line-height: 1.6;
    font-size: 14px;
}

/* =========================
   PRODUCT INFO
========================= */

.product-info {
    padding: 100px 7%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 60px;
}

.info-image {
    width: 50%;
    height: 400px;
    border-radius: 30px;
    background:
        radial-gradient(circle at center,
        rgba(255,70,0,.25),
        transparent 50%),
        #0b0d12;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid #222;
}

.info-image .mini-pen {
    width: 350px;
    height: 45px;
    border-radius: 30px;
    background: linear-gradient(
        90deg,
        #222,
        #777,
        #222
    );
    transform: rotate(-15deg);
    box-shadow: 0 30px 35px rgba(0,0,0,.8);
    position: relative;
}

.info-image .mini-pen::before {
    content: "OCTANE";
    position: absolute;
    left: 120px;
    top: 13px;
    font-size: 10px;
    letter-spacing: 4px;
    color: #ff5a00;
}

.info-content {
    width: 50%;
}

.info-content h2 {
    font-size: 48px;
    margin-bottom: 20px;
}

.info-content h2 span {
    color: #ff5a00;
}

.info-content p {
    color: #999;
    line-height: 1.8;
    margin-bottom: 25px;
}

.specs {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 15px;
}

.spec {
    padding: 15px;
    background: #0d1016;
    border-radius: 10px;
    border: 1px solid #222;
}

.spec small {
    color: #777;
}

.spec strong {
    display: block;
    margin-top: 5px;
}

/* =========================
   CTA
========================= */

.cta {
    margin: 50px 7% 100px;
    padding: 70px 30px;
    text-align: center;
    border-radius: 30px;
    background:
        linear-gradient(
            135deg,
            rgba(255,80,0,.18),
            rgba(255,255,255,.03)
        );
    border: 1px solid rgba(255,90,0,.25);
}

.cta h2 {
    font-size: 45px;
    margin-bottom: 15px;
}

.cta p {
    color: #999;
    margin-bottom: 30px;
}

/* =========================
   FOOTER
========================= */

footer {
    padding: 35px 7%;
    border-top: 1px solid #222;
    display: flex;
    justify-content: space-between;
    color: #666;
    font-size: 13px;
}

footer strong {
    color: #ff5a00;
}

/* =========================
   RESPONSIVE DESIGN
========================= */

@media(max-width: 900px) {

    .hero,
    .product-info {
        flex-direction: column;
        text-align: center;
    }

    .hero-content,
    .product-area,
    .info-image,
    .info-content {
        width: 100%;
    }

    .hero-content {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .feature-grid {
        grid-template-columns: repeat(2,1fr);
    }

    .nav-links {
        display: none;
    }

    .pen-wrapper {
        transform: scale(.8) rotate(-18deg);
    }

    .info-image {
        height: 300px;
    }
}

@media(max-width: 600px) {

    .hero h1 {
        font-size: 60px;
    }

    .feature-grid {
        grid-template-columns: 1fr;
    }

    .specs {
        grid-template-columns: 1fr;
    }

    .pen-wrapper {
        transform: scale(.6) rotate(-18deg);
    }

    .product-area {
        min-height: 350px;
    }

    .buttons {
        flex-direction: column;
        width: 100%;
    }

    .btn {
        width: 100%;
    }

    footer {
        flex-direction: column;
        gap: 10px;
        text-align: center;
    }
}
</style>
</head>

<body>

<!-- =========================
     NAVIGATION
========================= -->

<nav>

    <div class="logo">
        OCT<span>ANE</span>
    </div>

    <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#features">Features</a></li>
        <li><a href="#technology">Technology</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>

</nav>


<!-- =========================
     HERO SECTION
========================= -->

<section class="hero" id="home">

    <div class="hero-content">

        <div class="tag">
            NEXT-GENERATION WRITING
        </div>

        <h1>
            WRITE<br>
            <span>FASTER.</span>
        </h1>

        <p>
            Meet OCTANE — a premium performance pen engineered
            for people who demand precision, comfort and style
            from every line they write.
        </p>

        <div class="buttons">

            <button class="btn primary"
                    onclick="exploreProduct()">
                Explore OCTANE
            </button>

            <button class="btn secondary"
                    onclick="showMessage()">
                Discover More
            </button>

        </div>

    </div>


    <!-- 3D PRODUCT -->

    <div class="product-area">

        <div class="pen-wrapper" id="pen">

            <div class="grip"></div>

            <div class="pen-body"></div>

            <div class="pen-cap"></div>

            <div class="clip"></div>

            <div class="pen-name">
                OCTANE
            </div>

            <div class="pen-tip"></div>

        </div>

    </div>

</section>


<!-- =========================
     FEATURES
========================= -->

<section class="features" id="features">

    <div class="section-title">

        <h2>
            Built for <span>Performance</span>
        </h2>

        <p>
            Every detail of OCTANE is designed around your writing experience.
        </p>

    </div>


    <div class="feature-grid">

        <div class="feature-card">

            <div class="icon">⚡</div>

            <h3>Ultra Smooth</h3>

            <p>
                Experience effortless writing with a precision-engineered
                writing tip designed for smooth ink flow.
            </p>

        </div>


        <div class="feature-card">

            <div class="icon">🎯</div>

            <h3>Precision Tip</h3>

            <p>
                A carefully balanced tip delivers accurate and controlled
                strokes for everyday writing.
            </p>

        </div>


        <div class="feature-card">

            <div class="icon">🛡️</div>

            <h3>Built to Last</h3>

            <p>
                A durable premium body provides strength while maintaining
                a sophisticated appearance.
            </p>

        </div>


        <div class="feature-card">

            <div class="icon">✦</div>

            <h3>Premium Design</h3>

            <p>
                A modern aerodynamic design combines performance,
                comfort and professional aesthetics.
            </p>

        </div>

    </div>

</section>


<!-- =========================
     TECHNOLOGY
========================= -->

<section class="product-info" id="technology">

    <div class="info-image">

        <div class="mini-pen"></div>

    </div>


    <div class="info-content">

        <h2>
            Engineered for <span>Control.</span>
        </h2>

        <p>
            OCTANE combines a precision writing system with a balanced
            body design. The result is a pen that feels stable in your
            hand and responds naturally to every movement.
        </p>

        <div class="specs">

            <div class="spec">
                <small>BODY</small>
                <strong>Premium Alloy</strong>
            </div>

            <div class="spec">
                <small>TIP</small>
                <strong>Precision Point</strong>
            </div>

            <div class="spec">
                <small>GRIP</small>
                <strong>Ergonomic</strong>
            </div>

            <div class="spec">
                <small>DESIGN</small>
                <strong>Aerodynamic</strong>
            </div>

        </div>

    </div>

</section>


<!-- =========================
     CTA
========================= -->

<section class="cta" id="contact">

    <h2>
        Ready to write differently?
    </h2>

    <p>
        Experience the next generation of everyday writing.
    </p>

    <button class="btn primary"
            onclick="launchExperience()">
        Experience OCTANE
    </button>

</section>


<!-- =========================
     FOOTER
========================= -->

<footer>

    <div>
        © 2026 <strong>OCTANE</strong>
    </div>

    <div>
        Precision • Performance • Design
    </div>

</footer>


<!-- =========================
     INTERNAL JAVASCRIPT
========================= -->

<script>

/* =================================
   3D MOUSE MOVEMENT
================================= */

const pen = document.getElementById("pen");

document.addEventListener("mousemove", function(event) {

    const x = (window.innerWidth / 2 - event.clientX) / 40;
    const y = (window.innerHeight / 2 - event.clientY) / 40;

    pen.style.transform =
        `rotate(-18deg) rotateY(${x}deg) rotateX(${y}deg)`;

});


/* =================================
   RESET 3D EFFECT
================================= */

document.addEventListener("mouseleave", function() {

    pen.style.transform =
        "rotate(-18deg) rotateY(-15deg)";

});


/* =================================
   EXPLORE BUTTON
================================= */

function exploreProduct() {

    document.getElementById("features")
        .scrollIntoView({
            behavior: "smooth"
        });

}


/* =================================
   DISCOVER MORE
================================= */

function showMessage() {

    alert(
        "OCTANE combines precision engineering, premium design and an ultra-smooth writing experience."
    );

}


/* =================================
   CTA BUTTON
================================= */

function launchExperience() {

    const button = event.target;

    button.innerHTML = "OCTANE ACTIVATED ✓";

    button.style.background = "#222";

    setTimeout(function() {

        button.innerHTML = "Experience OCTANE";

        button.style.background = "#ff5a00";

    }, 2500);

}


/* =================================
   CARD TILT EFFECT
================================= */

const cards = document.querySelectorAll(".feature-card");

cards.forEach(card => {

    card.addEventListener("mousemove", function(e) {

        const rect = card.getBoundingClientRect();

        const x = e.clientX - rect.left;
        const y = e.clientY - rect.top;

        const centerX = rect.width / 2;
        const centerY = rect.height / 2;

        const rotateX =
            ((y - centerY) / centerY) * -5;

        const rotateY =
            ((x - centerX) / centerX) * 5;

        card.style.transform =
            `perspective(700px)
             rotateX(${rotateX}deg)
             rotateY(${rotateY}deg)
             translateY(-8px)`;

    });


    card.addEventListener("mouseleave", function() {

        card.style.transform =
            "perspective(700px) rotateX(0) rotateY(0) translateY(0)";

    });

});


/* =================================
   SCROLL REVEAL
================================= */

const observer = new IntersectionObserver(

    entries => {

        entries.forEach(entry => {

            if(entry.isIntersecting) {

                entry.target.style.opacity = "1";

                entry.target.style.transform =
                    "translateY(0)";

            }

        });

    },

    {
        threshold: 0.15
    }

);


document.querySelectorAll(
    ".feature-card, .info-content, .info-image"
).forEach(element => {

    element.style.opacity = "0";

    element.style.transform = "translateY(40px)";

    element.style.transition =
        "opacity .8s ease, transform .8s ease";

    observer.observe(element);

});


/* =================================
   CONSOLE MESSAGE
================================= */

console.log(
    "OCTANE — Precision. Performance. Design."
);

</script>

</body>
</html>
