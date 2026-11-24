# Akaki-Peter-Football-Blogging
Lets talk sport

```html
<!DOCTYPE html>
<html lang="en" class="dark">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AKAKI SPORTS | Global & Kenyan Football Hub</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Teko:wght@600;700&display=swap" rel="stylesheet">
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            display: ['Teko', 'sans-serif'],
          },
          colors: {
            akaki: {
              bg: '#090A0F',
              card: '#12151E',
              surface: '#1A1E2B',
              border: '#272C3D',
              red: '#EF233C',
              gold: '#F59E0B',
              pitch: '#10B981',
              pitchDark: '#064E3B'
            }
          },
          animation: {
            'pulse-fast': 'pulse 1.5s cubic-bezier(0.4, 0, 0.6, 1) infinite',
            'marquee': 'marquee 28s linear infinite',
          },
          keyframes: {
            marquee: {
              '0%': { transform: 'translateX(0%)' },
              '100%': { transform: 'translateX(-50%)' },
            }
          }
        }
      }
    }
  </script>
  <style>
    /* Custom scrollbar for broadcast feed */
    ::-webkit-scrollbar { width: 6px; height: 6px; }
    ::-webkit-scrollbar-track { background: #090A0F; }
    ::-webkit-scrollbar-thumb { background: #272C3D; border-radius: 9999px; }
    ::-webkit-scrollbar-thumb:hover { background: #EF233C; }
    .no-scrollbar::-webkit-scrollbar { display: none; }
    .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
  </style>
</head>
<body class="bg-akaki-bg text-slate-100 font-sans antialiased selection:bg-akaki-red selection:text-white pb-20 md:pb-8">

  <!-- Breaking News Ticker -->
  <div class="bg-akaki-red text-white text-xs font-bold uppercase tracking-wider overflow-hidden py-1.5 border-b border-red-400/30">
    <div class="max-w-7xl mx-auto px-4 flex items-center gap-3">
      <span class="bg-black text-akaki-gold px-2 py-0.5 rounded text-[10px] font-black shrink-0 flex items-center gap-1.5">
        <span class="w-1.5 h-1.5 rounded-full bg-akaki-red animate-ping"></span> BREAKING
      </span>
      <div class="overflow-hidden whitespace-nowrap flex-1">
        <div class="inline-block animate-marquee" id="ticker-content">
          <span>🚨 MANCHESTER UNITED EYEING JANUARY MIDFIELD REINFORCEMENT AT OLD TRAFFORD • </span>
          <span>🇰🇪 FKF PREMIER LEAGUE: AFC LEOPARDS & TUSKER FC LOCKED IN FIERCE TITLE RACE • </span>
          <span>🔥 INGWE FANS PACK NYAYO STADIUM AHEAD OF MASHEMEJI CLASH • </span>
          <span>⚡ BREWERS STRIKER HITS 10 GOALS IN 12 MATCHES FOR TUSKER FC • </span>
          <span>🚨 MANCHESTER UNITED EYEING JANUARY MIDFIELD REINFORCEMENT AT OLD TRAFFORD • </span>
          <span>🇰🇪 FKF PREMIER LEAGUE: AFC LEOPARDS & TUSKER FC LOCKED IN FIERCE TITLE RACE • </span>
        </div>
      </div>
    </div>
  </div>

  <!-- Top Broadcast Header -->
  <header class="sticky top-0 z-40 bg-akaki-bg/90 backdrop-blur-md border-b border-akaki-border">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 h-16 flex items-center justify-between">
      <!-- Brand Logo -->
      <div class="flex items-center gap-3 cursor-pointer" onclick="switchTab('matches')">
        <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-akaki-red via-red-700 to-black p-[1px] shadow-lg shadow-akaki-red/20">
          <div class="w-full h-full bg-akaki-card rounded-xl flex items-center justify-center relative overflow-hidden">
            <div class="absolute inset-0 bg-gradient-to-tr from-akaki-red/20 to-akaki-gold/20"></div>
            <span class="font-display text-2xl font-bold tracking-tighter text-white">AS</span>
          </div>
        </div>
        <div>
          <div class="flex items-center gap-1.5">
            <span class="font-display text-2xl sm:text-3xl font-bold tracking-wide text-white leading-none">AKAKI <span class="text-akaki-red">SPORTS</span></span>
            <span class="hidden sm:inline-block text-[10px] font-extrabold bg-akaki-gold/15 text-akaki-gold border border-akaki-gold/30 px-1.5 py-0.5 rounded uppercase">TV & Hub</span>
          </div>
          <p class="text-[10px] text-slate-400 tracking-widest uppercase font-semibold">Old Trafford to Nyayo Stadium</p>
        </div>
      </div>

      <!-- Desktop Navigation -->
      <nav class="hidden md:flex items-center gap-1 bg-akaki-card p-1 rounded-xl border border-akaki-border">
        <button onclick="switchTab('matches')" id="nav-matches" class="nav-btn px-4 py-2 rounded-lg text-sm font-bold transition-all flex items-center gap-2 bg-akaki-red text-white shadow-md">
          <span class="w-2 h-2 rounded-full bg-white animate-pulse"></span> Live Match Center
        </button>
        <button onclick="switchTab('news')" id="nav-news" class="nav-btn px-4 py-2 rounded-lg text-sm font-bold text-slate-400 hover:text-white transition-all">
          Transfer & Punditry
        </button>
        <button onclick="switchTab('tactics')" id="nav-tactics" class="nav-btn px-4 py-2 rounded-lg text-sm font-bold text-slate-400 hover:text-white transition-all">
          Tactics & Card Builder
        </button>
        <button onclick="switchTab('banter')" id="nav-banter" class="nav-btn px-4 py-2 rounded-lg text-sm font-bold text-slate-400 hover:text-white transition-all">
          Fan Banter & Polls
        </button>
      </nav>

      <!-- Live Sim Controls / Studio Status -->
      <div class="flex items-center gap-2 sm:gap-3">
        <button onclick="toggleSimSpeed()" id="sim-toggle-btn" class="px-3 py-1.5 rounded-lg bg-akaki-surface hover:bg-akaki-border border border-akaki-border text-xs font-bold text-akaki-pitch flex items-center gap-1.5 transition" title="Toggle Live Match Simulation">
          <span class="w-2 h-2 rounded-full bg-akaki-pitch animate-pulse"></span>
          <span id="sim-status-text">LIVE SIM: ON</span>
        </button>
        <button onclick="openNewsModal()" class="px-3 py-1.5 rounded-lg bg-akaki-gold hover:bg-amber-400 text-black text-xs font-extrabold uppercase tracking-wide shadow-lg shadow-akaki-gold/10 transition flex items-center gap-1">
          <span>+ Post Take</span>
        </button>
      </div>
    </div>
  </header>

  <!-- Main Content Container -->
  <main class="max-w-7xl mx-auto px-4 sm:px-6 pt-6">

    <!-- ==================== TAB 1: LIVE MATCH CENTER ==================== -->
    <section id="tab-matches" class="tab-section space-y-6">
      
      <!-- League Filter & Featured Scoreboard Strip -->
      <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 class="font-display text-3xl sm:text-4xl font-bold uppercase tracking-wide text-white flex items-center gap-2">
            Broadcast Match Center
            <span class="text-xs font-sans font-bold bg-akaki-red/20 text-akaki-red border border-akaki-red/40 px-2.5 py-0.5 rounded-full">3 LIVE MATCHES</span>
          </h1>
          <p class="text-xs sm:text-sm text-slate-400">Real-time simulated scores, xG telemetry & live commentary for EPL and FKF Premier League.</p>
        </div>
        <div class="flex items-center gap-2 overflow-x-auto no-scrollbar pb-1">
          <button onclick="filterMatches('ALL')" class="match-filter-btn active px-3 py-1.5 rounded-lg text-xs font-bold bg-white text-black transition">All Leagues</button>
          <button onclick="filterMatches('EPL')" class="match-filter-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-akaki-card text-slate-300 border border-akaki-border hover:border-slate-500 transition">🏴󠁧󠁢󠁥󠁮󠁧󠁿 Premier League</button>
          <button onclick="filterMatches('KPL')" class="match-filter-btn px-3 py-1.5 rounded-lg text-xs font-bold bg-akaki-card text-slate-300 border border-akaki-border hover:border-slate-500 transition">🇰🇪 Kenyan PL</button>
        </div>
      </div>

      <!-- Scoreboard Cards Grid -->
      <div id="scoreboard-grid" class="grid grid-cols-1 md:grid-cols-3 gap-4">
        <!-- Populated dynamically via JS -->
      </div>

      <!-- Detailed Broadcast Center (Selected Match Stats + Commentary) -->
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
        
        <!-- Left 7 Cols: Match Telemetry & Stats -->
        <div class="lg:col-span-7 bg-akaki-card rounded-2xl border border-akaki-border p-5 sm:p-6 shadow-xl relative overflow-hidden">
          <div class="absolute top-0 right-0 w-64 h-64 bg-akaki-red/5 rounded-full blur-3xl pointer-events-none"></div>
          
          <div class="flex items-center justify-between border-b border-akaki-border pb-4 mb-5">
            <div>
              <span id="detail-league" class="text-[11px] font-extrabold uppercase tracking-widest text-akaki-gold">ENGLISH PREMIER LEAGUE</span>
              <h2 id="detail-stadium" class="text-xs text-slate-400 mt-0.5">Old Trafford • Manchester</h2>
            </div>
            <div class="flex items-center gap-2">
              <span id="detail-minute" class="px-3 py-1 rounded-full bg-akaki-red/20 border border-akaki-red/40 text-akaki-red font-extrabold text-xs animate-pulse">67' LIVE</span>
            </div>
          </div>

          <!-- Big Match Banner -->
          <div class="grid grid-cols-3 items-center text-center py-4 bg-akaki-surface/60 rounded-2xl border border-akaki-border/80 mb-6">
            <div class="px-2">
              <div id="detail-home-badge" class="w-12 h-12 sm:w-14 sm:h-14 mx-auto rounded-2xl flex items-center justify-center font-display text-2xl font-bold shadow-lg mb-2">MUN</div>
              <h3 id="detail-home-name" class="font-bold text-sm sm:text-base text-white">Man United</h3>
              <p id="detail-home-scorers" class="text-[11px] text-slate-400 mt-1 space-y-0.5"></p>
            </div>
            
            <div>
              <div class="font-display text-5xl sm:text-6xl font-bold tracking-wider text-white flex items-center justify-center gap-3">
                <span id="detail-home-score">2</span>
                <span class="text-slate-600 text-3xl">:</span>
                <span id="detail-away-score">1</span>
              </div>
              <span class="inline-block mt-1 text-[10px] font-bold uppercase tracking-widest text-akaki-pitch bg-akaki-pitch/10 px-2 py-0.5 rounded">2nd Half</span>
            </div>

            <div class="px-2">
              <div id="detail-away-badge" class="w-12 h-12 sm:w-14 sm:h-14 mx-auto rounded-2xl flex items-center justify-center font-display text-2xl font-bold shadow-lg mb-2">ARS</div>
              <h3 id="detail-away-name" class="font-bold text-sm sm:text-base text-white">Arsenal</h3>
              <p id="detail-away-scorers" class="text-[11px] text-slate-400 mt-1 space-y-0.5"></p>
            </div>
          </div>

          <!-- Live Stats Bars -->
          <div class="space-y-4">
            <div class="flex items-center justify-between text-xs font-bold uppercase tracking-wider text-slate-400">
              <span>Match Telemetry</span>
              <span class="text-akaki-gold">Opta-Style Live Feed</span>
            </div>

            <!-- Possession -->
            <div>
              <div class="flex justify-between text-xs font-bold mb-1.5">
                <span id="stat-poss-home" class="text-white">54%</span>
                <span class="text-slate-400 uppercase text-[11px]">Possession</span>
                <span id="stat-poss-away" class="text-white">46%</span>
              </div>
              <div class="w-full h-2.5 bg-akaki-surface rounded-full overflow-hidden flex gap-0.5">
                <div id="bar-poss-home" class="bg-akaki-red h-full transition-all duration-500" style="width: 54%"></div>
                <div id="bar-poss-away" class="bg-slate-500 h-full transition-all duration-500" style="width: 46%"></div>
              </div>
            </div>

            <!-- Expected Goals (xG) -->
            <div>
              <div class="flex justify-between text-xs font-bold mb-1.5">
                <span id="stat-xg-home" class="text-akaki-gold">1.84</span>
                <span class="text-slate-400 uppercase text-[11px]">Expected Goals (xG)</span>
                <span id="stat-xg-away" class="text-white">1.21</span>
              </div>
              <div class="w-full h-2.5 bg-akaki-surface rounded-full overflow-hidden flex gap-0.5">
                <div id="bar-xg-home" class="bg-akaki-gold h-full transition-all duration-500" style="width: 60%"></div>
                <div id="bar-xg-away" class="bg-slate-500 h-full transition-all duration-500" style="width: 40%"></div>
              </div>
            </div>

            <!-- Total Shots -->
            <div>
              <div class="flex justify-between text-xs font-bold mb-1.5">
                <span id="stat-shots-home" class="text-white">14</span>
                <span class="text-slate-400 uppercase text-[11px]">Total Shots</span>
                <span id="stat-shots-away" class="text-white">10</span>
              </div>
              <div class="w-full h-2.5 bg-akaki-surface rounded-full overflow-hidden flex gap-0.5">
                <div id="bar-shots-home" class="bg-akaki-pitch h-full transition-all duration-500" style="width: 58%"></div>
                <div id="bar-shots-away" class="bg-slate-500 h-full transition-all duration-500" style="width: 42%"></div>
              </div>
            </div>

            <!-- Shots on Target -->
            <div>
              <div class="flex justify-between text-xs font-bold mb-1.5">
                <span id="stat-sot-home" class="text-white">6</span>
                <span class="text-slate-400 uppercase text-[11px]">Shots on Target</span>
                <span id="stat-sot-away" class="text-white">4</span>
              </div>
              <div class="w-full h-2.5 bg-akaki-surface rounded-full overflow-hidden flex gap-0.5">
                <div id="bar-sot-home" class="bg-akaki-red h-full transition-all duration-500" style="width: 60%"></div>
                <div id="bar-sot-away" class="bg-slate-500 h-full transition-all duration-500" style="width: 40%"></div>
              </div>
            </div>
          </div>

          <!-- Quick Match Action Trigger (User can trigger a simulated big moment) -->
          <div class="mt-6 pt-4 border-t border-akaki-border flex flex-wrap items-center justify-between gap-2">
            <span class="text-xs text-slate-400">Simulate Broadcast Event:</span>
            <div class="flex gap-2">
              <button onclick="triggerMatchEvent('GOAL_HOME')" class="px-3 py-1.5 rounded-lg bg-akaki-pitch/20 hover:bg-akaki-pitch/30 text-akaki-pitch border border-akaki-pitch/40 text-xs font-bold transition">⚽ Home Goal</button>
              <button onclick="triggerMatchEvent('GOAL_AWAY')" class="px-3 py-1.5 rounded-lg bg-akaki-red/20 hover:bg-akaki-red/30 text-akaki-red border border-akaki-red/40 text-xs font-bold transition">⚽ Away Goal</button>
              <button onclick="triggerMatchEvent('CHANCE')" class="px-3 py-1.5 rounded-lg bg-akaki-surface hover:bg-akaki-border text-slate-200 border border-akaki-border text-xs font-bold transition">🔥 Big Chance</button>
            </div>
          </div>
        </div>

        <!-- Right 5 Cols: Live Commentary Feed -->
        <div class="lg:col-span-5 bg-akaki-card rounded-2xl border border-akaki-border p-5 flex flex-col h-[500px]">
          <div class="flex items-center justify-between border-b border-akaki-border pb-3 mb-3">
            <div class="flex items-center gap-2">
              <span class="w-2.5 h-2.5 rounded-full bg-akaki-red animate-ping"></span>
              <h3 class="font-display text-2xl font-bold uppercase tracking-wide text-white">Live Commentary</h3>
            </div>
            <span class="text-[11px] font-semibold text-slate-400">AKAKI Studio Desk</span>
          </div>
          
          <div id="commentary-feed" class="flex-1 overflow-y-auto space-y-3 pr-1">
            <!-- Commentary items injected here -->
          </div>
        </div>

      </div>
    </section>

    <!-- ==================== TAB 2: BREAKING NEWS & PUNDITRY FEED ==================== -->
    <section id="tab-news" class="tab-section hidden space-y-6">
      <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
        <div>
          <h1 class="font-display text-3xl sm:text-4xl font-bold uppercase tracking-wide text-white">Breaking Transfer News & Punditry</h1>
          <p class="text-xs sm:text-sm text-slate-400">Exclusive stories from Old Trafford, Nyayo Stadium, and the AKAKI fan community.</p>
        </div>
        <button onclick="openNewsModal()" class="px-4 py-2.5 rounded-xl bg-akaki-red hover:bg-red-600 text-white font-bold text-sm shadow-lg shadow-akaki-red/25 transition flex items-center justify-center gap-2">
          <span>✍️ Publish Article / Hot Take</span>
        </button>
      </div>

      <!-- Category Filter Pills -->
      <div class="flex items-center gap-2 overflow-x-auto no-scrollbar pb-1">
        <button onclick="filterNews('ALL')" class="news-filter-btn active px-4 py-2 rounded-xl text-xs font-bold bg-white text-black transition shrink-0">All Stories</button>
        <button onclick="filterNews('EPL')" class="news-filter-btn px-4 py-2 rounded-xl text-xs font-bold bg-akaki-card text-slate-300 border border-akaki-border hover:border-akaki-red transition shrink-0">🏴󠁧󠁢󠁥󠁮󠁧󠁿 EPL & Man Utd</button>
        <button onclick="filterNews('Kenyan Football')" class="news-filter-btn px-4 py-2 rounded-xl text-xs font-bold bg-akaki-card text-slate-300 border border-akaki-border hover:border-akaki-pitch transition shrink-0">🇰🇪 Kenyan Football</button>
        <button onclick="filterNews('Transfer Rumors')" class="news-filter-btn px-4 py-2 rounded-xl text-xs font-bold bg-akaki-card text-slate-300 border border-akaki-border hover:border-akaki-gold transition shrink-0">🚨 Transfer Rumors</button>
        <button onclick="filterNews('Fan Banter')" class="news-filter-btn px-4 py-2 rounded-xl text-xs font-bold bg-akaki-card text-slate-300 border border-akaki-border hover:border-purple-500 transition shrink-0">🗣️ Fan Banter</button>
      </div>

      <!-- News Grid -->
      <div id="news-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Populated dynamically -->
      </div>
    </section>

    <!-- ==================== TAB 3: TACTICS & MATCHDAY CARD BUILDER ==================== -->
    <section id="tab-tactics" class="tab-section hidden space-y-6">
      <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
        <div>
          <h1 class="font-display text-3xl sm:text-4xl font-bold uppercase tracking-wide text-white">Matchday Lineup & Tactics Studio</h1>
          <p class="text-xs sm:text-sm text-slate-400">Build your Starting XI, select a preset squad or customize names, and export an official AKAKI SPORTS graphic card.</p>
        </div>
        <div class="flex flex-wrap items-center gap-2">
          <select id="preset-team-select" onchange="loadPresetSquad(this.value)" class="bg-akaki-card border border-akaki-border text-white text-xs font-bold rounded-xl px-3 py-2.5 focus:outline-none focus:border-akaki-gold">
            <option value="MANUTD">🔴 Preset: Manchester United XI</option>
            <option value="AFC">🔵 Preset: AFC Leopards (Ingwe) XI</option>
            <option value="TUSKER">🟡 Preset: Tusker FC (Brewers) XI</option>
          </select>
          <select id="formation-select" onchange="changeFormation(this
