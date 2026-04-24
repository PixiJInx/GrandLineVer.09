const fs = require('fs');
let html = fs.readFileSync('grand-line-race.html', 'utf8');

// 1. Meta Tags
html = html.replace(
  /<meta name="viewport"[^>]+>/,
  `<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <meta name="theme-color" content="#F9F9F6">`
);

// 2. Body padding
html = html.replace(
  /padding: 0 0 4rem 0;/,
  `padding: 0 0 calc(80px + env(safe-area-inset-bottom)) 0;`
);

// 3. Overlays Display None -> Opacity
html = html.replace(
  /display: none;(\s*margin-bottom: 2rem;\s*}\s*\.challenge-ended-banner\.show)/,
  `display: none;$1`
); // keep challenge ended banner logic

html = html.replace(
  /\.winner-overlay,[\s\S]*?\.settings-overlay[\s\S]*?{[\s\S]*?}/,
  `.winner-overlay,
    .settings-overlay {
      position: fixed;
      inset: 0;
      background: rgba(249, 249, 246, 0.98);
      z-index: 2000;
      display: flex;
      opacity: 0;
      pointer-events: none;
      align-items: center;
      justify-content: center;
      padding: 2rem;
      backdrop-filter: blur(4px);
      transition: opacity 0.3s ease;
    }`
);

html = html.replace(
  /\.winner-overlay\.show,[\s\S]*?\.settings-overlay\.show[\s\S]*?{[\s\S]*?}/,
  `.winner-overlay.show,
    .settings-overlay.show {
      opacity: 1;
      pointer-events: auto;
    }`
);

// Remove default transform CSS from winner/settings overlay show
html = html.replace(
  /(\.winner-overlay\.show\s*\.winner-box\s*{[\s\S]*?})/,
  ``
);
html = html.replace(
  /(\.settings-overlay\.show\s*\.settings-box\s*{[\s\S]*?})/,
  ``
);

html = html.replace(
  /\.settings-box\s*{[\s\S]*?}/,
  `.settings-box {
      background: var(--white);
      border: var(--border-w) solid var(--black);
      border-radius: var(--br);
      box-shadow: 8px 8px 0px var(--black);
      padding: 2.5rem;
      width: 100%;
      max-width: 800px;
      max-height: 90vh;
      overflow-y: auto;
      transform: scale(0.95);
      transition: transform 0.3s var(--spring);
    }
    .settings-overlay.show .settings-box { transform: scale(1); }`
);

html = html.replace(
  /\.winner-box\s*{[\s\S]*?}/,
  `.winner-box {
      background: var(--white);
      border: var(--border-w) solid var(--black);
      border-radius: var(--br);
      box-shadow: 12px 12px 0px var(--black);
      padding: 4rem 2rem;
      text-align: center;
      max-width: 600px;
      width: 100%;
      transform: scale(0.95);
      transition: transform 0.3s var(--spring);
    }
    .winner-overlay.show .winner-box { transform: scale(1); }`
);

