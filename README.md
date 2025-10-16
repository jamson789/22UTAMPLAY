
<html lang="sw">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UtamPlay Video App</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1a0b1e 0%, #2d0b0b 100%);
            color: #ffffff;
            line-height: 1.6;
            min-height: 100vh;
        }
        
        header {
            background: rgba(140, 20, 20, 0.9);
            padding: 25px 20px;
            text-align: center;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
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
            background: linear-gradient(90deg, #ff0000, #ff3333);
        }
        
        h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            color: #ff0000;
            text-shadow: 0 2px 10px rgba(255, 0, 0, 0.5);
            font-weight: 900;
            letter-spacing: 2px;
            text-transform: uppercase;
        }
        
        .tagline {
            font-size: 1.2rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .container {
            max-width: 1200px;
            margin: 30px auto;
            padding: 0 20px;
        }
        
        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }
        
        .video-card {
            background: rgba(70, 10, 10, 0.7);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 50, 50, 0.3);
        }
        
        .video-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(255, 0, 0, 0.3);
        }
        
        .video-header {
            padding: 15px 20px;
            background: rgba(120, 20, 20, 0.9);
            border-bottom: 1px solid rgba(255, 50, 50, 0.3);
        }
        
        .video-header h2 {
            font-size: 1.4rem;
            color: #ffffff;
            margin: 0;
        }
        
        .video-container {
            position: relative;
            padding-top: 56.25%; /* 16:9 Aspect Ratio */
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
        
        .link {
            display: inline-block;
            padding: 12px 25px;
            background: linear-gradient(45deg, #ff0000, #ff3333);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 0, 0, 0.4);
            border: none;
            cursor: pointer;
            letter-spacing: 0.5px;
        }
        
        .link:hover {
            transform: translateY(-3px);
            box-shadow: 0 7px 20px rgba(255, 0, 0, 0.6);
            background: linear-gradient(45deg, #ff3333, #ff6666);
        }
        
        footer {
            background: rgba(26, 11, 14, 0.9);
            padding: 25px 20px;
            text-align: center;
            margin-top: 50px;
            border-top: 1px solid rgba(255, 50, 50, 0.3);
        }
        
        .footer-content {
            max-width: 600px;
            margin: 0 auto;
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
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .video-grid {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 2.5rem;
            }
            
            .tagline {
                font-size: 1rem;
            }
            
            .app-name {
                font-size: 1.8rem;
            }
        }
        
        /* Loading animation */
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        /* Video counter */
        .video-counter {
            text-align: center;
            margin: 20px 0;
            font-size: 1.1rem;
            color: #ff6666;
        }
    </style>
</head>
<body>
    <header>
        <h1 class="pulse">22utamplay</h1>
        <p class="tagline"></p>
    </header>
    
    <div class="container">
        <div class="video-counter"></div>
        
        <div class="video-grid">
            <!-- Video 1 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 1 - Mtam1</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/8B0000/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn71.xcdn1.me/m/1fc826149688a3b2be7412ecfa47eb60videoN2E1ZDlhMzIwZmFjNmU5MzYwZjU1OTQzNjQ5NTZiZjUubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">BonyezaHapa</a>
                </div>
            </div>
            
            <!-- Video 2 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 2 - utam2</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/A52A2A/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn60.xcdn1.me/m/68f8d6724333b76eb6524752ef027f70videoNTZhOTNmNTBlYTZjOGY5MTJkZjhkMTRmYjk1NjMxZWEubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">BonyezaHapa</a>
                </div>
            </div>
            
            <!-- Video 3 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 3 - utam3</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/B22222/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn60.xcdn1.me/d/b1bfde439c7869796b66bd30af6a7341videoNWIzYzY4MzBmMGQ1OGUzMWE2N2M0MTRhYzczNDQ4NGIubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">BonyezaHapa</a>
                </div>
            </div>
            
            <!-- Video 4 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 4 - utam4</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/DC143C/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn60.xcdn1.me/m/67ebc9207bd840839c3cf147036b7986videoOTI1N2NlNmYxZDMxMTE3ZGI3ODk5NTZiMDFjMWU1NGQubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">BonyezaHapa</a>
                </div>
            </div>
            
            <!-- Video 5 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 5 - utam5</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/FF0000/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn41.xcdn1.me/m/8d280585381f445c62c9ca462fd83ef0videoZjJkOWFiNmU3YzQ0MmI0MWUxMDk5YjQxNTQyOTM5MGMubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">Bonyeza Hapa</a>
                </div>
            </div>
            
            <!-- Video 6 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 6 - utam6</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/FF4500/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn101.xcdn1.me/m/52eaba3495e4c4a8477e418dfee66077videoMjVmYzFkOTI5NzU1MjhkNTg0ZDhjZWJjNWM0MzlhMTIubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">Bonyeza Hapa</a>
                </div>
            </div>

            <!-- Video 7 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 7 - utam7</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/8B0000/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn50.xcdn1.me/m/948312e62f159e8c1f9fbb800cfda540videoNDY1ODJkNDM4NGQ0YzBjM2E5ZmQ0ZjNkNzM4MTAxOTkubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">BonyezaHapa</a>
                </div>
            </div>

            <!-- Video 8 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 8 - utam8</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/A52A2A/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn71.xcdn1.me/m/1c947c7a2a5b8222e17a9635530d9583videoOWUyNDJjODExMmQ1MDkwYzg5MzAwYTEyMGU4ODhmMzkubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">BonyezaHapa</a>
                </div>
            </div>

            <!-- Video 9 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 9 - utam9</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/B22222/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn50.xcdn1.me/m/0a8b9c0297cb7f8e1b2010b453539541videoMjFmN2IwMjRhYmVkZTI4MTU1NGJhZDhlZTQ3Zjk1YjUubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">BonyezaHapa</a>
                </div>
            </div>

            <!-- Video 10 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 10 - utam10</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/DC143C/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn50.xcdn1.me/m/0b690e7be4eb45432a76498d4fc72001videoNjlmM2JmNDBhZjA5OTI3NWY0NmY2ODczNzc0Nzk2MDMubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">BonyezaHapa</a>
                </div>
            </div>

            <!-- Video 11 -->
            <div class="video-card">
                <div class="video-header">
                    <h2>Video 11 - utam11</h2>
                </div>
                <div class="video-container">
                    <video controls poster="https://via.placeholder.com/350x200/FF0000/ffffff?text=UTAMPLAY+VIDEO">
                        <source src="https://cdn72.xcdn1.me/m/0c6fb61a6fd4e9d1d4eae74bd9faa7bavideoYjBhMTcyZDQyNTIzMWZkOTljNTBhZGExYzk2N2Q5Y2UubXA0.mp4" type="video/mp4">
                        Kivinjini chako hakitumii video tag.
                    </video>
                </div>
                <div class="video-footer">
                    <a href="https://utamuutamu.store/ea43f" class="link" target="_blank">Bonyeza Hapa</a>
                </div>
            </div>
        </div>
    </div>
    
    <footer>
        <div class="footer-content">
            <div class="app-name">UTAMPLAY</div>
            <p></p>
            <p class="copyright">©2025 UtamPlay</p>
        </div>
    </footer>
    
    <script>
        // Simple animation for video cards on load
        document.addEventListener('DOMContentLoaded', function() {
            const videoCards = document.querySelectorAll('.video-card');
            
            videoCards.forEach((card, index) => {
                // Stagger the animation
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
            
            // Add click effect to buttons
            const links = document.querySelectorAll('.link');
            links.forEach(link => {
                link.addEventListener('mousedown', function() {
                    this.style.transform = 'scale(0.95)';
                });
                
                link.addEventListener('mouseup', function() {
                    this.style.transform = '';
                });
            });
            
            // Add red glow effect to header on load
            const header = document.querySelector('header');
            header.style.boxShadow = '0 4px 30px rgba(255, 0, 0, 0.7)';
            setTimeout(() => {
                header.style.boxShadow = '0 4px 20px rgba(0, 0, 0, 0.4)';
            }, 2000);
        });
    </script>
</body>
</html>
