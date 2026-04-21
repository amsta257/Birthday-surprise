# Birthday-surprise
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Happy Birthday, Grace! 🎂💖</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      min-height: 100vh;
      background: linear-gradient(135deg, #f5afb8 0%, #fdd9b5 50%, #ffe6c9 100%);
      font-family: 'Segoe UI', 'Poppins', 'Quicksand', 'Dancing Script', cursive, system-ui, -apple-system, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
      position: relative;
      overflow-x: hidden;
    }

    /* Floating balloons & confetti background */
    .floating-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 1;
      overflow: hidden;
    }

    .floating-bg i {
      position: absolute;
      font-size: 1.8rem;
      animation: floatUp 14s infinite linear;
      bottom: -10%;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 0;
      }
      15% {
        opacity: 0.8;
      }
      85% {
        opacity: 0.7;
      }
      100% {
        transform: translateY(-120vh) rotate(360deg);
        opacity: 0;
      }
    }

    /* main card */
    .birthday-card {
      position: relative;
      z-index: 20;
      max-width: 600px;
      width: 100%;
      background: rgba(255, 251, 248, 0.98);
      backdrop-filter: blur(2px);
      border-radius: 70px 50px 80px 50px;
      box-shadow: 0 35px 55px rgba(0, 0, 0, 0.2), 0 0 0 12px rgba(255, 220, 200, 0.7);
      padding: 2rem 2rem 2.5rem;
      text-align: center;
      animation: softAppear 0.7s cubic-bezier(0.2, 0.9, 0.4, 1.1);
    }

    @keyframes softAppear {
      0% {
        transform: scale(0.92) translateY(20px);
        opacity: 0;
      }
      100% {
        transform: scale(1) translateY(0);
        opacity: 1;
      }
    }

    .cake-icon {
      font-size: 5rem;
      filter: drop-shadow(2px 8px 15px rgba(0, 0, 0, 0.15));
      margin-bottom: 0.2rem;
      display: inline-block;
      animation: wiggle 1.5s infinite ease;
    }

    @keyframes wiggle {
      0%, 100% { transform: rotate(0deg); }
      25% { transform: rotate(10deg); }
      75% { transform: rotate(-5deg); }
    }

    h1 {
      font-size: 3rem;
      background: linear-gradient(125deg, #e85d75, #f4a261, #e76f51);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      margin: 0.5rem 0 0.2rem;
      font-weight: 800;
      font-family: 'Dancing Script', cursive;
    }

    .grace-name {
      font-size: 2.8rem;
      background: linear-gradient(120deg, #e84393, #f4a261);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      display: inline-block;
      margin: 0 5px;
    }

    .subtitle {
      font-size: 1.2rem;
      color: #c96f5e;
      background: #fff0e6;
      display: inline-block;
      padding: 0.4rem 1.5rem;
      border-radius: 60px;
      margin: 0.8rem 0 1rem;
      font-weight: 500;
    }

    /* message box */
    .message-box {
      background: #fff9f5;
      border-radius: 40px;
      padding: 1.5rem;
      margin: 1.2rem 0;
      box-shadow: inset 0 1px 4px #ffe0cc, 0 8px 20px rgba(0,0,0,0.05);
      border: 1px solid #ffe0cc;
    }

    .message-box p {
      font-size: 1.1rem;
      line-height: 1.6;
      color: #5a3e35;
      margin: 12px 0;
    }

    .signature {
      font-family: 'Dancing Script', cursive;
      font-size: 1.4rem;
      color: #e85d75;
      margin-top: 10px;
    }

    /* birthday wishes options */
    .wishes-container {
      margin: 20px 0;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 12px;
    }

    .wish-card {
      background: #ffe8e0;
      border-radius: 60px;
      padding: 8px 16px;
      font-size: 0.9rem;
      font-weight: 500;
      color: #b84c5e;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      cursor: pointer;
      transition: all 0.2s;
      border: 1px solid #ffcdb5;
    }

    .wish-card:hover {
      background: #ffd9cc;
      transform: scale(1.02);
    }

    /* balloon button */
    .balloon-btn {
      background: #e85d75;
      border: none;
      color: white;
      font-size: 1.2rem;
      padding: 12px 28px;
      border-radius: 60px;
      cursor: pointer;
      font-weight: bold;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      margin: 15px 0 10px;
      transition: 0.2s;
      font-family: inherit;
      box-shadow: 0 6px 14px rgba(232, 93, 117, 0.3);
    }

    .balloon-btn:hover {
      background: #c74f67;
      transform: scale(1.02);
    }

    /* footer */
    .footer-note {
      margin-top: 1.5rem;
      font-size: 0.85rem;
      color: #cc8b7a;
      border-top: 1px dashed #ffd9cc;
      padding-top: 1.2rem;
    }

    /* confetti modal */
    .modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.7);
      backdrop-filter: blur(6px);
      z-index: 1000;
      display: flex;
      align-items: center;
      justify-content: center;
      opacity: 0;
      visibility: hidden;
      transition: all 0.3s ease;
    }

    .modal.active {
      opacity: 1;
      visibility: visible;
    }

    .modal-content {
      background: #fffaf7;
      max-width: 400px;
      width: 85%;
      border-radius: 55px;
      padding: 2rem 1.5rem;
      text-align: center;
      transform: scale(0.8);
      transition: transform 0.3s cubic-bezier(0.34, 1.2, 0.64, 1);
      border: 2px solid #ffccb3;
    }

    .modal.active .modal-content {
      transform: scale(1);
    }

    .modal-content h3 {
      font-size: 2rem;
      color: #e85d75;
      font-family: 'Dancing Script', cursive;
    }

    .close-modal {
      background: #e85d75;
      border: none;
      color: white;
      font-size: 1rem;
      padding: 8px 20px;
      border-radius: 50px;
      margin-top: 20px;
      cursor: pointer;
    }

    @keyframes bounce {
      0%,100%{ transform: translateY(0); }
      50%{ transform: translateY(-5px); }
    }

    @media (max-width: 550px) {
      .birthday-card { padding: 1.5rem; }
      h1 { font-size: 2.2rem; }
      .grace-name { font-size: 2rem; }
      .message-box p { font-size: 0.95rem; }
    }
  </style>
