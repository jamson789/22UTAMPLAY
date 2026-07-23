
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nyeto Tz · Connection Zote</title>
    <!-- Bootstrap 5 CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- Font Awesome 6 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js">
    </script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #6c5ce7;
            --secondary: #a29bfe;
            --accent: #fd79a8;
            --card-bg: rgba(20, 18, 40, 0.85);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: #0d0b1a;
            background-image: radial-gradient(circle at 10% 20%, #1a1040 0%, #0b0918 90%);
            color: #f0eaff;
            padding-top: 80px;
            min-height: 100vh;
            position: relative;
            overflow-x: hidden;
        }

        body::before {
            content: '';
            position: fixed;
            inset: 0;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 200"><circle cx="30" cy="30" r="1.5" fill="%23a29bfe" opacity="0.3"/><circle cx="170" cy="70" r="2" fill="%23fd79a8" opacity="0.25"/><circle cx="80" cy="180" r="1.8" fill="%23a29bfe" opacity="0.2"/><circle cx="140" cy="140" r="1.2" fill="%23ffffff" opacity="0.15"/></svg>') repeat;
            pointer-events: none;
            z-index: 0;
            opacity: 0.5;
        }

        .container,
        .navbar,
        .footer {
            position: relative;
            z-index: 2;
        }

        /* NAVBAR */
        .navbar {
            background: rgba(10, 8, 25, 0.85);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(108, 92, 231, 0.3);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.6);
            padding: 12px 0;
        }

        .navbar-brand {
            font-weight: 800;
            font-size: 2rem;
            background: linear-gradient(135deg, #a29bfe, #fd79a8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: 1px;
        }

        .navbar-brand i {
            -webkit-text-fill-color: initial;
            color: #fd79a8;
            margin-right: 10px;
        }

        .btn-admin-nav {
            background: rgba(253, 121, 168, 0.15);
            border: 1px solid rgba(253, 121, 168, 0.3);
            color: #fd79a8;
            border-radius: 50px;
            padding: 8px 24px;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            text-decoration: none;
            display: inline-block;
        }

        .btn-admin-nav:hover {
            background: rgba(253, 121, 168, 0.3);
            color: #fff;
            border-color: #fd79a8;
            transform: scale(1.05);
        }

        .btn-viewer-nav {
            background: rgba(108, 92, 231, 0.15);
            border: 1px solid rgba(108, 92, 231, 0.3);
            color: #a29bfe;
            border-radius: 50px;
            padding: 8px 24px;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            text-decoration: none;
            display: inline-block;
        }

        .btn-viewer-nav:hover {
            background: rgba(108, 92, 231, 0.3);
            color: #fff;
            border-color: #a29bfe;
            transform: scale(1.05);
        }

        /* SECTION TITLE */
        .section-title {
            font-weight: 800;
            font-size: 2rem;
            background: linear-gradient(to right, #a29bfe, #fd79a8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: inline-block;
            text-shadow: 0 0 40px rgba(162, 155, 254, 0.2);
            position: relative;
        }

        .section-title::after {
            content: '✦';
            -webkit-text-fill-color: initial;
            color: #fd79a8;
            margin-left: 12px;
            font-size: 1.4rem;
            opacity: 0.7;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(162, 155, 254, 0.15);
            padding-bottom: 16px;
            margin-bottom: 30px;
        }

        /* VIDEO CARDS */
        .video-card {
            background: var(--card-bg);
            backdrop-filter: blur(8px);
            border: 1px solid rgba(162, 155, 254, 0.15);
            border-radius: 24px;
            overflow: hidden;
            transition: all 0.35s cubic-bezier(0.2, 0.9, 0.3, 1.2);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.5);
            margin-bottom: 28px;
            height: 100%;
            display: flex;
            flex-direction: column;
        }

        .video-card:hover {
            transform: translateY(-12px) scale(1.01);
            box-shadow: 0 25px 60px rgba(108, 92, 231, 0.3);
            border-color: rgba(162, 155, 254, 0.4);
        }

        .video-wrapper {
            position: relative;
            width: 100%;
            padding-top: 56.25%;
            background: #0a0818;
            overflow: hidden;
            border-bottom: 1px solid rgba(162, 155, 254, 0.1);
        }

        .video-wrapper video {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            background: #0a0818;
        }

        .card-body {
            padding: 18px 20px;
            background: transparent;
            flex: 1;
        }

        .video-info {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        .video-info span {
            font-weight: 600;
            font-size: 1.05rem;
            color: #e4ddff;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .video-actions {
            display: flex;
            gap: 8px;
        }

        .btn-action {
            background: rgba(162, 155, 254, 0.08);
            border: 1px solid rgba(162, 155, 254, 0.15);
            color: #c8bfff;
            width: 38px;
            height: 38px;
            border-radius: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s ease;
            cursor: pointer;
        }

        .btn-action:hover {
            background: rgba(253, 121, 168, 0.2);
            color: #fd79a8;
            border-color: #fd79a8;
            transform: scale(1.1);
        }

        /* SHOW MORE */
        .btn-show-more {
            background: linear-gradient(135deg, #6c5ce7, #a29bfe);
            border: none;
            padding: 14px 40px;
            border-radius: 60px;
            font-weight: 700;
            font-size: 1rem;
            letter-spacing: 1px;
            color: #fff;
            box-shadow: 0 8px 30px rgba(108, 92, 231, 0.4);
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .btn-show-more:hover {
            transform: scale(1.04) translateY(-4px);
            box-shadow: 0 16px 50px rgba(108, 92, 231, 0.6);
            background: linear-gradient(135deg, #7c6cf0, #b2abff);
            color: #fff;
        }

        /* ADMIN PANEL */
        .admin-panel {
            background: rgba(10, 8, 25, 0.95);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(162, 155, 254, 0.2);
            border-radius: 24px;
            padding: 30px;
            margin-bottom: 40px;
        }

        .admin-panel .form-control {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(162, 155, 254, 0.2);
            color: #fff;
            border-radius: 12px;
            padding: 12px 16px;
        }

        .admin-panel .form-control:focus {
            background: rgba(255, 255, 255, 0.08);
            border-color: #a29bfe;
            box-shadow: 0 0 20px rgba(108, 92, 231, 0.2);
            color: #fff;
        }

        .admin-panel .form-control::placeholder {
            color: rgba(255, 255, 255, 0.3);
        }

        .btn-upload {
            background: linear-gradient(135deg, #6c5ce7, #a29bfe);
            border: none;
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: 600;
            color: #fff;
            transition: all 0.3s ease;
        }

        .btn-upload:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 30px rgba(108, 92, 231, 0.4);
            color: #fff;
        }

        .btn-danger-sm {
            background: rgba(253, 121, 168, 0.15);
            border: 1px solid rgba(253, 121, 168, 0.3);
            color: #fd79a8;
            border-radius: 50px;
            padding: 6px 16px;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            font-size: 0.85rem;
        }

        .btn-danger-sm:hover {
            background: rgba(253, 121, 168, 0.3);
            color: #fff;
        }

        /* ANALYTICS - WASTANI DESIGN */
        .analytics-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 14px;
            margin-bottom: 20px;
        }

        .stat-card-sm {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(162, 155, 254, 0.08);
            border-radius: 14px;
            padding: 14px 12px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-card-sm:hover {
            background: rgba(255, 255, 255, 0.05);
            border-color: rgba(162, 155, 254, 0.15);
        }

        .stat-number-sm {
            font-size: 1.6rem;
            font-weight: 700;
            background: linear-gradient(135deg, #a29bfe, #fd79a8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1.2;
        }

        .stat-label-sm {
            color: rgba(255, 255, 255, 0.4);
            font-size: 0.7rem;
            font-weight: 400;
            margin-top: 3px;
            letter-spacing: 0.3px;
        }

        .stat-icon-sm {
            font-size: 1.2rem;
            color: #a29bfe;
            opacity: 0.25;
            margin-bottom: 3px;
        }

        .analytics-row {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 16px;
            margin-top: 4px;
        }

        .chart-box {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(162, 155, 254, 0.08);
            border-radius: 14px;
            padding: 14px 16px;
            min-height: 220px;
        }

        .chart-box h6 {
            color: #a29bfe;
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .chart-box canvas {
            height: 160px !important;
            min-height: 160px;
            width: 100% !important;
        }

        .visit-log-sm {
            max-height: 180px;
            overflow-y: auto;
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(162, 155, 254, 0.08);
            border-radius: 14px;
            padding: 10px 12px;
        }

        .visit-log-sm .item {
            padding: 5px 8px;
            border-bottom: 1px solid rgba(162, 155, 254, 0.04);
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.75rem;
            display: flex;
            justify-content: space-between;
        }

        .visit-log-sm .item:last-child {
            border-bottom: none;
        }

        .visit-log-sm .item .time {
            color: rgba(255, 255, 255, 0.25);
            font-size: 0.65rem;
        }

        /* PASSWORD OVERLAY */
        .password-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(8px);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 9999;
        }

        .password-overlay.active {
            display: flex;
        }

        .password-box {
            background: rgba(20, 18, 40, 0.95);
            border: 1px solid rgba(162, 155, 254, 0.2);
            border-radius: 24px;
            padding: 40px;
            max-width: 400px;
            width: 90%;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.8);
        }

        .password-box h4 {
            color: #a29bfe;
            margin-bottom: 20px;
            font-size: 1.3rem;
        }

        .password-box .form-control {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(162, 155, 254, 0.2);
            color: #fff;
            border-radius: 12px;
            padding: 12px 16px;
        }

        .password-box .form-control:focus {
            background: rgba(255, 255, 255, 0.08);
            border-color: #a29bfe;
            box-shadow: 0 0 20px rgba(108, 92, 231, 0.2);
            color: #fff;
        }

        .btn-cancel {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            color: rgba(255, 255, 255, 0.5);
            border-radius: 50px;
            padding: 8px 20px;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .btn-cancel:hover {
            background: rgba(255, 255, 255, 0.1);
            color: #fff;
        }

        /* ADMIN TABS */
        .admin-tabs {
            border-bottom: 1px solid rgba(162, 155, 254, 0.1);
            margin-bottom: 20px;
            display: flex;
            gap: 6px;
            flex-wrap: wrap;
        }

        .admin-tab {
            padding: 8px 20px;
            border-radius: 10px 10px 0 0;
            color: rgba(255, 255, 255, 0.4);
            font-weight: 600;
            font-size: 0.85rem;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
            background: transparent;
        }

        .admin-tab:hover {
            color: #fff;
            background: rgba(162, 155, 254, 0.05);
        }

        .admin-tab.active {
            color: #a29bfe;
            background: rgba(162, 155, 254, 0.08);
            border-bottom: 2px solid #a29bfe;
        }

        .admin-tab i {
            margin-right: 6px;
        }

        .admin-content {
            display: none;
        }

        .admin-content.active {
            display: block;
        }

        .video-list-item {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(162, 155, 254, 0.06);
            border-radius: 10px;
            padding: 10px 14px;
            margin-bottom: 6px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .video-list-item .title {
            color: rgba(255, 255, 255, 0.75);
            font-size: 0.9rem;
        }

        .video-list-item .url {
            color: rgba(255, 255, 255, 0.2);
            font-size: 0.7rem;
            max-width: 250px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
        }

        /* FOOTER */
        .footer {
            background: rgba(8, 6, 20, 0.9);
            backdrop-filter: blur(8px);
            border-top: 1px solid rgba(162, 155, 254, 0.08);
            padding: 40px 0 16px;
            margin-top: 50px;
        }

        .footer-title {
            font-weight: 800;
            background: linear-gradient(to right, #a29bfe, #fd79a8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-size: 1.5rem;
        }

        .copyright {
            text-align: center;
            color: rgba(200, 190, 255, 0.3);
            font-weight: 300;
            font-size: 0.85rem;
            letter-spacing: 0.5px;
            border-top: 1px solid rgba(162, 155, 254, 0.05);
            padding-top: 20px;
            margin-top: 24px;
        }

        .video-count {
            color: #a29bfe;
            font-size: 0.85rem;
            opacity: 0.5;
        }

        /* Page toggle */
        .page-viewer {
            display: block;
        }
        .page-admin {
            display: none;
        }

        .page-admin.active {
            display: block;
        }
        .page-viewer.hidden {
            display: none;
        }

        @media (max-width: 768px) {
            body {
                padding-top: 70px;
            }
            .section-title {
                font-size: 1.5rem;
            }
            .admin-panel {
                padding: 16px;
            }
            .analytics-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 10px;
            }
            .analytics-row {
                grid-template-columns: 1fr;
                gap: 12px;
            }
            .stat-number-sm {
                font-size: 1.3rem;
            }
            .video-list-item {
                flex-direction: column;
                align-items: flex-start;
                gap: 4px;
            }
            .video-list-item .url {
                max-width: 100%;
            }
            .admin-tab {
                padding: 6px 14px;
                font-size: 0.75rem;
            }
            .chart-box canvas {
                height: 130px !important;
                min-height: 130px;
            }
        }

        ::-webkit-scrollbar {
            width: 8px;
            background: #0b0918;
        }
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(#6c5ce7, #a29bfe);
            border-radius: 20px;
            border: 2px solid #0b0918;
        }
        ::-webkit-scrollbar-track {
            background: #0b0918;
        }
    </style>
</head>

<body>

    <!-- PASSWORD OVERLAY -->
    <div class="password-overlay" id="passwordOverlay">
        <div class="password-box">
            <h4><i class="fas fa-lock me-2"></i>Admin Access</h4>
            <p style="color: rgba(255,255,255,0.4); font-size: 0.85rem;">Ingiza password kuingia Admin</p>
            <input type="password" class="form-control" id="adminPasswordInput" placeholder="Enter password...">
            <div class="mt-3 d-flex gap-2">
                <button class="btn-upload w-100" onclick="verifyAdminPassword()">Confirm</button>
                <button class="btn-cancel" onclick="closePasswordOverlay()">Cancel</button>
            </div>
            <p id="adminPassError" style="color: #fd79a8; font-size: 0.8rem; margin-top: 10px; display: none;">Password incorrect!</p>
        </div>
    </div>

    <!-- NAVBAR -->
    <nav class="navbar navbar-expand-lg navbar-dark fixed-top">
        <div class="container">
            <a class="navbar-brand" href="#" onclick="showViewerPage()">
                <i class="fas fa-play-circle"></i>Nyeto Tz
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto align-items-center">
                    <li class="nav-item me-2">
                        <button class="btn-viewer-nav" onclick="showViewerPage()">
                            <i class="fas fa-eye me-1"></i> Viewer
                        </button>
                    </li>
                    <li class="nav-item">
                        <button class="btn-admin-nav" onclick="openAdminPage()">
                            <i class="fas fa-user-shield me-1"></i> Admin
                        </button>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- ========================================================== -->
    <!-- PAGE: VIEWER -->
    <!-- ========================================================== -->
    <div class="page-viewer" id="viewerPage">
        <section class="container mb-4">
            <div class="section-header">
                <h2 class="section-title">✦ Connection Zote</h2>
                <span class="video-count" id="videoCount">0 videos</span>
            </div>

            <div class="row" id="videoContainer"></div>
            <div class="hidden-videos" style="display:none;"></div>

            <div class="show-more-container text-center mt-3">
                <button id="showMoreBtn" class="btn-show-more"><i class="fas fa-chevron-down me-2"></i>Show More Videos</button>
            </div>
        </section>
    </div>

    <!-- ========================================================== -->
    <!-- PAGE: ADMIN -->
    <!-- ========================================================== -->
    <div class="page-admin" id="adminPage">
        <section class="container mb-4">
            <div class="section-header">
                <h2 class="section-title">✦ Admin Dashboard</h2>
                <button class="btn-viewer-nav" onclick="showViewerPage()">
                    <i class="fas fa-eye me-1"></i> View Website
                </button>
            </div>

            <div class="admin-panel">
                <!-- Tabs -->
                <div class="admin-tabs">
                    <button class="admin-tab active" data-tab="upload" onclick="switchAdminTab('upload')">
                        <i class="fas fa-cloud-upload-alt"></i> Upload
                    </button>
                    <button class="admin-tab" data-tab="manage" onclick="switchAdminTab('manage')">
                        <i class="fas fa-list"></i> Manage
                    </button>
                    <button class="admin-tab" data-tab="analytics" onclick="switchAdminTab('analytics')">
                        <i class="fas fa-chart-line"></i> Analytics
                    </button>
                </div>

                <!-- TAB: Upload -->
                <div class="admin-content active" id="tabUpload">
                    <h5 style="color: #a29bfe; margin-bottom: 16px; font-size: 1rem;"><i class="fas fa-plus-circle me-2"></i>Upload New Video</h5>
                    <form id="uploadForm" onsubmit="addVideo(event)">
                        <div class="row g-3">
                            <div class="col-md-8">
                                <label class="form-label" style="color: #a29bfe; font-size: 0.85rem;">Video URL (mp4)</label>
                                <input type="url" class="form-control" id="videoUrl" placeholder="https://example.com/video.mp4" required>
                            </div>
                            <div class="col-md-4">
                                <label class="form-label" style="color: #a29bfe; font-size: 0.85rem;">Title</label>
                                <input type="text" class="form-control" id="videoTitle" placeholder="Video title..." required>
                            </div>
                            <div class="col-12">
                                <button type="submit" class="btn-upload" style="padding: 10px 28px; font-size: 0.9rem;"><i class="fas fa-plus-circle me-2"></i>Add Video</button>
                            </div>
                        </div>
                    </form>
                    <hr style="border-color: rgba(162,155,254,0.06); margin: 16px 0;">
                    <p style="color: rgba(255,255,255,0.3); font-size: 0.75rem;">
                        <i class="fas fa-info-circle me-1"></i> Videos zina saved kwenye browser. 
                        <span id="totalVideosInStorage">0</span> videos total.
                    </p>
                </div>

                <!-- TAB: Manage -->
                <div class="admin-content" id="tabManage">
                    <h5 style="color: #a29bfe; margin-bottom: 16px; font-size: 1rem;"><i class="fas fa-list me-2"></i>Manage Videos</h5>
                    <div id="videoListContainer">
                        <p style="color: rgba(255,255,255,0.25); font-size: 0.85rem;">Loading...</p>
                    </div>
                </div>

                <!-- TAB: Analytics (WASTANI DESIGN) -->
                <div class="admin-content" id="tabAnalytics">
                    <h5 style="color: #a29bfe; margin-bottom: 14px; font-size: 1rem;"><i class="fas fa-chart-pie me-2"></i>Analytics</h5>

                    <!-- Stats - wastani -->
                    <div class="analytics-grid">
                        <div class="stat-card-sm">
                            <div class="stat-icon-sm"><i class="fas fa-user"></i></div>
                            <div class="stat-number-sm" id="todayVisitors">0</div>
                            <div class="stat-label-sm">Leo</div>
                        </div>
                        <div class="stat-card-sm">
                            <div class="stat-icon-sm"><i class="fas fa-users"></i></div>
                            <div class="stat-number-sm" id="weekVisitors">0</div>
                            <div class="stat-label-sm">Wiki Hii</div>
                        </div>
                        <div class="stat-card-sm">
                            <div class="stat-icon-sm"><i class="fas fa-globe"></i></div>
                            <div class="stat-number-sm" id="totalVisitors">0</div>
                            <div class="stat-label-sm">Jumla</div>
                        </div>
                        <div class="stat-card-sm">
                            <div class="stat-icon-sm"><i class="fas fa-eye"></i></div>
                            <div class="stat-number-sm" id="totalPageViews">0</div>
                            <div class="stat-label-sm">Page Views</div>
                        </div>
                    </div>

                    <!-- Chart + Log -->
                    <div class="analytics-row">
                        <div class="chart-box">
                            <h6><i class="fas fa-calendar-alt me-2"></i>Siku 7 zilizopita</h6>
                            <canvas id="visitorChart"></canvas>
                        </div>
                        <div class="chart-box">
                            <h6><i class="fas fa-clock me-2"></i>Recent Visits</h6>
                            <div class="visit-log-sm" id="visitLog">
                                <div style="color: rgba(255,255,255,0.2); text-align: center; padding: 15px; font-size: 0.8rem;">No visits yet</div>
                            </div>
                        </div>
                    </div>

                    <!-- Reset -->
                    <div class="mt-3">
                        <button class="btn-danger-sm" onclick="resetAnalytics()" style="font-size: 0.75rem; padding: 4px 14px;">
                            <i class="fas fa-trash me-1"></i> Reset Analytics
                        </button>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- FOOTER -->
    <footer class="footer">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-md-6">
                    <h5 class="footer-title"><i class="fas fa-play-circle me-2" style="-webkit-text-fill-color:initial;color:#fd79a8;"></i>Nyeto Tz</h5>
                    <p style="color: #a29bfe; opacity:0.4; font-size:0.8rem;">Connection Zote</p>
                </div>
                <div class="col-md-6 text-md-end">
                    <span style="color: #a29bfe; opacity:0.2; font-size:0.8rem;"><i class="fas fa-star"></i> アニメ</span>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2026 Nyeto Tz</p>
            </div>
        </div>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js">
    </script>

    <script>
        // ============================================================
        // 1. VIDEOS DATA
        // ============================================================
        const DEFAULT_VIDEOS = [
            { url: "https://cdn.tanzaniahub.icu/cdn/connection_teacher_student.mp4", title: "Connection Teacher Student" },
            { url: "https://cdn.tanzaniahub.icu/cdn/Mtoto_Mchungaj.mp4", title: "Mtoto Mchungaj" },
            { url: "https://cdn.tanzaniahub.icu/cdn/xVdiode_.mp4", title: "xVdiode" },
            { url: "https://cdn.tanzaniahub.icu/cdn/Xvideo.mp4", title: "Xvideo" },
            { url: "https://cdn.tanzaniahub.icu/cdn/Connectionza_112.mp4", title: "Connectionza 112" },
            { url: "https://cdn.tanzaniahub.icu/cdn/TomBoi9091.mp4", title: "TomBoi9091" },
            { url: "https://cdn.tanzaniahub.icu/cdn/Xvideoo.mp4", title: "Xvideoo" },
            { url: "https://cdn.tanzaniahub.icu/cdn/Connectionion_121.mp4", title: "Connectionion 121" },
            { url: "https://cdn.tanzaniahub.icu/cdn/Xvideo11.mp4", title: "Xvideo11" },
            { url: "https://cdn.tanzaniahub.icu/cdn/cONNECTION11.mp4", title: "cONNECTION11" },
            { url: "https://cdn.tanzaniahub.icu/cdn/Connection_3.mp4", title: "Connection 3" }
        ];

        let allVideos = [];
        let currentIndex = 0;
        const increment = 4;

        // ============================================================
        // 2. ANALYTICS        // ============================================================
        function getAnalytics() {
            let data = localStorage.getItem('nyeto_analytics');
            if (data) {
                try { return JSON.parse(data); } catch (e) {}
            }
            const init = { visits: [], pageViews: 0 };
            localStorage.setItem('nyeto_analytics', JSON.stringify(init));
            return init;
        }

        function saveAnalytics(data) {
            localStorage.setItem('nyeto_analytics', JSON.stringify(data));
        }

        function recordVisit() {
            const analytics = getAnalytics();
            const now = new Date();
            const dateStr = now.toISOString().split('T')[0];
            const timeStr = now.toTimeString().slice(0, 5);

            let visitorId = localStorage.getItem('nyeto_visitor_id');
            if (!visitorId) {
                visitorId = 'v_' + Math.random().toString(36).substr(2, 6);
                localStorage.setItem('nyeto_visitor_id', visitorId);
            }

            const todayVisits = analytics.visits.filter(v => v.date === dateStr);
            const alreadyVisited = todayVisits.some(v => v.visitorId === visitorId);

            if (!alreadyVisited) {
                analytics.visits.push({ date: dateStr, time: timeStr, visitorId: visitorId });
            }
            analytics.pageViews = (analytics.pageViews || 0) + 1;
            saveAnalytics(analytics);
        }

        // ============================================================
        // 3. VIDEO STORAGE
        // ============================================================
        function loadVideosFromStorage() {
            const stored = localStorage.getItem('nyeto_videos');
            if (stored) {
                try { allVideos = JSON.parse(stored); return; } catch (e) {}
            }
            allVideos = [...DEFAULT_VIDEOS];
            saveVideosToStorage();
        }

        function saveVideosToStorage() {
            localStorage.setItem('nyeto_videos', JSON.stringify(allVideos));
        }

        // ============================================================
        // 4. RENDER VIDEOS
        // ============================================================
        function shuffleArray(arr) {
            for (let i = arr.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [arr[i], arr[j]] = [arr[j], arr[i]];
            }
            return arr;
        }

        function renderVideos() {
            const container = document.getElementById('videoContainer');
            const hiddenContainer = document.querySelector('.hidden-videos');
            const showMoreBtn = document.getElementById('showMoreBtn');

            container.innerHTML = '';
            hiddenContainer.innerHTML = '';
            currentIndex = 0;

            const shuffled = shuffleArray([...allVideos]);
            const animeIcons = ['🌸', '⚡', '🔥', '🌀', '⭐', '🍃', '✨', '🎴', '💫', '🌟', '🌈', '🎯', '💎', '🌊'];

            shuffled.forEach((video, idx) => {
                const card = document.createElement('div');
                card.className = "col-md-6 col-lg-6 mb-4";
                const icon = animeIcons[idx % animeIcons.length];
                const displayTitle = video.title || video.url.split('/').pop().replace('.mp4', '').replace(/_/g, ' ');

                card.innerHTML = `
                    <div class="video-card">
                        <div class="video-wrapper">
                            <video controls preload="metadata">
                                <source src="${video.url}" type="video/mp4">
                            </video>
                        </div>
                        <div class="card-body">
                            <div class="video-info">
                                <span><i class="fas fa-play-circle" style="color:#a29bfe;"></i> ${displayTitle} ${icon}</span>
                                <div class="video-actions">
                                    <button class="btn-action"><i class="fas fa-heart"></i></button>
                                    <button class="btn-action"><i class="fas fa-share-alt"></i></button>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
                hiddenContainer.appendChild(card);
            });

            const hiddenVideos = Array.from(hiddenContainer.children);
            const nextVideos = hiddenVideos.slice(0, increment);
            nextVideos.forEach(v => container.appendChild(v));
            currentIndex = increment;

            if (currentIndex >= hiddenVideos.length) {
                showMoreBtn.style.display = "none";
            } else {
                showMoreBtn.style.display = "inline-block";
            }

            document.getElementById('videoCount').textContent = allVideos.length + ' videos';
            document.getElementById('totalVideosInStorage').textContent = allVideos.length;

            window._hiddenVideos = hiddenVideos;
            window._showMoreBtn = showMoreBtn;
            renderVideoList();
        }

        // ============================================================
        // 5. SHOW MORE
        // ============================================================
        document.getElementById('showMoreBtn').addEventListener('click', function() {
            const container = document.getElementById('videoContainer');
            const hidden = window._hiddenVideos || [];
            const next = hidden.slice(currentIndex, currentIndex + increment);
            next.forEach(v => container.appendChild(v));
            currentIndex += increment;
            if (currentIndex >= hidden.length) {
                this.style.display = "none";
            }
        });

        // ============================================================
        // 6. PAGE NAVIGATION
        // ============================================================
        const ADMIN_PASSWORD = "admin123";
        let chartInstance = null;

        function showViewerPage() {
            document.getElementById('viewerPage').style.display = 'block';
            document.getElementById('adminPage').style.display = 'none';
            document.getElementById('adminPage').classList.remove('active');
        }

        function openAdminPage() {
            document.getElementById('passwordOverlay').classList.add('active');
            document.getElementById('adminPasswordInput').value = '';
            document.getElementById('adminPassError').style.display = 'none';
        }

        function closePasswordOverlay() {
            document.getElementById('passwordOverlay').classList.remove('active');
        }

        function verifyAdminPassword() {
            const input = document.getElementById('adminPasswordInput').value;
            if (input === ADMIN_PASSWORD) {
                closePasswordOverlay();
                document.getElementById('viewerPage').style.display = 'none';
                document.getElementById('adminPage').style.display = 'block';
                document.getElementById('adminPage').classList.add('active');
                renderVideoList();
                setTimeout(updateAnalyticsDashboard, 150);
            } else {
                document.getElementById('adminPassError').style.display = 'block';
            }
        }

        document.getElementById('adminPasswordInput').addEventListener('keydown', function(e) {
            if (e.key === 'Enter') verifyAdminPassword();
        });

        // ============================================================
        // 7. ADMIN TABS
        // ============================================================
        function switchAdminTab(tab) {
            document.querySelectorAll('.admin-tab').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.admin-content').forEach(c => c.classList.remove('active'));

            document.querySelector(`.admin-tab[data-tab="${tab}"]`).classList.add('active');
            document.getElementById('tab' + tab.charAt(0).toUpperCase() + tab.slice(1)).classList.add('active');

            if (tab === 'analytics') {
                setTimeout(updateAnalyticsDashboard, 100);
            }
            if (tab === 'manage') {
                renderVideoList();
            }
        }

        // ============================================================
        // 8. ADD / DELETE VIDEO
        // ============================================================
        function addVideo(e) {
            e.preventDefault();
            const url = document.getElementById('videoUrl').value.trim();
            const title = document.getElementById('videoTitle').value.trim();

            if (!url || !title) {
                alert('Tafadhali jaza URL na Title!');
                return;
            }

            if (allVideos.some(v => v.url === url)) {
                alert('Video hii tayari ipo!');
                return;
            }

            allVideos.push({ url, title });
            saveVideosToStorage();
            renderVideos();

            document.getElementById('videoUrl').value = '';
            document.getElementById('videoTitle').value = '';

            const btn = e.target.querySelector('button[type="submit"]');
            const original = btn.innerHTML;
            btn.innerHTML = '<i class="fas fa-check me-2"></i>Added!';
            setTimeout(() => btn.innerHTML = original, 1500);
        }

        function deleteVideo(url) {
            if (confirm('Je, una uhakika unataka kufuta video hii?')) {
                allVideos = allVideos.filter(v => v.url !== url);
                saveVideosToStorage();
                renderVideos();
            }
        }

        function renderVideoList() {
            const container = document.getElementById('videoListContainer');
            if (allVideos.length === 0) {
                container.innerHTML = '<p style="color: rgba(255,255,255,0.25); font-size: 0.85rem;">No videos uploaded yet.</p>';
                return;
            }

            container.innerHTML = allVideos.map((v, i) => `
                <div class="video-list-item">
                    <div>
                        <div class="title">${i+1}. ${v.title}</div>
                        <div class="url">${v.url}</div>
                    </div>
                    <button class="btn-danger-sm" onclick="deleteVideo('${v.url}')" style="font-size:0.7rem; padding:4px 12px;">
                        <i class="fas fa-trash"></i> Delete
                    </button>
                </div>
            `).join('');
        }

        // ============================================================
        // 9. ANALYTICS DASHBOARD (WASTANI - IMEBORESHA)
        // ============================================================
        function updateAnalyticsDashboard() {
            const analytics = getAnalytics();
            const visits = analytics.visits || [];
            const pageViews = analytics.pageViews || 0;

            const today = new Date().toISOString().split('T')[0];
            const todayVisits = visits.filter(v => v.date === today);
            const uniqueToday = new Set(todayVisits.map(v => v.visitorId));
            document.getElementById('todayVisitors').textContent = uniqueToday.size;

            const weekAgo = new Date();
            weekAgo.setDate(weekAgo.getDate() - 7);
            const weekStr = weekAgo.toISOString().split('T')[0];
            const weekVisits = visits.filter(v => v.date >= weekStr);
            const uniqueWeek = new Set(weekVisits.map(v => v.visitorId));
            document.getElementById('weekVisitors').textContent = uniqueWeek.size;

            const allUnique = new Set(visits.map(v => v.visitorId));
            document.getElementById('totalVisitors').textContent = allUnique.size;
            document.getElementById('totalPageViews').textContent = pageViews;

            const logContainer = document.getElementById('visitLog');
            if (visits.length === 0) {
                logContainer.innerHTML = '<div style="color: rgba(255,255,255,0.2); text-align: center; padding: 15px; font-size: 0.8rem;">No visits yet</div>';
            } else {
                const recent = visits.slice(-15).reverse();
                logContainer.innerHTML = recent.map(v =>
                    `<div class="item">
                        <span>${v.date}</span>
                        <span class="time">${v.time}</span>
                    </div>`
                ).join('');
            }

            // Chart - sasa ina height fixed
            const days = [];
            const counts = [];
            for (let i = 6; i >= 0; i--) {
                const d = new Date();
                d.setDate(d.getDate() - i);
                const ds = d.toISOString().split('T')[0];
                days.push(ds.slice(5));
                const dayVisits = visits.filter(v => v.date === ds);
                const unique = new Set(dayVisits.map(v => v.visitorId));
                counts.push(unique.size);
            }

            const ctx = document.getElementById('visitorChart').getContext('2d');
            if (chartInstance) chartInstance.destroy();

            chartInstance = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: days,
                    datasets: [{
                        label: 'Visitors',
                        data: counts,
                        borderColor: '#a29bfe',
                        backgroundColor: 'rgba(162, 155, 254, 0.08)',
                        tension: 0.3,
                        fill: true,
                        pointBackgroundColor: '#fd79a8',
                        pointBorderColor: '#fd79a8',
                        pointRadius: 3,
                        borderWidth: 2
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { 
                            labels: { 
                                color: 'rgba(255,255,255,0.4)', 
                                boxWidth: 10,
                                font: { size: 10 }
                            } 
                        }
                    },
                    scales: {
                        y: { 
                            beginAtZero: true, 
                            ticks: { color: 'rgba(255,255,255,0.25)', stepSize: 1, font: { size: 9 } },
                            grid: { color: 'rgba(255,255,255,0.03)' }
                        },
                        x: { 
                            ticks: { color: 'rgba(255,255,255,0.25)', font: { size: 9 } },
                            grid: { color: 'rgba(255,255,255,0.03)' }
                        }
                    }
                }
            });
        }

        function resetAnalytics() {
            if (confirm('Futa data zote za analytics?')) {
                localStorage.removeItem('nyeto_analytics');
                localStorage.removeItem('nyeto_visitor_id');
                updateAnalyticsDashboard();
            }
        }

        // ============================================================
        // 10. INIT
        // ============================================================
        loadVideosFromStorage();
        renderVideos();
        recordVisit();
        showViewerPage();

        console.log('✅ Nyeto Tz ready!');
        console.log('🔐 Admin password: admin123');
    </script>

</body>

</html>
