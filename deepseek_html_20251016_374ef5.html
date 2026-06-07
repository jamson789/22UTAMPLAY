<html lang="sw">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UtamPlay - Video App na Admin Panel</title>
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
        
        /* Header */
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
        
        .tagline {
            color: #aaa;
        }
        
        .container {
            max-width: 1200px;
            margin: 30px auto;
            padding: 0 20px;
        }
        
        /* Admin Button - Anayeonekana kwa wote, ila admin ndo anayejua password */
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
        
        /* ADMIN DASHBOARD PANEL - Inaonekana tu admin akiingia */
        .admin-dashboard {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.98);
            z-index: 2000;
            overflow-y: auto;
            animation: fadeIn 0.3s ease;
        }
        
        .admin-dashboard.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .dashboard-header {
            background: #000;
            padding: 20px 30px;
            border-bottom: 3px solid #ff0000;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            position: sticky;
            top: 0;
            z-index: 10;
        }
        
        .dashboard-header h2 {
            color: #ff0000;
            font-size: 1.5rem;
        }
        
        .close-dashboard {
            background: #ff0000;
            color: #000;
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
        }
        
        .dashboard-container {
            max-width: 1400px;
            margin: 30px auto;
            padding: 0 20px;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .stat-card {
            background: #111;
            border: 1px solid #ff0000;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
        }
        
        .stat-card .number {
            font-size: 2rem;
            font-weight: bold;
            color: #ff0000;
        }
        
        .video-stats-table {
            background: #111;
            border-radius: 15px;
            overflow-x: auto;
            margin-bottom: 30px;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        th, td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #333;
        }
        
        th {
            background: #1a1a1a;
            color: #ff0000;
        }
        
        .logs-container {
            background: #111;
            border-radius: 15px;
            padding: 20px;
            max-height: 400px;
            overflow-y: auto;
        }
        
        .log-item {
            background: #1a1a1a;
            padding: 10px;
            margin: 8px 0;
            border-left: 3px solid #ff0000;
            border-radius: 5px;
            font-size: 13px;
        }
        
        .action-buttons {
            display: flex;
            gap: 15px;
            margin: 20px 0;
            flex-wrap: wrap;
        }
        
        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
        }
        
        .btn-danger {
            background: #8b0000;
            color: white;
        }
        
        .btn-warning {
            background: #333;
            color: #ff0000;
            border: 1px solid #ff0000;
        }
        
        /* Login Modal ndani ya dashboard */
        .login-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.95);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
        }
        
        .login-box {
            background: #111;
            border: 2px solid #ff0000;
            border-radius: 20px;
            padding: 40px;
            width: 350px;
            text-align: center;
        }
        
        .login-box input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            background: #222;
            border: 1px solid #ff0000;
            color: white;
            border-radius: 8px;
        }
        
        .login-box button {
            width: 100%;
            padding: 12px;
            background: #ff0000;
            color: #000;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
        }
        
        @media (max-width: 768px) {
            .video-grid {
                grid-template-columns: 1fr;
            }
            h1 {
                font-size: 2.5rem;
            }
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
    </style>
</head>
<body>
    <header>
        <h1 class="pulse">22utamplay</h1>
        <p class="tagline">Angalia video za kipekee - Admin bonyeza kitufe chini kulia</p>
    </header>
    
    <div class="container">
        <div class="stats-bar">
            📊 <span id="viewCount">0</span> watazamaji wameangalia video
        </div>
        
        <div class="video-grid" id="videoGrid">
            <!-- Video 1 - Kila video ina KAVA LAKE TOFAUTI -->
            <div class="video-card" data-video-id="1" data-video-name="Mtam1">
                <div class="video-header">
                    <h2>🎬 Video 1 - Mtam1</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://picsum.photos/id/100/400/300">
                        <source src="https://cdn71.xcdn1.me/m/1fc826149688a3b2be7412ecfa47eb60videoN2E1ZDlhMzIwZmFjNmU5MzYwZjU1OTQzNjQ5NTZiZjUubXA0.mp4" type="video/mp4">
                    </video>
                </div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 2 -->
            <div class="video-card" data-video-id="2" data-video-name="utam2">
                <div class="video-header"><h2>🎬 Video 2 - utam2</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/101/400/300"><source src="https://cdn60.xcdn1.me/m/68f8d6724333b76eb6524752ef027f70videoNTZhOTNmNTBlYTZjOGY5MTJkZjhkMTRmYjk1NjMxZWEubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 3 -->
            <div class="video-card" data-video-id="3" data-video-name="utam3">
                <div class="video-header"><h2>🎬 Video 3 - utam3</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/102/400/300"><source src="https://cdn60.xcdn1.me/d/b1bfde439c7869796b66bd30af6a7341videoNWIzYzY4MzBmMGQ1OGUzMWE2N2M0MTRhYzczNDQ4NGIubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 4 -->
            <div class="video-card" data-video-id="4" data-video-name="utam4">
                <div class="video-header"><h2>🎬 Video 4 - utam4</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/103/400/300"><source src="https://cdn60.xcdn1.me/m/67ebc9207bd840839c3cf147036b7986videoOTI1N2NlNmYxZDMxMTE3ZGI3ODk5NTZiMDFjMWU1NGQubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 5 -->
            <div class="video-card" data-video-id="5" data-video-name="utam5">
                <div class="video-header"><h2>🎬 Video 5 - utam5</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/104/400/300"><source src="https://cdn41.xcdn1.me/m/8d280585381f445c62c9ca462fd83ef0videoZjJkOWFiNmU3YzQ0MmI0MWUxMDk5YjQxNTQyOTM5MGMubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 6 -->
            <div class="video-card" data-video-id="6" data-video-name="utam6">
                <div class="video-header"><h2>🎬 Video 6 - utam6</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/105/400/300"><source src="https://cdn101.xcdn1.me/m/52eaba3495e4c4a8477e418dfee66077videoMjVmYzFkOTI5NzU1MjhkNTg0ZDhjZWJjNWM0MzlhMTIubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 7 -->
            <div class="video-card" data-video-id="7" data-video-name="utam7">
                <div class="video-header"><h2>🎬 Video 7 - utam7</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/106/400/300"><source src="https://cdn50.xcdn1.me/m/948312e62f159e8c1f9fbb800cfda540videoNDY1ODJkNDM4NGQ0YzBjM2E5ZmQ0ZjNkNzM4MTAxOTkubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 8 -->
            <div class="video-card" data-video-id="8" data-video-name="utam8">
                <div class="video-header"><h2>🎬 Video 8 - utam8</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/107/400/300"><source src="https://cdn71.xcdn1.me/m/1c947c7a2a5b8222e17a9635530d9583videoOWUyNDJjODExMmQ1MDkwYzg5MzAwYTEyMGU4ODhmMzkubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 9 -->
            <div class="video-card" data-video-id="9" data-video-name="utam9">
                <div class="video-header"><h2>🎬 Video 9 - utam9</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/108/400/300"><source src="https://cdn50.xcdn1.me/m/0a8b9c0297cb7f8e1b2010b453539541videoMjFmN2IwMjRhYmVkZTI4MTU1NGJhZDhlZTQ3Zjk1YjUubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 10 -->
            <div class="video-card" data-video-id="10" data-video-name="utam10">
                <div class="video-header"><h2>🎬 Video 10 - utam10</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/109/400/300"><source src="https://cdn50.xcdn1.me/m/0b690e7be4eb45432a76498d4fc72001videoNjlmM2JmNDBhZjA5OTI3NWY0NmY2ODczNzc0Nzk2MDMubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
            
            <!-- Video 11 -->
            <div class="video-card" data-video-id="11" data-video-name="utam11">
                <div class="video-header"><h2>🎬 Video 11 - utam11</h2></div>
                <div class="video-container"><video controls poster="https://picsum.photos/id/110/400/300"><source src="https://cdn72.xcdn1.me/m/0c6fb61a6fd4e9d1d4eae74bd9faa7bavideoYjBhMTcyZDQyNTIzMWZkOTljNTBhZGExYzk2N2Q5Y2UubXA0.mp4" type="video/mp4"></video></div>
                <div class="video-footer"></div>
            </div>
        </div>
    </div>
    
    <!-- Admin Button - Kila mtu anaiona -->
    <button class="admin-btn" id="adminBtn">🔐 ADMIN PANEL</button>
    
    <!-- Admin Dashboard - Inaonekana tu admin akiingia ndani -->
    <div id="adminDashboard" class="admin-dashboard">
        <div class="dashboard-header">
            <h2>🔧 ADMIN DASHBOARD - UTAMPLAY</h2>
            <button class="close-dashboard" id="closeDashboardBtn">✖ FUNGA</button>
        </div>
        <div class="dashboard-container" id="dashboardContent">
            <!-- Content itajazwa na JavaScript -->
        </div>
    </div>
    
    <footer>
        <div class="footer-content">
            <div class="app-name">UTAMPLAY</div>
            <p class="copyright">©2025 UtamPlay | Kila video ina kava lake tofauti</p>
        </div>
    </footer>
    
    <script>
        // ==================== ADMIN PASSWORD ====================
        const ADMIN_PASSWORD = "admin123";
        
        // Admin login state
        let isAdminLoggedIn = false;
        
        // Get dashboard element
        const dashboard = document.getElementById('adminDashboard');
        
        // ==================== VIDEO TRACKING ====================
        let viewerLogs = [];
        
        function loadLogs() {
            const saved = localStorage.getItem('utamplay_viewer_logs');
            if(saved) {
                viewerLogs = JSON.parse(saved);
            }
            updateViewCount();
        }
        
        function saveLogs() {
            localStorage.setItem('utamplay_viewer_logs', JSON.stringify(viewerLogs));
            updateViewCount();
            if(isAdminLoggedIn && dashboard.classList.contains('active')) {
                renderDashboardContent();
            }
        }
        
        function updateViewCount() {
            const uniqueViewers = new Set();
            viewerLogs.forEach(log => {
                if(log.viewerId) uniqueViewers.add(log.viewerId);
            });
            const viewCountSpan = document.getElementById('viewCount');
            if(viewCountSpan) viewCountSpan.innerText = uniqueViewers.size;
        }
        
        function getViewerId() {
            let viewerId = localStorage.getItem('utamplay_viewer_id');
            if(!viewerId) {
                viewerId = 'viewer_' + Date.now() + '_' + Math.random().toString(36).substr(2, 8);
                localStorage.setItem('utamplay_viewer_id', viewerId);
            }
            return viewerId;
        }
        
        function logVideoView(videoId, videoName) {
            const viewerId = getViewerId();
            const timestamp = new Date().toLocaleString('sw-TZ', {timeZone: 'Africa/Dar_es_Salaam'});
            
            viewerLogs.push({
                id: Date.now(),
                viewerId: viewerId,
                videoId: videoId,
                videoName: videoName,
                timestamp: timestamp
            });
            
            saveLogs();
        }
        
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
                        if(card) {
                            card.style.boxShadow = '0 0 20px rgba(255,0,0,0.8)';
                            setTimeout(() => {
                                card.style.boxShadow = '';
                            }, 1000);
                        }
                    }
                });
            });
        }
        
        // ==================== DASHBOARD FUNCTIONS ====================
        function getUniqueViewersCount(logs) {
            const unique = new Set();
            logs.forEach(log => {
                if(log.viewerId) unique.add(log.viewerId);
            });
            return unique.size;
        }
        
        function getVideoStats(logs) {
            const stats = {};
            logs.forEach(log => {
                const key = log.videoId;
                if(!stats[key]) {
                    stats[key] = {
                        id: log.videoId,
                        name: log.videoName,
                        count: 0
                    };
                }
                stats[key].count++;
            });
            return Object.values(stats).sort((a,b) => b.count - a.count);
        }
        
        function clearAllLogs() {
            if(confirm('⚠️ UNA UHAKIKA? Hii itafuta rekodi ZOTE za watazamaji. Huwezi kurejesha!')) {
                saveViewerLogs([]);
                viewerLogs = [];
                saveLogs();
                if(isAdminLoggedIn && dashboard.classList.contains('active')) {
                    renderDashboardContent();
                }
                alert('✅ Rekodi zote zimefutika.');
            }
        }
        
        function saveViewerLogs(logs) {
            localStorage.setItem('utamplay_viewer_logs', JSON.stringify(logs));
        }
        
        function exportLogs() {
            const logs = viewerLogs;
            const dataStr = JSON.stringify(logs, null, 2);
            const dataBlob = new Blob([dataStr], {type: 'application/json'});
            const url = URL.createObjectURL(dataBlob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `utamplay_logs_${new Date().toISOString().slice(0,19)}.json`;
            a.click();
            URL.revokeObjectURL(url);
        }
        
        function renderDashboardContent() {
            const logs = viewerLogs;
            const uniqueViewers = getUniqueViewersCount(logs);
            const totalPlays = logs.length;
            const videoStats = getVideoStats(logs);
            
            const today = new Date().toLocaleDateString('sw-TZ');
            const todayLogs = logs.filter(log => {
                const logDate = new Date(log.timestamp).toLocaleDateString('sw-TZ');
                return logDate === today;
            });
            
            const content = `
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="number">${uniqueViewers}</div>
                        <div>Watazamaji Wapekee</div>
                    </div>
                    <div class="stat-card">
                        <div class="number">${totalPlays}</div>
                        <div>Uchezaji Jumla</div>
                    </div>
                    <div class="stat-card">
                        <div class="number">${todayLogs.length}</div>
                        <div>Uchezaji Leo</div>
                    </div>
                    <div class="stat-card">
                        <div class="number">${videoStats.length}</div>
                        <div>Video Zilizochezwa</div>
                    </div>
                </div>
                
                <h3 style="color:#ff0000; margin:20px 0 10px;">📊 TAKWIMU ZA KILA VIDEO</h3>
                <div class="video-stats-table">
                    <table>
                        <thead>
                            <tr><th>#</th><th>Jina la Video</th><th>Mara Imechezwa</th><th>Asilimia</th></tr>
                        </thead>
                        <tbody>
                            ${videoStats.map((stat, index) => `
                                <tr>
                                    <td>${index + 1}</td>
                                    <td><strong style="color:#ff6666;">🎬 ${stat.name}</strong></td>
                                    <td>${stat.count} views</td>
                                    <td>${totalPlays > 0 ? Math.round((stat.count/totalPlays)*100) : 0}%</td>
                                </tr>
                            `).join('')}
                            ${videoStats.length === 0 ? '<tr><td colspan="4" style="text-align:center;">📭 Hakuna data bado</td></tr>' : ''}
                        </tbody>
                    </table>
                </div>
                
                <div class="action-buttons">
                    <button class="btn btn-danger" id="clearLogsBtn">🗑️ FUTA REKODI ZOTE</button>
                    <button class="btn btn-warning" id="exportLogsBtn">📥 EXPORT LOGS (JSON)</button>
                </div>
                
                <h3 style="color:#ff0000; margin:20px 0 10px;">📋 REKODI ZA WATAZAMAJI</h3>
                <div class="logs-container">
                    ${logs.length === 0 ? `
                        <div style="text-align:center; padding:40px; color:#555;">
                            📭 Hakuna rekodi bado. Watazamaji wakianza kuangalia video, wataonekana hapa.
                        </div>
                    ` : logs.slice().reverse().map(log => `
                        <div class="log-item">
                            <div><span style="color:#ff6666;">🎬 ${log.videoName}</span> (ID: ${log.videoId})</div>
                            <div style="color:#66ff66; font-size:12px;">👤 ${log.viewerId}</div>
                            <div style="color:#aaa; font-size:11px;">🕐 ${log.timestamp}</div>
                        </div>
                    `).join('')}
                </div>
            `;
            
            document.getElementById('dashboardContent').innerHTML = content;
            
            // Attach events
            const clearBtn = document.getElementById('clearLogsBtn');
            const exportBtn = document.getElementById('exportLogsBtn');
            if(clearBtn) clearBtn.addEventListener('click', clearAllLogs);
            if(exportBtn) exportBtn.addEventListener('click', exportLogs);
        }
        
        function showLoginPrompt() {
            const content = `
                <div class="login-overlay" id="loginOverlay">
                    <div class="login-box">
                        <h2 style="color:#ff0000;">🔐 ADMIN LOGIN</h2>
                        <p style="color:#aaa;">Weka password ya admin</p>
                        <input type="password" id="adminPasswordInput" placeholder="Password" autofocus>
                        <button id="submitLoginBtn">INGIA</button>
                        <div id="loginErrorMsg" style="color:red; margin-top:10px;"></div>
                        <p style="margin-top:15px; font-size:12px; color:#555;">Default: admin123</p>
                    </div>
                </div>
            `;
            document.getElementById('dashboardContent').innerHTML = content;
            
            const loginBtn = document.getElementById('submitLoginBtn');
            const passwordInput = document.getElementById('adminPasswordInput');
            
            loginBtn.addEventListener('click', () => {
                const password = passwordInput.value;
                if(password === ADMIN_PASSWORD) {
                    isAdminLoggedIn = true;
                    renderDashboardContent();
                } else {
                    document.getElementById('loginErrorMsg').innerText = '❌ Password si sahihi!';
                }
            });
            
            passwordInput.addEventListener('keypress', (e) => {
                if(e.key === 'Enter') loginBtn.click();
            });
        }
        
        function openDashboard() {
            dashboard.classList.add('active');
            if(isAdminLoggedIn) {
                renderDashboardContent();
            } else {
                showLoginPrompt();
            }
        }
        
        function closeDashboard() {
            dashboard.classList.remove('active');
        }
        
        // ==================== EVENT LISTENERS ====================
        document.getElementById('adminBtn').addEventListener('click', openDashboard);
        document.getElementById('closeDashboardBtn').addEventListener('click', closeDashboard);
        
        // Close on outside click
        window.addEventListener('click', (e) => {
            if(e.target === dashboard) {
                closeDashboard();
            }
        });
        
        // ==================== INITIALIZE ====================
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
        });
    </script>
</body>
</html>