</head>
<body>

<div class="floating-bg" id="floatingBg"></div>

<div class="birthday-card">
  <div class="cake-icon">🎂🎈🎉</div>
  <h1>Happy Birthday, <span class="grace-name">Grace!</span> 🎀</h1>
  <div class="subtitle">✨ Today is all about YOU ✨</div>
  
  <div class="message-box">
    <p>💖 Dear Grace, 💖</p>
    <p>You're one of those rare souls who makes the world brighter just by being in it. I'm so grateful for your kindness, your laugh, and the way you always know how to make someone feel seen.</p>
    <p>May your year ahead be filled with as much joy as you bring to everyone around you. Wishing you endless cake, big smiles, and all the happiness you deserve!</p>
    <p class="signature">— With love, your friend 💕</p>
  </div>
  
  <div class="wishes-container">
    <div class="wish-card" data-wish="🎂 Happy Birthday, Grace! You're a total gem. Shine bright today and always! ✨">🎂 Sweet & Short</div>
    <div class="wish-card" data-wish="🎉 Grace! Hope your day is as amazing as you are — full of laughter, good vibes, and maybe three cakes. Love you, girl! 💖🥳">🎈 Fun & Playful</div>
    <div class="wish-card" data-wish="🌟 On your birthday, I just want to say thank you. Thank you for your loyalty, your honesty, and your beautiful heart. You're a gift. Happy Birthday, Grace! 💫">🌟 Deep & Meaningful</div>
  </div>
  
  <button class="balloon-btn" id="celebrateBtn">🎈 Send Birthday Confetti 🎉</button>
  
  <div class="footer-note">
    <span>💕 You deserve the world, Grace 💕</span>
    <span>🎂 Cheers to another fabulous year 🎂</span>
  </div>
