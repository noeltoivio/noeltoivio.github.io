---
layout: default
title:  PC will shut down soon!
button: false
---

<audio id="pageSound" src="/assets/audio/Belligerent.wav" preload="auto"></audio>

<script>
document.addEventListener("DOMContentLoaded", function() {
  const sound = document.getElementById("pageSound");

  // Try autoplay
  sound.play().catch(err => {
    console.log("Autoplay blocked:", err);

    // Create a manual play button as fallback
    const btn = document.createElement("button");
    btn.textContent = "🔊 Play sound";
    btn.style = `
      position: fixed;
      top: 20px;
      right: 20px;
      padding: 10px 16px;
      background: #222;
      color: white;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-size: 16px;
      z-index: 9999;
    `;
    btn.onclick = () => {
      sound.play();
      btn.remove();
    };
    document.body.appendChild(btn);
  });
});
</script>

If not otherwise specified, the PC is set to turn off in 45 min.

<style>
.site-footer {
  display: none;
}
</style>