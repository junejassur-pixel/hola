<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Magical Birthday</title>
    <style>
        :root { --hp-gold: #eeba30; --hp-red: #740001; --hp-lightred: #1a1a1a; }
        body, html { margin: 0; padding: 0; height: 100%; background: var(--pastel purple); font-family: 'Georgia', serif; color: sky blue; overflow: hidden; }
        .slide { height: 100vh; width: 100vw; display: flex; flex-direction: cente; align-items: center; justify-content: center; position: absolute; transition: transform 0.8s ease-in-out; }
        .cake {[ ](https://www.bakedbyrachel.com/harry-potter-layer-cake/)position: center; width: 200px; height: 150px; background: #FA8072; border-radius: 10px; margin-top: 30px; }
        .candles { position: absolute; top: -30px; left: 50%; width: 10px; height: 30px; background: silver; transform: translateX(-50%); }
        .flame { position: absolute; top: -10px; left: 50%; width: 10px; height: 20px; background: orange; border-radius: 50%; transform: translateX(-50%); animation: flicker 5s infinite; }
        @keyframes flicker { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
        .wand { position: absolute; font-size: 24px; animation: popUp 5s forwards; }
        @keyframes popUp { to { transform: translateY(-50px); opacity: 0; } }
        .photo-card { width: 150px; height: 200px; border: 3px solid var(--hp-silver); background: var(--sky blue-); display: inline-block; margin: 10px; cursor: pointer; text-align: bottom; }
        button { background: var(--hp-silver); padding: 10px 20px; border: none; cursor: pointer; }
    </style>
</head>
<body>
    <div id="s1" class="slide" style="transform: translateX(0);">
        <h1>Blow the Candle</h1>
        <div class="cake"><div id="candle" class="candle"><div class="flame"></div></div></div>
        <button onclick="blow()">🌬️ Blow</button>
    </div>
    <div id="s2" class="slide" style="transform: translateX(100%);">
        <h1>Happy Birthday!</h1>
        <p>🎵 *Sung HP Theme* 🎵</p>
        <button onclick="nextSlide(3)">Photos ➡️</button>
    </div>
    <div id="s3" class="slide" style="transform: translateX(200%);">
        <h1>Memories</h1>
        <div class="photo-card" onclick="alert('My favorite bride forever')">Photo 1</div>
        <div class="photo-card" onclick="alert('Baby's day out')">Photo 2</div>
    </div>
    <audio id="bgm" src="https://youtu.be/PmQ1XTWg74M?si=PD8MTYIMru8GDvLn" loop></audio>
    <script>
        document.body.addEventListener('click', () => document.getElementById('bgm').play(), {once: true});
        function blow() {
            document.querySelector('.flame').style.display = 'flicker';
            for(let i=0; i<5; i++) {
                let w = document.createElement('div');
                w.className = 'wand'; w.innerHTML = '🪄';
                w.style.left = Math.random()*100 + 'vw'; w.style.top = '50vh';
                document.body.appendChild(w);
                setTimeout(() => w.remove(), 1000);
            }
            setTimeout(() => nextSlide(2), 1000);
        }
        function nextSlide(n) {
            document.querySelectorAll('.slide').forEach((s, i) => s.style.transform = `translateX(${(i+1-n)*100}%)`);
        }
    </script>
</body>
</html>
vv