</div>

<!-- Celebration modal -->
<div id="celebrationModal" class="modal">
  <div class="modal-content">
    <div style="font-size: 3rem;">🎉🎂🎈💖✨</div>
    <h3>Happy Birthday, Grace! 🎀</h3>
    <p>Wishing you a day filled with love, laughter, and cake! 🍰</p>
    <button class="close-modal" id="closeModalBtn">💕 Thank you! 💕</button>
  </div>
</div>

<script>
  (function() {
    // ---------- FLOATING BALLOONS & CAKES ----------
    const floatContainer = document.getElementById('floatingBg');
    const FLOATING_ITEMS = ['🎈', '🎂', '🎉', '🎁', '🎀', '🌸', '✨', '💖', '🎊', '🍰', '🕯️', '🎵'];
    
    function createFloatingItem() {
      const el = document.createElement('i');
      el.innerHTML = FLOATING_ITEMS[Math.floor(Math.random() * FLOATING_ITEMS.length)];
      const size = Math.random() * 28 + 18;
      el.style.fontSize = size + 'px';
      el.style.left = Math.random() * 100 + '%';
      el.style.opacity = Math.random() * 0.6 + 0.3;
      el.style.animationDuration = Math.random() * 12 + 10 + 's';
      el.style.animationDelay = Math.random() * 10 + 's';
      floatContainer.appendChild(el);
      setTimeout(() => { if(el && el.remove) el.remove(); }, 15000);
    }
    
    for(let i = 0; i < 35; i++) setTimeout(() => createFloatingItem(), i * 180);
    setInterval(createFloatingItem, 1500);
    
    // ---------- WISH CARD CLICK (show custom message) ----------
    const wishCards = document.querySelectorAll('.wish-card');
    const modal = document.getElementById('celebrationModal');
    const modalContent = modal.querySelector('.modal-content');
    const closeModalBtn = document.getElementById('closeModalBtn');
    
    // store original modal content to restore
    const originalModalHTML = modalContent.innerHTML;
    
    function showCustomWish(wishText) {
      // temporarily change modal content
      modalContent.innerHTML = `
        <div style="font-size: 3rem;">🎀💖🎂</div>
        <h3 style="font-size: 1.6rem;">For You, Grace ✨</h3>
        <p style="font-size: 1.1rem; margin: 15px 0;">${wishText}</p>
        <button class="close-modal" id="tempCloseBtn">💕 Love it! 💕</button>
      `;
      modal.classList.add('active');
      const tempClose = document.getElementById('tempCloseBtn');
      if (tempClose) {
        tempClose.addEventListener('click', () => {
          modal.classList.remove('active');
          // restore original modal after closing
          setTimeout(() => {
            modalContent.innerHTML = originalModalHTML;
            // re-attach close button event for original modal after restore
            const newCloseBtn = document.getElementById('closeModalBtn');
            if (newCloseBtn) {
              newCloseBtn.addEventListener('click', () => modal.classList.remove('active'));
            }
          }, 100);
        });
      }
      // also close on overlay click
      modal.onclick = (e) => {
        if (e.target === modal) {
          modal.classList.remove('active');
          setTimeout(() => {
            modalContent.innerHTML = originalModalHTML;
            const newCloseBtn = document.getElementById('closeModalBtn');
            if (newCloseBtn) newCloseBtn.addEventListener('click', () => modal.classList.remove('active'));
          }, 100);
        }
      };
    }
    
    wishCards.forEach(card => {
      card.addEventListener('click', (e) => {
        const wish = card.getAttribute('data-wish');
        if (wish) showCustomWish(wish);
      });
    });
    
    // ---------- CONFETTI CELEBRATION BUTTON ----------
    const celebrateBtn = document.getElementById('celebrateBtn');
    
    function launchConfetti() {
      if (typeof confetti === 'function') {
        confetti({ particleCount: 200, spread: 100, origin: { y: 0.6 }, colors: ['#e85d75', '#f4a261', '#f7c59f', '#ffb7c5'] });
        confetti({ particleCount: 150, spread: 130, origin: { y: 0.3, x: 0.2 }, startVelocity: 18 });
        confetti({ particleCount: 150, spread: 130, origin: { y: 0.4, x: 0.8 }, startVelocity: 18 });
        setTimeout(() => {
          confetti({ particleCount: 400, spread: 80, origin: { y: 0.5 }, startVelocity: 22, colors: ['#ffd966', '#e85d75', '#f8c291', '#ffb3c6'] });
        }, 200);
        setTimeout(() => {
          confetti({ particleCount: 300, spread: 110, origin: { y: 0.7 } });
        }, 450);
      } else {
        // fallback: create more floating items
        for (let i=0; i<60; i++) setTimeout(() => createFloatingItem(), i*30);
      }
      
      // Also burst extra balloons on screen
      const symbols = ['🎈', '🎂', '🎉', '🎁', '💖', '🎀'];
      for (let i=0; i<30; i++) {
        const burst = document.createElement('div');
        burst.style.position = 'fixed';
        burst.style.fontSize = (Math.random() * 40 + 28) + 'px';
        burst.style.left = Math.random() * 100 + '%';
        burst.style.top = Math.random() * 80 + 10 + '%';
        burst.style.pointerEvents = 'none';
        burst.style.zIndex = '999';
        burst.style.opacity = '0.9';
        burst.style.animation = 'floatUp 1.5s ease-out forwards';
        burst.innerHTML = symbols[Math.floor(Math.random() * symbols.length)];
        document.body.appendChild(burst);
        setTimeout(() => burst.remove(), 1600);
      }
    }
    
    function showCelebration() {
      launchConfetti();
      // show the birthday modal
      modal.classList.add('active');
      // ensure modal content is original
      modalContent.innerHTML = originalModalHTML;
      const newClose = document.getElementById('closeModalBtn');
      if (newClose) {
        newClose.addEventListener('click', () => modal.classList.remove('active'));
      }
      modal.onclick = (e) => {
        if (e.target === modal) modal.classList.remove('active');
      };
    }
    
    celebrateBtn.addEventListener('click', showCelebration);
    
    // also attach close button from original (if exists after restores)
    const originalClose = document.getElementById('closeModalBtn');
    if (originalClose) {
      originalClose.addEventListener('click', () => modal.classList.remove('active'));
    }
    
    // Load canvas-confetti
    if (typeof confetti !== 'function') {
      const script = document.createElement('script');
      script.src = 'https://cdn.jsdelivr.net/npm/canvas-confetti@1';
      script.onload = () => { console.log('🎉 Confetti ready for Grace!'); };
      document.head.appendChild(script);
    }
    
    // ---------- EXTRA TOUCH: Floating birthday message after 2 sec ----------
    setTimeout(() => {
      const popup = document.createElement('div');
      popup.innerText = "🎂 Grace, you're amazing! 🎂";
      popup.style.position = 'fixed';
      popup.style.bottom = '20px';
      popup.style.right = '20px';
      popup.style.backgroundColor = '#ffe8e0';
      popup.style.padding = '10px 18px';
      popup.style.borderRadius = '50px';
      popup.style.fontSize = '0.9rem';
      popup.style.fontWeight = 'bold';
      popup.style.color = '#c74f67';
      popup.style.boxShadow = '0 4px 12px rgba(0,0,0,0.1)';
      popup.style.zIndex = '1002';
      popup.style.border = '1px solid #ffccb3';
      popup.style.pointerEvents = 'none';
      document.body.appendChild(popup);
      setTimeout(() => popup.remove(), 5000);
    }, 2000);
    
    console.log("%c🎂 Happy Birthday, Grace! Wishing you joy today and always! 🎉", "color: #e85d75; font-size: 14px; font-weight: bold;");
  })();
</script>
</body>
</html>
