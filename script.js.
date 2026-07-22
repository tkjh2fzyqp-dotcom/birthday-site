/* ===========================
   LOADING SCREEN
=========================== */

window.addEventListener("load", () => {
    setTimeout(() => {
        const loader = document.getElementById("loading-screen");

        if (loader) {
            loader.style.opacity = "0";

            setTimeout(() => {
                loader.style.display = "none";
            }, 600);
        }
    }, 2500);
});


/* ===========================
   ELEMENTS
=========================== */

const startBtn = document.getElementById("begin");
const intro = document.getElementById("intro");
const reasons = document.getElementById("reasons");
const gallery = document.getElementById("gallery");
const letter = document.getElementById("letter");
const typing = document.getElementById("typing");


/* ===========================
   BEGIN BUTTON
=========================== */

if (startBtn) {

    startBtn.addEventListener("click", () => {

        [intro, reasons, gallery, letter].forEach(section => {

            if (section) {
                section.classList.remove("hidden");
            }

        });

        if (intro) {
            intro.scrollIntoView({
                behavior: "smooth"
            });
        }

        typeWriter();

    });

}


/* ===========================
   TYPEWRITER
=========================== */

const text = `I wanted to make you something that couldn't fit inside a message.

Not just another "Happy Birthday."

Something you'd remember.

Something you'd smile at.

Something that reminds you that somewhere in this world...

there's someone who's genuinely grateful that today exists.

Because today gave the world you.

Happy Birthday,
My Little Angel. 🤍

— Yours' Truly`;

function typeWriter() {

    if (!typing) return;

    typing.innerHTML = "";

    let i = 0;

    function write() {

        if (i < text.length) {

            typing.innerHTML += text.charAt(i);

            i++;

            setTimeout(write, 28);

        }

    }

    write();

}


/* ===========================
   REASON CARDS
=========================== */

document.querySelectorAll(".card").forEach(card => {

    card.addEventListener("click", () => {

        card.style.transform = "scale(1.05)";

        setTimeout(() => {

            card.style.transform = "scale(1)";

        }, 180);

    });

});


/* ===========================
   PHOTO POPUP
=========================== */

document.querySelectorAll(".photos img").forEach(img => {

    img.addEventListener("click", () => {

        const overlay = document.createElement("div");

        overlay.style.position = "fixed";
        overlay.style.inset = "0";
        overlay.style.background = "rgba(0,0,0,.9)";
        overlay.style.display = "flex";
        overlay.style.alignItems = "center";
        overlay.style.justifyContent = "center";
        overlay.style.zIndex = "9999";

        const image = document.createElement("img");

        image.src = img.src;
        image.style.maxWidth = "90%";
        image.style.maxHeight = "90%";
        image.style.borderRadius = "18px";

        overlay.appendChild(image);

        overlay.addEventListener("click", () => overlay.remove());

        document.body.appendChild(overlay);

    });

});


/* ===========================
   HUG COUPON
=========================== */

const hug = document.getElementById("hug");

if (hug) {

    hug.addEventListener("click", () => {

        alert(`🤍 Birthday Hug Coupon

Owner:
My Little Angel

Redeem:
Anytime.

Expiry:
Never.

Love,
Yours' Truly`);

    });

}


/* ===========================
   OPTIONAL CONFETTI
=========================== */

const canvas = document.getElementById("confetti");

if (canvas) {

    const ctx = canvas.getContext("2d");

    function resize() {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
    }

    resize();

    const pieces = [];

    for (let i = 0; i < 120; i++) {

        pieces.push({
            x: Math.random() * canvas.width,
            y: Math.random() * canvas.height,
            r: 2 + Math.random() * 5,
            s: 1 + Math.random() * 3,
            c: ["#fff", "#ffd6e8", "#ffb6d9", "#ffeef7"][Math.floor(Math.random() * 4)]
        });

    }

    function animate() {

        ctx.clearRect(0, 0, canvas.width, canvas.height);

        pieces.forEach(p => {

            ctx.beginPath();
            ctx.fillStyle = p.c;
            ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
            ctx.fill();

            p.y += p.s;

            if (p.y > canvas.height) {
                p.y = -10;
                p.x = Math.random() * canvas.width;
            }

        });

        requestAnimationFrame(animate);

    }

    animate();

    window.addEventListener("resize", resize);

}
