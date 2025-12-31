# 👋 Welcome to the crazy world of mvrck-dev

<script>
  // Lightweight seed for some tiny dynamic vibes without heavy libs
  document.addEventListener('DOMContentLoaded', () => {
    const wink = document.querySelector('#wink');
    const toggle = document.querySelector('#sound-toggle');
    if (wink && toggle) {
      toggle.addEventListener('click', () => {
        wink.classList.toggle('spin');
      });
    }
  });
</script>

<style>
  :root{
    --bg: #0b1020;
    --card: #141a2b;
    --accent: #7cffcb;
    --text: #e9e9f3;
    --muted: #a2a2b5;
  }
  body { background: var(--bg); color: var(--text); margin: 0; font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto; }
  .container { max-width: 980px; margin: 0 auto; padding: 20px; }
  /* Fancy header badge */
  .header {
    display: flex; align-items: center; justify-content: space-between;
    padding: 16px; border-radius: 16px; background: linear-gradient(135deg, #1b1f2a 0%, #0e1220 100%);
    border: 1px solid rgba(124,255,203,.25);
    position: relative; overflow: hidden;
  }
  .header h1 { font-size: 28px; margin: 0; letter-spacing: .5px; }
  .pulse {
    width: 12px; height: 12px; border-radius: 50%; background: #7cffcb;
    position: absolute; right: -6px; top: -6px; animation: ping 2s infinite;
  }
  @keyframes ping { 0% { transform: scale(0.7); opacity: .9 } 70% { transform: scale(1.6); opacity: 0 } 100% { transform: scale(1.6); opacity: 0 } }

  .card {
    background: rgba(20,26,43,.9);
    border: 1px solid rgba(124,255,203,.25);
    border-radius: 16px; padding: 16px; margin-top: 14px;
    box-shadow: 0 10px 25px rgba(0,0,0,.25);
  }

  .grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 16px;
  }
  @media (max-width: 700px) {
    .grid { grid-template-columns: 1fr; }
  }

  .stat {
    display: flex; align-items: center; gap: 12px;
    padding: 12px; border-radius: 12px; background: rgba(0,0,0,.15);
  }
  .stat .num { font-size: 22px; font-weight: 700; }
  .stat .label { color: var(--muted); }

  /* Interactive fun bits */
  .button {
    display: inline-flex; align-items: center; gap: 8px;
    background: linear-gradient(135deg, #6c3cff, #00e6d6);
    color: white; border: none; padding: 10px 14px; border-radius: 999px;
    cursor: pointer; font-weight: 700; text-decoration: none;
  }
  .button:hover { transform: translateY(-1px); }

  #wink { display: inline-block; transition: transform 0.4s ease; }
  #wink.spin { transform: rotate(360deg); }

  /* CSS-only mini-game panel */
  .dice {
    display: inline-block; width: 40px; height: 40px; border-radius: 8px;
    background: #1f2a44; border: 1px solid #2b3a71;
    display: grid; place-items: center; font-weight: 800;
    cursor: pointer; user-select: none;
    transition: transform 0.2s;
  }
  .dice:active { transform: scale(0.92); }

  /* Simple animated gradient strip */
  .gradient-strip {
    height: 6px; border-radius: 6px; margin-top: 8px;
    background: linear-gradient(90deg, #ff6b6b, #ffd93d, #6bffb3, #7cffcb);
    background-size: 400% 100%; animation: gradient 8s linear infinite;
  }
  @keyframes gradient { 0%{ background-position: 0% 0 } 100%{ background-position: 100% 0 } }

  /* GitHub stats placeholders (no external calls beyond readme render) */
  .stats-embeds {
    display: grid; grid-template-columns: 1fr 1fr; gap: 12px;
  }
  .embed { padding: 12px; border-radius: 12px; background: rgba(255,255,255,.04); border: 1px solid rgba(124,255,203,.25); }
  a { color: #7cffcb; text-decoration: none; }
  a:hover { text-decoration: underline; }
</style>

<div class="container">
  <div class="header card" role="banner" aria-label="Intro banner">
    <div style="display:flex; align-items: center; gap: 12px;">
      <span aria-hidden="true" style="font-size: 18px;">✨</span>
      <div>
        <h1>mvrck-dev • The Fun Zone</h1>
        <div style="color: var(--muted); font-size: 12px;">
          Interactive, silly, and a little chaotic. Welcome to my profile!
        </div>
      </div>
    </div>
    <span class="pulse" aria-hidden="true"></span>
  </div>

  <div class="gradient-strip" aria-hidden="true"></div>

  <div class="grid" style="margin-top:14px;">
    <section class="card" aria-label="Intro">
      <h3 style="margin:0 0 8px 0;">Who am I?</h3>
      <p>Front-end tinkerer, maker of tiny tools, and full-time meme enthusiast. I code in React, vanilla JS, and a lot of enthusiasm. This README is my playground—expect motion, surprises, and occasional chaos.</p>
      <p style="margin-top:6px;">
        Quick actions: 
        <button id="sound-toggle" class="button" aria-label="Toggle spin on wink">
          <span id="wink" style="display:inline-block;">😉</span> Spin the orb
        </button>
      </p>
    </section>

    <section class="card" aria-label="Stats">
      <h3 style="margin:0 0 8px 0;">Stats & Skills</h3>
      <div class="grid" style="grid-template-columns: 1fr 1fr;">
        <div class="stat" aria-label="Projects">
          <span style="font-size:22px; font-weight:700;">12</span>
          <span class="label">Projects</span>
        </div>
        <div class="stat" aria-label="Contributions">
          <span style="font-size:22px; font-weight:700;">3y</span>
          <span class="label">On GitHub</span>
        </div>
        <div class="stat" aria-label="Languages">
          <span style="font-size:22px; font-weight:700;">JS/TS</span>
          <span class="label">Primary</span>
        </div>
        <div class="stat" aria-label="Tech stack">
          <span style="font-size:22px; font-weight:700;">React</span>
          <span class="label">Favorite</span>
        </div>
      </div>
      <div class="gradient-strip" aria-hidden="true" style="margin-top:12px;"></div>
    </section>
  </div>

  <section class="card" aria-label="Interactive mini-game">
    <h3 style="margin-top:0;">Mini Dice Game (CSS + JS)</h3>
    <p>Roll the die and see a match! It’s silly, but it scratches that itch.</p>
    <div style="display:flex; gap:8px; align-items:center;">
      <div id="dice" class="dice" role="button" aria-label="Roll dice" title="Roll">
        🎲
      </div>
      <div id="dice-result" style="min-width:60px; font-family: ui-monospace, SFMono-Regular, Menlo, Consolas; font-weight:700;">
        - 
      </div>
    </div>
  </section>

  <section class="card" aria-label="Highlighted repos">
    <h3 style="margin-top:0;">Pinned Lightweights</h3>
    <ul>
      <li><a href="https://github.com/mvrck-dev/awesome-tools" target="_blank" rel="noopener">awesome-tools</a> — tiny utilities I actually use</li>
      <li><a href="https://github.com/mvrck-dev/doodle-canvas" target="_blank" rel="noopener">doodle-canvas</a> — canvas experiments that went right</li>
      <li><a href="https://github.com/mvrck-dev/quiz-lite" target="_blank" rel="noopener">quiz-lite</a> — a few brain-teasers</li>
    </ul>
  </section>

  <section class="card" aria-label="Footer">
    <div class="stats-embeds" style="margin-bottom:6px;">
      <div class="embed">
        <strong>Location</strong><br>
        Nārnaund, Haryana, IN
      </div>
      <div class="embed">
        <strong>Contact</strong><br>
        <a href="mailto:you@example.com">you@example.com</a>
      </div>
    </div>
    <div style="font-size:12px; color:var(--muted);">
      This README is a living project. Update whenever inspiration hits. Want more interactivity? Tell me what vibe you want next.
    </div>
  </section>
</div>
