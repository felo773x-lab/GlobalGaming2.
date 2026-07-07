<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GameToZone - Play & Earn</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    
    <script src="https://www.gstatic.com/firebasejs/10.13.1/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.13.1/firebase-auth-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.13.1/firebase-firestore-compat.js"></script>

    <!-- ADSGRAM SDK -->
    <script src="https://sad.adsgram.ai/js/sad.min.js"></script>

    <style>
        body { font-family: 'Poppins', sans-serif; background-color: #0f172a; color: #fff; user-select: none; }
        ::-webkit-scrollbar { width: 5px; }
        ::-webkit-scrollbar-track { background: #1e293b; }
        ::-webkit-scrollbar-thumb { background: #6366f1; border-radius: 5px; }
        .pulse-gold-btn { animation: pulse-gold 2s infinite; }
        @keyframes pulse-gold { 0% { box-shadow: 0 0 0 0 rgba(234, 179, 8, 0.7); } 70% { box-shadow: 0 0 0 10px rgba(234, 179, 8, 0); } 100% { box-shadow: 0 0 0 0 rgba(234, 179, 8, 0); } }
        .toast { position: fixed; top: 20px; left: 50%; transform: translateX(-50%); z-index: 2000; background: #1e293b; border-left: 4px solid #6366f1; padding: 15px; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.5); display: flex; align-items: center; opacity: 0; transition: opacity 0.3s; }
        .toast.show { opacity: 1; }
        .nav-item.active { color: #6366f1; }
        .game-frame { width: 100%; height: 100%; border: none; }
        .disabled-card { opacity: 0.5; pointer-events: none; filter: grayscale(1); }
    </style>
</head>
<body class="h-screen flex flex-col relative">

    <div id="toast-container"></div>

    <!-- Auth -->
    <div id="auth-screen" class="fixed inset-0 z-50 bg-slate-900 flex flex-col items-center justify-center p-6">
        <div class="w-24 h-24 bg-indigo-600 rounded-full flex items-center justify-center mb-6 shadow-lg shadow-indigo-500/50">
            <i class="fas fa-gamepad text-4xl text-white"></i>
        </div>
        <h1 class="text-3xl font-bold mb-2 text-transparent bg-clip-text bg-gradient-to-r from-indigo-400 to-cyan-400">GameToZone</h1>
        <p class="text-slate-400 mb-8 text-center">Play, Watch & Earn Real Cash!</p>
        <button onclick="initAuth()" class="w-full max-w-xs bg-indigo-600 hover:bg-indigo-700 py-3 rounded-xl font-bold text-lg shadow-lg">Start Earning</button>
        <p class="text-xs text-slate-500 mt-4">Connecting...</p>
    </div>

    <!-- Main -->
    <div id="main-app" class="hidden flex-1 flex flex-col overflow-hidden pb-16">
        <header class="flex justify-between items-center p-4 bg-slate-800/80 backdrop-blur sticky top-0 z-20 border-b border-slate-700">
            <div class="flex items-center">
                <div class="w-8 h-8 rounded-full bg-yellow-500 flex items-center justify-center mr-2 shadow-lg">
                    <i class="fas fa-coins text-white text-xs"></i>
                </div>
                <div>
                    <p class="text-[10px] text-slate-400 uppercase">Balance</p>
                    <p class="font-bold text-white leading-none" id="header-balance">0</p>
                </div>
            </div>
            <div class="font-bold text-indigo-400">GameToZone</div>
        </header>

        <main class="flex-1 overflow-y-auto p-4 relative">
            <div id="home-page" class="page-section">
                <!-- Socials -->
                <div id="social-links-container" class="flex justify-center gap-4 mb-6 hidden"></div>

                <!-- Watch & Earn -->
                <div id="watch-earn-card" onclick="triggerWatchEarn()" class="bg-gradient-to-r from-purple-600 to-blue-600 rounded-2xl p-6 mb-6 relative overflow-hidden shadow-lg active:scale-95 transition cursor-pointer">
                    <div class="relative z-10">
                        <h2 class="text-2xl font-bold text-white mb-1"><i class="fas fa-play-circle mr-2"></i>Watch & Earn</h2>
                        <p class="text-blue-100 text-sm">Watch ads to get coins!</p>
                        <div class="mt-4 inline-block bg-white/20 px-4 py-1 rounded-full text-xs font-bold backdrop-blur-sm">
                            GET <span id="ad-reward-disp">50</span> COINS
                        </div>
                        <p id="ad-timer-msg" class="text-xs text-yellow-300 mt-2 hidden">Next ad in: <span id="ad-cooldown-timer">0</span>s</p>
                    </div>
                    <i class="fas fa-video absolute -bottom-4 -right-4 text-8xl text-white opacity-10"></i>
                </div>

                <!-- Play Games -->
                <div onclick="showPage('games-list-page')" class="bg-gradient-to-r from-orange-500 to-red-600 rounded-2xl p-6 mb-6 relative overflow-hidden shadow-lg active:scale-95 transition cursor-pointer">
                    <div class="relative z-10">
                        <h2 class="text-2xl font-bold text-white mb-1"><i class="fas fa-gamepad mr-2"></i>Play Games</h2>
                        <p class="text-orange-100 text-sm">Play <span id="game-time-disp">60</span>s to earn.</p>
                        <div class="mt-4 inline-block bg-white/20 px-4 py-1 rounded-full text-xs font-bold backdrop-blur-sm">PLAY NOW</div>
                    </div>
                    <i class="fas fa-ghost absolute -bottom-4 -right-4 text-8xl text-white opacity-10"></i>
                </div>

                <div class="grid grid-cols-2 gap-4">
                    <div class="bg-slate-800 p-4 rounded-xl border border-slate-700">
                        <p class="text-slate-400 text-xs">Total Earned</p>
                        <p class="text-xl font-bold text-green-400" id="total-earned-display">0</p>
                    </div>
                    <div class="bg-slate-800 p-4 rounded-xl border border-slate-700">
                        <p class="text-slate-400 text-xs">Refers</p>
                        <p class="text-xl font-bold text-blue-400" id="total-refers-display">0</p>
                    </div>
                </div>
            </div>

            <div id="games-list-page" class="page-section hidden">
                <button onclick="showPage('home-page')" class="mb-4 text-slate-400 text-sm flex items-center"><i class="fas fa-arrow-left mr-2"></i> Back</button>
                <div id="games-list" class="grid grid-cols-2 gap-4">
                    <div class="col-span-2 text-center py-10 text-slate-500">Loading Games...</div>
                </div>
            </div>

            <div id="wallet-page" class="page-section hidden">
                <div class="bg-slate-800 rounded-2xl p-6 mb-6 text-center border border-slate-700">
                    <p class="text-slate-400 text-sm mb-1">Current Balance</p>
                    <h1 class="text-4xl font-bold text-yellow-400 mb-2" id="wallet-balance">0</h1>
                    <p class="text-xs text-green-400 font-bold bg-green-400/10 inline-block px-3 py-1 rounded-full">Rate: 100 Coins = <span id="val-disp">₹1</span></p>
                </div>
                <div class="bg-slate-800 rounded-xl p-4">
                    <h3 class="font-bold mb-4 text-indigo-400">Withdraw Money</h3>
                    <form onsubmit="handleWithdraw(event)" class="space-y-3">
                        <select id="withdraw-method" class="w-full bg-slate-700 border-none rounded-lg p-3 text-white"></select>
                        <input type="text" id="withdraw-details" required placeholder="Enter Mobile / UPI ID" class="w-full bg-slate-700 border-none rounded-lg p-3 text-white">
                        <input type="number" id="withdraw-amount" required min="100" placeholder="Amount (Coins)" class="w-full bg-slate-700 border-none rounded-lg p-3 text-white">
                        <button type="submit" class="w-full bg-green-600 hover:bg-green-700 text-white font-bold py-3 rounded-lg">Submit Request</button>
                    </form>
                </div>
            </div>

            <div id="history-page" class="page-section hidden">
                <h3 class="font-bold mb-4 text-white">Transaction History</h3>
                <div id="tx-history" class="space-y-2"><p class="text-center text-slate-500 text-sm py-10">No transactions.</p></div>
            </div>

            <div id="refer-page" class="page-section hidden">
                <div class="text-center mt-10">
                    <i class="fas fa-users text-6xl text-indigo-500 mb-4"></i>
                    <h2 class="text-2xl font-bold text-white mb-2">Invite Friends</h2>
                    <p class="text-slate-400 mb-6 px-4">Earn <span class="text-yellow-400" id="refer-bonus-disp">500</span> Coins per refer.</p>
                    <div class="bg-slate-800 p-4 rounded-xl mx-4 border border-dashed border-slate-600 mb-6">
                        <p class="text-xs text-slate-400 mb-2">YOUR CODE</p>
                        <div class="flex justify-between items-center bg-slate-900 rounded-lg p-3">
                            <span id="my-ref-code" class="font-mono text-lg font-bold text-white tracking-wider">...</span>
                            <button onclick="copyRefCode()" class="text-indigo-400 hover:text-white"><i class="fas fa-copy"></i></button>
                        </div>
                    </div>
                    <div class="bg-slate-800 p-4 rounded-xl mx-4 border border-slate-700">
                        <p class="text-xs text-slate-400 mb-2 text-left">HAVE A CODE?</p>
                        <div class="flex gap-2">
                            <input type="text" id="input-ref-code" placeholder="Enter Code" class="bg-slate-900 flex-1 rounded-lg p-3 text-white border border-slate-600 outline-none uppercase">
                            <button onclick="redeemReferral()" class="bg-green-600 text-white px-4 rounded-lg font-bold">Apply</button>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <nav class="fixed bottom-0 left-0 right-0 bg-slate-900 border-t border-slate-800 flex justify-around p-2 pb-6 z-30">
            <button onclick="showPage('home-page')" class="nav-item active flex flex-col items-center text-slate-500 w-1/4" id="nav-home"><i class="fas fa-home text-xl mb-1"></i> <span class="text-[10px]">Home</span></button>
            <button onclick="showPage('refer-page')" class="nav-item flex flex-col items-center text-slate-500 w-1/4" id="nav-refer"><i class="fas fa-share-alt text-xl mb-1"></i> <span class="text-[10px]">Refer</span></button>
            <button onclick="showPage('wallet-page')" class="nav-item flex flex-col items-center text-slate-500 w-1/4" id="nav-wallet"><i class="fas fa-wallet text-xl mb-1"></i> <span class="text-[10px]">Wallet</span></button>
            <button onclick="showPage('history-page')" class="nav-item flex flex-col items-center text-slate-500 w-1/4" id="nav-history"><i class="fas fa-history text-xl mb-1"></i> <span class="text-[10px]">History</span></button>
        </nav>
    </div>

    <!-- Overlay -->
    <div id="play-overlay" class="hidden fixed inset-0 z-50 bg-slate-900 flex flex-col">
        <div class="flex justify-between items-center p-3 bg-slate-800 z-10 shadow-lg">
            <button onclick="exitGame()" class="text-white bg-red-600 px-3 py-1 rounded text-xs font-bold">EXIT</button>
            <div class="flex items-center gap-2">
                <i class="fas fa-clock text-slate-400 text-xs"></i>
                <div class="bg-black px-3 py-1 rounded text-yellow-400 font-mono font-bold" id="game-timer">00:00</div>
            </div>
        </div>
        <div id="top-claim-container" class="hidden absolute top-16 left-0 right-0 z-20 flex justify-center px-4">
            <button onclick="triggerClaimReward()" class="bg-gradient-to-r from-yellow-500 to-orange-600 text-white font-bold text-lg py-3 px-8 rounded-full shadow-lg border-2 border-yellow-300 pulse-gold-btn flex items-center gap-2"><i class="fas fa-gift"></i> CLAIM COIN</button>
        </div>
        <div class="flex-1 bg-black relative w-full h-full">
            <iframe id="game-iframe" src="" class="game-frame" sandbox="allow-scripts allow-same-origin"></iframe>
        </div>
    </div>

    <!-- Simulation (Fallback) -->
    <div id="ad-modal" class="hidden fixed inset-0 z-[100] bg-black flex flex-col items-center justify-center p-4">
        <div class="absolute top-4 right-4 text-xs font-bold bg-white text-black px-2 py-1 rounded" id="ad-timer">5s</div>
        <div class="w-full max-w-sm bg-slate-800 p-6 rounded-lg text-center border border-indigo-500">
            <h2 class="text-xl font-bold text-white mb-2">Ad Loading...</h2>
            <div class="h-40 bg-slate-700 rounded mb-4 flex items-center justify-center animate-pulse"><i class="fas fa-ad text-4xl text-slate-500"></i></div>
            <p class="text-xs text-slate-400 mb-4">Please wait...</p>
        </div>
    </div>

    <script>
        const firebaseConfig = {
  apiKey: "AIzaSyDCGKB2n585VwKpbymRTlulCiDHMNclWO0",
  authDomain: "play-stor-a5ac9.firebaseapp.com",
  databaseURL: "https://play-stor-a5ac9-default-rtdb.firebaseio.com",
  projectId: "play-stor-a5ac9",
  storageBucket: "play-stor-a5ac9.firebasestorage.app",
  messagingSenderId: "391459473116",
  appId: "1:391459473116:web:2dd5401c8d5c6aa4da1619",
  measurementId: "G-2MF0K84WQ6"
};

        firebase.initializeApp(firebaseConfig);
        const auth = firebase.auth();
        const db = firebase.firestore();

        let currentUser = null, userData = null, gameTimerInterval = null, secondsPlayed = 0;
        let lastAdWatchTime = 0; // For Cooldown

        let SETTINGS = { gameDuration: 60, gameReward: 50, referBonus: 500, watchAdReward: 50, watchAdDelay: 15, coinValue: "₹1", socials: {}, paymentMethods: ['Paytm','UPI'] };

        async function initAuth() { try { await auth.signInAnonymously(); } catch(e) { fallbackMode(); } }

        auth.onAuthStateChanged(async (u) => {
            if (u) {
                currentUser = u;
                document.getElementById('auth-screen').classList.add('hidden');
                document.getElementById('main-app').classList.remove('hidden');
                await loadSettings();
                loadProfile(u.uid);
            }
        });

        async function loadSettings() {
            try {
                const doc = await db.collection('settings').doc('global').get();
                if(doc.exists) {
                    const d = doc.data();
                    if(d.gameDuration) SETTINGS.gameDuration=d.gameDuration;
                    if(d.gameReward) SETTINGS.gameReward=d.gameReward;
                    if(d.referralBonus) SETTINGS.referBonus=d.referralBonus;
                    if(d.watchAdReward) SETTINGS.watchAdReward=d.watchAdReward;
                    if(d.watchAdDelay) SETTINGS.watchAdDelay=d.watchAdDelay;
                    if(d.coinValue) SETTINGS.coinValue=d.coinValue;
                    if(d.socials) SETTINGS.socials=d.socials;
                    if(d.paymentMethods) SETTINGS.paymentMethods=d.paymentMethods;
                }
                updateUI();
            } catch(e) { console.log("Settings error"); }
        }

        function updateUI() {
            document.getElementById('game-time-disp').innerText = SETTINGS.gameDuration;
            document.getElementById('ad-reward-disp').innerText = SETTINGS.watchAdReward;
            document.getElementById('refer-bonus-disp').innerText = SETTINGS.referBonus;
            document.getElementById('val-disp').innerText = SETTINGS.coinValue;

            const sc = document.getElementById('social-links-container');
            sc.innerHTML = '';
            if(SETTINGS.socials) {
                sc.classList.remove('hidden');
                const s = SETTINGS.socials;
                if(s.telegram) sc.innerHTML += `<a href="${s.telegram}" target="_blank" class="w-10 h-10 bg-blue-500 rounded-full flex items-center justify-center text-white"><i class="fab fa-telegram"></i></a>`;
                if(s.youtube) sc.innerHTML += `<a href="${s.youtube}" target="_blank" class="w-10 h-10 bg-red-600 rounded-full flex items-center justify-center text-white"><i class="fab fa-youtube"></i></a>`;
                if(s.instagram) sc.innerHTML += `<a href="${s.instagram}" target="_blank" class="w-10 h-10 bg-pink-600 rounded-full flex items-center justify-center text-white"><i class="fab fa-instagram"></i></a>`;
            }

            const ps = document.getElementById('withdraw-method');
            ps.innerHTML = '';
            SETTINGS.paymentMethods.forEach(m => {
                const o = document.createElement('option'); o.value=m; o.innerText=m; ps.appendChild(o);
            });
        }

        async function loadProfile(uid) {
            const ref = db.collection('users').doc(uid);
            try {
                const doc = await ref.get();
                if(!doc.exists) {
                    const code = 'REF'+Math.floor(1000+Math.random()*9000);
                    await ref.set({uid, balance:0, referralCode:code, totalEarned:0, totalRefers:0, referredBy:null});
                    userData={balance:0, referralCode:code};
                } else userData=doc.data();
                updateHeader();
                listenData();
                loadGames();
                loadHistory();
            } catch(e) { fallbackMode(); }
        }

        function listenData() {
            db.collection('users').doc(currentUser.uid)
            .onSnapshot(d=>{ if(d.exists) { userData=d.data(); updateHeader(); }});
        }

        function updateHeader() {
            if(!userData) return;
            document.getElementById('header-balance').innerText=userData.balance;
            document.getElementById('wallet-balance').innerText=userData.balance;
            document.getElementById('total-earned-display').innerText=userData.totalEarned||0;
            document.getElementById('total-refers-display').innerText=userData.totalRefers||0;
            document.getElementById('my-ref-code').innerText=userData.referralCode||'...';
        }

        function showPage(id) {
            document.querySelectorAll('.page-section').forEach(e=>e.classList.add('hidden'));
            document.getElementById(id).classList.remove('hidden');
            document.querySelectorAll('.nav-item').forEach(e=>e.classList.remove('active'));
            if(id.includes('home')) document.getElementById('nav-home').classList.add('active');
            if(id.includes('refer')) document.getElementById('nav-refer').classList.add('active');
            if(id.includes('wallet')) document.getElementById('nav-wallet').classList.add('active');
            if(id.includes('history')) document.getElementById('nav-history').classList.add('active');
        }

        // --- WATCH & EARN (With Cooldown) ---
        function triggerWatchEarn() {
            const now = Date.now();
            const elapsed = (now - lastAdWatchTime) / 1000;
            const cooldown = SETTINGS.watchAdDelay;

            if (elapsed < cooldown) {
                const left = Math.ceil(cooldown - elapsed);
                showToast(`Wait ${left}s before next ad`, "error");
                return;
            }

            showGigaAd(async () => {
                await addCoins(SETTINGS.watchAdReward);
                lastAdWatchTime = Date.now();
                startCooldownTimer(cooldown);
            });
        }


        function startCooldownTimer(seconds) {
            let left = seconds;
            const card = document.getElementById('watch-earn-card');
            const timerMsg = document.getElementById('ad-timer-msg');
            const timerSpan = document.getElementById('ad-cooldown-timer');
            
            card.classList.add('disabled-card');
            timerMsg.classList.remove('hidden');
            timerSpan.innerText = left;

            const interval = setInterval(() => {
                left--;
                if (left <= 0) {
                    clearInterval(interval);
                    card.classList.remove('disabled-card');
                    timerMsg.classList.add('hidden');
                } else {
                    timerSpan.innerText = left;
                }
            }, 1000);
        }

        function showGigaAd(callback) {
            if (window.Adsgram && window.Adsgram.init) {
                try {
                    const AdController = window.Adsgram.init({ blockId: "int-7078" });
                    AdController.show().then((result) => {
                        callback();
                    }).catch((result) => {
                        showModalAd(callback);
                    });
                } catch(e) {
                    showModalAd(callback);
                }
            } else {
                showModalAd(callback);
            }
        }

        function showModalAd(callback) {
            const modal = document.getElementById('ad-modal');
            const timerSpan = document.getElementById('ad-timer');
            modal.classList.remove('hidden');
            let time = 5;
            timerSpan.innerText = time + 's';

            const interval = setInterval(() => {
                time--;
                if (time <= 0) {
                    clearInterval(interval);
                    modal.classList.add('hidden');
                    callback();
                } else {
                    timerSpan.innerText = time + 's';
                }
            }, 1000);
        }

        async function addCoins(amount, desc = "Earned Reward") {
            if (!userData) userData = { balance: 0, totalEarned: 0, totalRefers: 0 };
            userData.balance = (userData.balance || 0) + amount;
            if (amount > 0) {
                userData.totalEarned = (userData.totalEarned || 0) + amount;
            }
            updateHeader();

            // Save history
            const tx = {
                title: desc,
                amount: amount > 0 ? `+${amount}` : `${amount}`,
                date: new Date().toLocaleDateString() + ' ' + new Date().toLocaleTimeString([], {hour: '2-digit', minute:'2-digit'}),
                type: amount > 0 ? 'credit' : 'debit'
            };

            // Save to local storage
            try {
                localStorage.setItem('gtz_user_data', JSON.stringify(userData));
                let localTx = JSON.parse(localStorage.getItem('gtz_tx_history') || '[]');
                localTx.unshift(tx);
                localStorage.setItem('gtz_tx_history', JSON.stringify(localTx));
            } catch(e) {}

            // Save to Firebase if active
            if (currentUser && !currentUser.isFallback) {
                try {
                    await db.collection('users').doc(currentUser.uid).update({
                        balance: userData.balance,
                        totalEarned: userData.totalEarned
                    });
                    await db.collection('users').doc(currentUser.uid).collection('history').add(tx);
                } catch(e) {}
            }
            showToast(`+${amount} Coins Added!`, "success");
            loadHistory();
        }

        function loadGames() {
            const gamesList = document.getElementById('games-list');
            const games = [
                { title: "2048 Puzzle", img: "https://images.unsplash.com/photo-1611996575749-79a3a250f948?w=300&q=80", url: "https://play2048.co/" },
                { title: "Hextris", img: "https://images.unsplash.com/photo-1550745165-9bc0b252726f?w=300&q=80", url: "https://hextris.io/" },
                { title: "Flappy Bird", img: "https://images.unsplash.com/photo-1511512578047-dfb367046420?w=300&q=80", url: "https://flappybird.io/" },
                { title: "Tower Building", img: "https://images.unsplash.com/photo-1538481199705-c710c4e965fc?w=300&q=80", url: "https://www.towergame.app/" }
            ];

            gamesList.innerHTML = '';
            games.forEach(g => {
                gamesList.innerHTML += `
                    <div class="bg-slate-800 rounded-xl overflow-hidden border border-slate-700 shadow-lg flex flex-col justify-between">
                        <div class="h-28 bg-slate-700 relative overflow-hidden">
                            <img src="${g.img}" class="w-full h-full object-cover">
                            <div class="absolute inset-0 bg-gradient-to-t from-slate-900 to-transparent"></div>
                        </div>
                        <div class="p-3 text-center">
                            <h4 class="font-bold text-sm text-white mb-2 truncate">${g.title}</h4>
                            <button onclick="playGame('${g.url}', '${g.title}')" class="w-full bg-gradient-to-r from-orange-500 to-red-600 hover:from-orange-600 hover:to-red-700 text-white text-xs font-bold py-2 rounded-lg shadow transition">
                                <i class="fas fa-play mr-1"></i> PLAY NOW
                            </button>
                        </div>
                    </div>
                `;
            });
        }

        let currentGameInterval = null;
        function playGame(url, title) {
            document.getElementById('game-iframe').src = url;
            document.getElementById('play-overlay').classList.remove('hidden');
            document.getElementById('top-claim-container').classList.add('hidden');
            
            let timeLeft = SETTINGS.gameDuration || 60;
            const timerEl = document.getElementById('game-timer');
            timerEl.innerText = `00:${timeLeft < 10 ? '0'+timeLeft : timeLeft}`;

            if (currentGameInterval) clearInterval(currentGameInterval);
            currentGameInterval = setInterval(() => {
                timeLeft--;
                if (timeLeft <= 0) {
                    clearInterval(currentGameInterval);
                    timerEl.innerText = "00:00";
                    document.getElementById('top-claim-container').classList.remove('hidden');
                } else {
                    timerEl.innerText = `00:${timeLeft < 10 ? '0'+timeLeft : timeLeft}`;
                }
            }, 1000);
        }

        async function triggerClaimReward() {
            await addCoins(SETTINGS.gameReward || 50, "Game Played Reward");
            exitGame();
        }

        function exitGame() {
            if (currentGameInterval) clearInterval(currentGameInterval);
            document.getElementById('play-overlay').classList.add('hidden');
            document.getElementById('game-iframe').src = "";
            document.getElementById('top-claim-container').classList.add('hidden');
        }

        async function loadHistory() {
            const txContainer = document.getElementById('tx-history');
            let historyList = [];

            if (currentUser && !currentUser.isFallback) {
                try {
                    const snap = await db.collection('users').doc(currentUser.uid).collection('history').orderBy('date', 'desc').limit(20).get();
                    historyList = snap.docs.map(d => d.data());
                } catch(e) {}
            }

            if (historyList.length === 0) {
                try {
                    historyList = JSON.parse(localStorage.getItem('gtz_tx_history') || '[]');
                } catch(e) {}
            }

            if (historyList.length === 0) {
                txContainer.innerHTML = `<p class="text-center text-slate-500 text-sm py-10">No transactions yet.</p>`;
                return;
            }

            txContainer.innerHTML = '';
            historyList.forEach(tx => {
                const isCredit = tx.type === 'credit' || (tx.amount && tx.amount.toString().includes('+'));
                txContainer.innerHTML += `
                    <div class="bg-slate-800 p-3 rounded-xl border border-slate-700 flex justify-between items-center">
                        <div>
                            <p class="font-bold text-sm text-white">${tx.title || 'Reward'}</p>
                            <p class="text-[10px] text-slate-400">${tx.date || ''}</p>
                        </div>
                        <span class="font-bold text-sm ${isCredit ? 'text-green-400' : 'text-red-400'}">${tx.amount}</span>
                    </div>
                `;
            });
        }

        function copyRefCode() {
            const code = document.getElementById('my-ref-code').innerText;
            if (!code || code === '...') return;
            navigator.clipboard.writeText(code);
            showToast("Referral code copied!", "success");
        }

        async function redeemReferral() {
            const input = document.getElementById('input-ref-code');
            const code = input.value.trim().toUpperCase();
            if (!code) {
                showToast("Please enter a referral code", "error");
                return;
            }
            if (userData && userData.referralCode === code) {
                showToast("Cannot use your own referral code!", "error");
                return;
            }
            if (localStorage.getItem('gtz_refer_used')) {
                showToast("You have already applied a referral code!", "error");
                return;
            }

            await addCoins(SETTINGS.referBonus || 500, "Referral Bonus");
            localStorage.setItem('gtz_refer_used', 'true');
            input.value = '';
            showToast("Referral applied successfully!", "success");
        }

        function handleWithdraw(e) {
            e.preventDefault();
            const method = document.getElementById('withdraw-method').value;
            const details = document.getElementById('withdraw-details').value;
            const amount = parseInt(document.getElementById('withdraw-amount').value);

            if (!userData || userData.balance < amount) {
                showToast("Insufficient coin balance!", "error");
                return;
            }

            addCoins(-amount, `Withdrawal to ${method} (${details})`);
            document.getElementById('withdraw-details').value = '';
            document.getElementById('withdraw-amount').value = '';
            showToast("Withdrawal request submitted successfully!", "success");
        }

        function fallbackMode() {
            let savedUid = localStorage.getItem('gtz_uid');
            if (!savedUid) {
                savedUid = 'user_' + Math.floor(100000 + Math.random() * 900000);
                localStorage.setItem('gtz_uid', savedUid);
            }
            currentUser = { uid: savedUid, isFallback: true };

            let savedData = null;
            try {
                savedData = JSON.parse(localStorage.getItem('gtz_user_data'));
            } catch(e) {}

            if (savedData) {
                userData = savedData;
            } else {
                userData = {
                    balance: 100,
                    referralCode: 'REF' + Math.floor(1000 + Math.random() * 9000),
                    totalEarned: 100,
                    totalRefers: 0
                };
                localStorage.setItem('gtz_user_data', JSON.stringify(userData));
            }

            document.getElementById('auth-screen').classList.add('hidden');
            document.getElementById('main-app').classList.remove('hidden');

            updateUI();
            updateHeader();
            loadGames();
            loadHistory();
        }

        function showToast(msg, type = "info") {
            const container = document.getElementById('toast-container');
            const toast = document.createElement('div');
            toast.className = `toast ${type === 'error' ? '!border-red-500' : type === 'success' ? '!border-green-500' : ''}`;
            toast.innerHTML = `<span class="font-bold text-sm text-white">${msg}</span>`;
            container.appendChild(toast);

            setTimeout(() => { toast.style.opacity = '1'; }, 10);
            setTimeout(() => {
                toast.style.opacity = '0';
                setTimeout(() => { toast.remove(); }, 300);
            }, 3000);
        }
    </script>
</body>
</html>
