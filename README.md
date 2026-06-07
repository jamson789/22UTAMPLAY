<html lang="sw">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UtamPlay Video App - Admin Panel</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            color: #ffffff;
            line-height: 1.6;
            min-height: 100vh;
        }
        
        /* Dark Theme */
        body.dark-theme {
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
        }
        
        header {
            background: rgba(0, 0, 0, 0.95);
            padding: 25px 20px;
            text-align: center;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #ff6b6b, #ff0000, #ff6b6b);
            animation: slide 2s infinite;
        }
        
        @keyframes slide {
            0% { background-position: -100% 0; }
            100% { background-position: 200% 0; }
        }
        
        h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            color: #ff0000;
            text-shadow: 0 0 20px rgba(255, 0, 0, 0.5);
            font-weight: 900;
            letter-spacing: 2px;
            text-transform: uppercase;
            animation: glow 2s ease-in-out infinite alternate;
        }
        
        @keyframes glow {
            from { text-shadow: 0 0 10px red; }
            to { text-shadow: 0 0 30px red, 0 0 10px darkred; }
        }
        
        .container {
            max-width: 1200px;
            margin: 30px auto;
            padding: 0 20px;
        }
        
        /* Admin Button */
        .admin-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #000;
            border: 2px solid #ff0000;
            color: #ff0000;
            padding: 12px 20px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            z-index: 1000;
            transition: all 0.3s ease;
            box-shadow: 0 0 15px rgba(255,0,0,0.3);
        }
        
        .admin-btn:hover {
            background: #ff0000;
            color: #000;
            transform: scale(1.05);
            box-shadow: 0 0 25px rgba(255,0,0,0.6);
        }
        
        /* Admin Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.95);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            animation: fadeIn 0.3s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .modal-content {
            background: #111;
            border: 2px solid #ff0000;
            border-radius: 20px;
            padding: 30px;
            max-width: 500px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
            box-shadow: 0 0 50px rgba(255,0,0,0.3);
        }
        
        .modal-content h2 {
            color: #ff0000;
            margin-bottom: 20px;
            text-align: center;
        }
        
        .modal-content input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            background: #222;
            border: 1px solid #ff0000;
            color: white;
            border-radius: 10px;
            font-size: 16px;
        }
        
        .modal-content button {
            width: 100%;
            padding: 12px;
            background: #ff0000;
            color: black;
            border: none;
            border-radius: 10px;
            font-weight: bold;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s;
        }
        
        .modal-content button:hover {
            background: #ff4444;
            transform: scale(1.02);
        }
        
        .log-list {
            margin-top: 20px;
        }
        
        .log-item {
            background: #1a1a1a;
            padding: 10px;
            margin: 8px 0;
            border-left: 3px solid #ff0000;
            font-size: 14px;
            border-radius: 5px;
        }
        
        .close-modal {
            float: right;
            font-size: 28px;
            cursor: pointer;
            color: #ff0000;
        }
        
        /* Video Grid */
        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }
        
        .video-card {
            background: rgba(20, 20, 20, 0.95);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(255, 50, 50, 0.3);
        }
        
        .video-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(255, 0, 0, 0.3);
        }
        
        .video-header {
            padding: 15px 20px;
            background: rgba(30, 30, 30, 0.95);
            border-bottom: 1px solid #ff0000;
        }
        
        .video-header h2 {
            font-size: 1.4rem;
            color: #ff4444;
            margin: 0;
        }
        
        .video-container {
            position: relative;
            padding-top: 56.25%;
            height: 0;
            overflow: hidden;
        }
        
        .video-container video {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }
        
        .video-footer {
            padding: 15px 20px;
            text-align: center;
        }
        
        footer {
            background: #0a0a0a;
            padding: 25px 20px;
            text-align: center;
            margin-top: 50px;
            border-top: 1px solid #ff0000;
        }
        
        .app-name {
            font-size: 2.2rem;
            margin-bottom: 10px;
            color: #ff0000;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .copyright {
            opacity: 0.8;
            font-size: 0.9rem;
        }
        
        /* Stats Bar */
        .stats-bar {
            background: #111;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            text-align: center;
            border: 1px solid #ff0000;
        }
        
        .stats-bar span {
            color: #ff0000;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        @media (max-width: 768px) {
            .video-grid {
                grid-template-columns: 1fr;
            }
            h1 {
                font-size: 2.5rem;
            }
        }
        
        /* Animations */
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="dark-theme">
    <header>
        <h1 class="pulse">22utamplay</h1>
        <p class="tagline"></p>
    </header>
    
    <div class="container">
        <div class="stats-bar">
            📊 <span id="viewCount">0</span> watazamaji wameangalia video
        </div>
        
        <div class="video-grid" id="videoGrid">
            <!-- Video 1 -->
            <div class="video-card" data-video-id="1" data-video-name="Mtam1">
                <div class="video-header">
                    <h2>Video 1 - Mtam1</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/333333/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn71.xcdn1.me/m/1fc826149688a3b2be7412ecfa47eb60videoN2E1ZDlhMzIwZmFjNmU5MzYwZjU1OTQzNjQ5NTZiZjUubXA0.mp4" type="video/mp4">
                    </video>
                </div>
                <div class="video-footer">
                    <!-- Bonyeza Hapa imeondolewa kabisa -->
                </div>
            </div>
            
            <!-- Video 2 -->
            <div class="video-card" data-video-id="2" data-video-name="utam2">
                <div class="video-header">
                    <h2>Video 2 - utam2</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/333333/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn60.xcdn1.me/m/68f8d6724333b76eb6524752ef027f70videoNTZhOTNmNTBlYTZjOGY5MTJkZjhkMTRmYjk1NjMxZWEubXA0.mp4" type="video/mp4">
                    </video>
                </div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 3 hadi 11 zimefupishwa kwa ajili ya nafasi, lakini zote zina muundo sawa -->
            <div class="video-card" data-video-id="3" data-video-name="utam3">
                <div class="video-header"><h2>Video 3 - utam3</h2></div>
                <div class="video-container"><video controls><source src="https://cdn60.xcdn1.me/d/b1bfde439c7869796b66bd30af6a7341videoNWIzYzY4MzBmMGQ1OGUzMWE2N2M0MTRhYzczNDQ4NGIubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            <div class="video-card" data-video-id="4" data-video-name="utam4">
                <div class="video-header"><h2>Video 4 - utam4</h2></div>
                <div class="video-container"><video controls><source src="https://cdn60.xcdn1.me/m/67ebc9207bd840839c3cf147036b7986videoOTI1N2NlNmYxZDMxMTE3ZGI3ODk5NTZiMDFjMWU1NGQubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            <div class="video-card" data-video-id="5" data-video-name="utam5">
                <div class="video-header"><h2>Video 5 - utam5</h2></div>
                <div class="video-container"><video controls><source src="https://cdn41.xcdn1.me/m/8d280585381f445c62c9ca462fd83ef0videoZjJkOWFiNmU3YzQ0MmI0MWUxMDk5YjQxNTQyOTM5MGMubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            <div class="video-card" data-video-id="6" data-video-name="utam6">
                <div class="video-header"><h2>Video 6 - utam6</h2></div>
                <div class="video-container"><video controls><source src="https://cdn101.xcdn1.me/m/52eaba3495e4c4a8477e418dfee66077videoMjVmYzFkOTI5NzU1MjhkNTg0ZDhjZWJjNWM0MzlhMTIubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            <div class="video-card" data-video-id="7" data-video-name="utam7">
                <div class="video-header"><h2>Video 7 - utam7</h2></div>
                <div class="video-container"><video controls><source src="https://cdn50.xcdn1.me/m/948312e62f159e8c1f9fbb800cfda540videoNDY1ODJkNDM4NGQ0YzBjM2E5ZmQ0ZjNkNzM4MTAxOTkubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            <div class="video-card" data-video-id="8" data-video-name="utam8">
                <div class="video-header"><h2>Video 8 - utam8</h2></div>
                <div class="video-container"><video controls><source src="https://cdn71.xcdn1.me/m/1c947c7a2a5b8222e17a9635530d9583videoOWUyNDJjODExMmQ1MDkwYzg5MzAwYTEyMGU4ODhmMzkubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            <div class="video-card" data-video-id="9" data-video-name="utam9">
                <div class="video-header"><h2>Video 9 - utam9</h2></div>
                <div class="video-container"><video controls><source src="https://cdn50.xcdn1.me/m/0a8b9c0297cb7f8e1b2010b453539541videoMjFmN2IwMjRhYmVkZTI4MTU1NGJhZDhlZTQ3Zjk1YjUubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            <div class="video-card" data-video-id="10" data-video-name="utam10">
                <div class="video-header"><h2>Video 10 - utam10</h2></div>
                <div class="video-container"><video controls><source src="https://cdn50.xcdn1.me/m/0b690e7be4eb45432a76498d4fc72001videoNjlmM2JmNDBhZjA5OTI3NWY0NmY2ODczNzc0Nzk2MDMubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            <div class="video-card" data-video-id="11" data-video-name="utam11">
                <div class="video-header"><h2>Video 11 - utam11</h2></div>
                <div class="video-container"><video controls><source src="https://cdn72.xcdn1.me/m/0c6fb61a6fd4e9d1d4eae74bd9faa7bavideoYjBhMTcyZDQyNTIzMWZkOTljNTBhZGExYzk2N2Q5Y2UubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
        </div>
    </div>
    
    <!-- Admin Button -->
    <div class="admin-btn" id="adminBtn">🔐 ADMIN PANEL</div>
    
    <!-- Admin Login Modal -->
    <div id="adminModal" class="modal">
        <div class="modal-content">
            <span class="close-modal" id="closeModal">&times;</span>
            <h2>🔑 ADMIN LOGIN</h2>
            <input type="password" id="adminPassword" placeholder="Weka password ya Admin">
            <button id="loginBtn">Ingia</button>
            <div id="loginError" style="color: red; margin-top: 10px; text-align: center;"></div>
        </div>
    </div>
    
    <!-- Admin Dashboard Modal -->
    <div id="dashboardModal" class="modal">
        <div class="modal-content" style="max-width: 700px;">
            <span class="close-modal" id="closeDashboard">&times;</span>
            <h2>📋 ADMIN DASHBOARD</h2>
            <div style="background: #1a1a1a; padding: 10px; border-radius: 10px; margin: 10px 0;">
                <p>🔐 Nguvu: <strong style="color: #00ff00;">IMEINGIA</strong></p>
                <p>📊 Jumla ya watazamaji: <strong id="dashboardTotalViews" style="color: #ff0000;">0</strong></p>
            </div>
            <div id="adminLogs" class="log-list">
                <!-- Logs zitaonekana hapa -->
            </div>
            <button id="clearLogsBtn" style="background: #333; margin-top: 15px;">Futa Historia</button>
            <button id="logoutBtn" style="background: #ff0000; margin-top: 10px;">Toka (Logout)</button>
        </div>
    </div>
    
    <footer>
        <div class="footer-content">
            <div class="app-name">UTAMPLAY</div>
            <p class="copyright">©2025 UtamPlay | Admin Panel Imewekwa</p>
        </div>
    </footer>
    
    <script>
        // ADMIN PASSWORD - Badilisha hapa password unayotaka
        const ADMIN_PASSWORD = "admin123";
        
        // Hifadhi ya watazamaji
        let viewerLogs = [];
        
        // Load logs from localStorage
        function loadLogs() {
            const saved = localStorage.getItem('utamplay_viewer_logs');
            if(saved) {
                viewerLogs = JSON.parse(saved);
            }
            updateViewCount();
        }
        
        // Save logs to localStorage
        function saveLogs() {
            localStorage.setItem('utamplay_viewer_logs', JSON.stringify(viewerLogs));
            updateViewCount();
        }
        
        // Update view count display
        function updateViewCount() {
            const uniqueViewers = new Set();
            viewerLogs.forEach(log => {
                if(log.viewerId) uniqueViewers.add(log.viewerId);
            });
            document.getElementById('viewCount').innerText = uniqueViewers.size;
            const dashboardTotal = document.getElementById('dashboardTotalViews');
            if(dashboardTotal) dashboardTotal.innerText = uniqueViewers.size;
        }
        
        // Generate or get viewer ID
        function getViewerId() {
            let viewerId = localStorage.getItem('utamplay_viewer_id');
            if(!viewerId) {
                viewerId = 'viewer_' + Date.now() + '_' + Math.random().toString(36).substr(2, 8);
                localStorage.setItem('utamplay_viewer_id', viewerId);
            }
            return viewerId;
        }
        
        // Log video view
        function logVideoView(videoId, videoName) {
            const viewerId = getViewerId();
            const timestamp = new Date().toLocaleString('sw-TZ', {timeZone: 'Africa/Dar_es_Salaam'});
            
            viewerLogs.push({
                id: Date.now(),
                viewerId: viewerId,
                videoId: videoId,
                videoName: videoName,
                timestamp: timestamp,
                ip: "LocalStorage Mode" // Kwa demo, unaweza kubadilisha kuwa ip real kwa backend
            });
            
            saveLogs();
        }
        
        // Track video play events
        function setupVideoTracking() {
            const videos = document.querySelectorAll('.video-card video');
            videos.forEach((video, index) => {
                const card = video.closest('.video-card');
                const videoId = card ? card.getAttribute('data-video-id') : index+1;
                const videoName = card ? card.getAttribute('data-video-name') : `Video ${index+1}`;
                let hasLogged = false;
                
                video.addEventListener('play', () => {
                    if(!hasLogged) {
                        logVideoView(videoId, videoName);
                        hasLogged = true;
                        console.log(`✅ Imerekodi: ${videoName} imechezwa`);
                        // Animation effect kwenye card
                        card.style.boxShadow = '0 0 20px rgba(255,0,0,0.8)';
                        setTimeout(() => {
                            card.style.boxShadow = '';
                        }, 1000);
                    }
                });
            });
        }
        
        // Admin Panel Functions
        let isAdminLoggedIn = false;
        
        function showAdminLogin() {
            document.getElementById('adminModal').style.display = 'flex';
            document.getElementById('adminPassword').value = '';
            document.getElementById('loginError').innerText = '';
        }
        
        function closeAdminLogin() {
            document.getElementById('adminModal').style.display = 'none';
        }
        
        function showAdminDashboard() {
            if(!isAdminLoggedIn) {
                showAdminLogin();
                return;
            }
            
            // Update dashboard logs
            const logsContainer = document.getElementById('adminLogs');
            if(viewerLogs.length === 0) {
                logsContainer.innerHTML = '<div class="log-item">📭 Hakuna rekodi bado. Mtu aanze kuangalia video.</div>';
            } else {
                logsContainer.innerHTML = viewerLogs.slice().reverse().map(log => `
                    <div class="log-item">
                        🎬 <strong>${log.videoName}</strong> (ID: ${log.videoId})<br>
                        👤 ${log.viewerId}<br>
                        🕐 ${log.timestamp}
                    </div>
                `).join('');
            }
            
            updateViewCount();
            document.getElementById('dashboardModal').style.display = 'flex';
        }
        
        function closeDashboard() {
            document.getElementById('dashboardModal').style.display = 'none';
        }
        
        function logoutAdmin() {
            isAdminLoggedIn = false;
            closeDashboard();
            alert('Umetoka kwenye Admin Panel.');
        }
        
        function clearLogs() {
            if(confirm('Una uhakika unataka kufuta rekodi zote za watazamaji?')) {
                viewerLogs = [];
                saveLogs();
                if(document.getElementById('dashboardModal').style.display === 'flex') {
                    showAdminDashboard();
                }
                alert('Rekodi zimefutika.');
            }
        }
        
        // Event Listeners for Admin
        document.getElementById('adminBtn').addEventListener('click', () => {
            if(isAdminLoggedIn) {
                showAdminDashboard();
            } else {
                showAdminLogin();
            }
        });
        
        document.getElementById('closeModal').addEventListener('click', closeAdminLogin);
        document.getElementById('closeDashboard').addEventListener('click', closeDashboard);
        
        document.getElementById('loginBtn').addEventListener('click', () => {
            const password = document.getElementById('adminPassword').value;
            if(password === ADMIN_PASSWORD) {
                isAdminLoggedIn = true;
                closeAdminLogin();
                showAdminDashboard();
            } else {
                document.getElementById('loginError').innerText = '❌ Password si sahihi! Jaribu tena.';
            }
        });
        
        document.getElementById('logoutBtn').addEventListener('click', logoutAdmin);
        document.getElementById('clearLogsBtn').addEventListener('click', clearLogs);
        
        // Close modals when clicking outside
        window.addEventListener('click', (e) => {
            if(e.target === document.getElementById('adminModal')) closeAdminLogin();
            if(e.target === document.getElementById('dashboardModal')) closeDashboard();
        });
        
        // Enter key for password
        document.getElementById('adminPassword').addEventListener('keypress', (e) => {
            if(e.key === 'Enter') document.getElementById('loginBtn').click();
        });
        
        // Initialize
        loadLogs();
        setupVideoTracking();
        
        // Animation for video cards
        document.addEventListener('DOMContentLoaded', function() {
            const videoCards = document.querySelectorAll('.video-card');
            videoCards.forEach((card, index) => {
                setTimeout(() => {
                    card.style.opacity = '0';
                    card.style.transform = 'translateY(20px)';
                    card.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                    setTimeout(() => {
                        card.style.opacity = '1';
                        card.style.transform = 'translateY(0)';
                    }, 100);
                }, index * 100);
            });
            
            // Glow effect header
            const header = document.querySelector('header');
            header.style.boxShadow = '0 4px 30px rgba(255, 0, 0, 0.7)';
            setTimeout(() => {
                header.style.boxShadow = '0 4px 20px rgba(0, 0, 0, 0.5)';
            }, 2000);
        });
    </script>
</body>
</html>