// 4. Inject Mobile Nav CSS & Map Dragging inside @media
html = html.replace(
  /(\/\* Mobile Optimization \*\/[\s\S]*?@media \(max-width: 768px\) {)/,
  `$1
      /* Bottom Nav Bar */
      .bottom-nav {
        display: flex;
        position: fixed;
        bottom: 0;
        left: 0;
        right: 0;
        height: calc(64px + env(safe-area-inset-bottom));
        padding-bottom: env(safe-area-inset-bottom);
        background: var(--white);
        border-top: var(--border-w) solid var(--black);
        z-index: 1000;
        box-shadow: 0 -4px 0px rgba(0,0,0,1);
      }
      .nav-item {
        flex: 1;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background: none;
        border: none;
        border-right: var(--border-w) solid var(--black);
        font-family: inherit;
        font-weight: 900;
        font-size: 0.75rem;
        cursor: pointer;
        color: var(--black);
        text-transform: uppercase;
        letter-spacing: -0.02em;
      }
      .nav-item:last-child {
        border-right: none;
      }
      .nav-item.active {
        background: var(--yellow);
      }
      .nav-icon {
        font-size: 1.5rem;
        margin-bottom: 2px;
      }

      /* Hide Bentos by default on mobile */
      .map-bento, .leaderboard-bento, .bottom-grid {
        display: none !important; 
      }
      .map-bento.active-tab, .leaderboard-bento.active-tab, .bottom-grid.active-tab {
        display: block !important;
        animation: fadeIn 0.3s ease;
      }
      
      @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
      }

      /* Native App Modals Fullscreen */
      .winner-overlay, .settings-overlay {
        align-items: flex-end;
        padding: 0;
      }
      .settings-box, .winner-box {
        width: 100vw;
        height: 100dvh;
        max-height: 100dvh;
        border-radius: 0;
        border: none;
        border-top: var(--border-w) solid var(--black);
        transform: translateY(100%);
        padding-bottom: calc(2rem + env(safe-area-inset-bottom));
      }
      .settings-overlay.show .settings-box, .winner-overlay.show .winner-box {
        transform: translateY(0);
      }
`
);

// Map Scroll touch-action and min-height for inputs globally
html = html.replace(
  /(\.map-scroll\s*{[\s\S]*?})/,
  `.map-scroll {
      width: 100%;
      overflow-x: auto;
      border-top: var(--border-w) solid var(--black);
      border-bottom: var(--border-w) solid var(--black);
      background: var(--bg-alabaster);
      touch-action: pan-y; /* allow custom horizontal pan JS */
      cursor: grab;
    }
    
    input, select, button {
      min-height: 48px;
    }`
);

// Add Bottom Nav
html = html.replace(
  /(<\/body>)/,
  `
  <!-- Mobile Bottom Nav -->
  <nav class="bottom-nav" id="bottomNav" style="display: none;">
    <button class="nav-item active" onclick="switchTab('map', event)">
      <span class="nav-icon">🗺️</span>
      <span>Map</span>
    </button>
    <button class="nav-item" onclick="switchTab('leaderboard', event)">
      <span class="nav-icon">🏆</span>
      <span>Rank</span>
    </button>
    <button class="nav-item" onclick="switchTab('log', event)">
      <span class="nav-icon">✍️</span>
      <span>Log Hours</span>
    </button>
    <button class="nav-item" onclick="switchTab('activity', event)">
      <span class="nav-icon">📜</span>
      <span>Crew Logs</span>
    </button>
  </nav>

  <script>
    // Tab switching logic for mobile
    window.switchTab = function(tab, event) {
      if(event) {
        document.querySelectorAll('.nav-item').forEach(btn => btn.classList.remove('active'));
        event.currentTarget.classList.add('active');
      }

      document.getElementById('tab-map').classList.remove('active-tab');
      document.getElementById('tab-leaderboard').classList.remove('active-tab');
      document.getElementById('tab-log-container').classList.remove('active-tab');

      if(tab === 'map') document.getElementById('tab-map').classList.add('active-tab');
      if(tab === 'leaderboard') document.getElementById('tab-leaderboard').classList.add('active-tab');
      if(tab === 'log') {
        document.getElementById('tab-log-container').classList.add('active-tab');
        document.getElementById('tab-log').style.display = 'block';
        document.getElementById('tab-activity').style.display = 'none';
      }
      if(tab === 'activity') {
        document.getElementById('tab-log-container').classList.add('active-tab');
        document.getElementById('tab-log').style.display = 'none';
        document.getElementById('tab-activity').style.display = 'block';
      }
      
      // Update body for mobile layout
      document.body.style.overflowX = 'hidden';
    }

    // Touch Panning for map
    const mapScroll = document.querySelector('.map-scroll');
    if(mapScroll) {
      let isDown = false;
      let startX;
      let scrollLeft;

      mapScroll.addEventListener('mousedown', (e) => {
        isDown = true;
        mapScroll.style.cursor = 'grabbing';
        startX = e.pageX - mapScroll.offsetLeft;
        scrollLeft = mapScroll.scrollLeft;
      });
      mapScroll.addEventListener('mouseleave', () => {
        isDown = false;
        mapScroll.style.cursor = 'grab';
      });
      mapScroll.addEventListener('mouseup', () => {
        isDown = false;
        mapScroll.style.cursor = 'grab';
      });
      mapScroll.addEventListener('mousemove', (e) => {
        if(!isDown) return;
        e.preventDefault();
        const x = e.pageX - mapScroll.offsetLeft;
        const walk = (x - startX) * 1.5;
        mapScroll.scrollLeft = scrollLeft - walk;
      });
    }
    
    // Check if mobile and show bottom nav
    if(window.innerWidth <= 768) {
      document.getElementById('bottomNav').style.display = 'flex';
      window.switchTab('map', null);
    }
  </script>
$1`
);

// Add IDs to bentos
html = html.replace(/<section class="bento map-bento">/, '<section class="bento map-bento" id="tab-map">');
html = html.replace(/<section class="bento leaderboard-bento">/, '<section class="bento leaderboard-bento" id="tab-leaderboard">');
html = html.replace(/<div class="bottom-grid">/, '<div class="bottom-grid" id="tab-log-container">'); 
html = html.replace(/<div class="bento form-bento">/, '<div class="bento form-bento" id="tab-log">');
html = html.replace(/<div class="bento log-bento" style="display:flex; flex-direction:column;">/, '<div class="bento log-bento" id="tab-activity" style="display:flex; flex-direction:column;">');

fs.writeFileSync('grand-line-race.html', html);
console.log("SUCCESS");
