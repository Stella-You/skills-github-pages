
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>「幽」のStorage</title>
    <style>
        :root {
            --primary-color: #e8d6ff;
            --secondary-color: #d1b8ff;
            --text-color: #4a3a6d;
            --accent-color: #8a75c4;
            --background-color: #faf9ff;
            --border-radius: 8px;
            --shadow: 0 2px 15px rgba(138, 117, 196, 0.15);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #f8f5ff 0%, #e6e1ff 100%);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: var(--text-color);
            line-height: 1.6;
            padding: 20px;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            text-align: center;
            margin-bottom: 40px;
            padding: 30px 0;
        }

        h1 {
            font-size: 2.8rem;
            background: linear-gradient(45deg, #8a75c4, #6a55a3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
            font-weight: 300;
        }

        .subtitle {
            color: var(--accent-color);
            font-size: 1.1rem;
            opacity: 0.9;
        }

        .tabs-container {
            background: rgba(255, 255, 255, 0.92);
            backdrop-filter: blur(10px);
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            padding: 15px;
            margin-bottom: 40px;
            position: sticky;
            top: 20px;
            z-index: 100;
        }

        .tabs {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tab {
            background: var(--primary-color);
            color: var(--text-color);
            border: none;
            padding: 12px 24px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 0.95rem;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .tab:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
        }

        .tab.active {
            background: var(--accent-color);
            color: white;
            box-shadow: 0 4px 10px rgba(138, 117, 196, 0.3);
        }

        .tab-content {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(8px);
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            padding: 40px;
            margin-bottom: 30px;
            display: none;
            animation: fadeIn 0.4s ease;
        }

        .tab-content.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section-title {
            font-size: 1.8rem;
            color: var(--accent-color);
            margin-bottom: 25px;
            position: relative;
            padding-bottom: 10px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 3px;
            background: var(--accent-color);
            border-radius: 3px;
        }

        .content-box {
            padding: 20px;
            background: white;
            border-radius: var(--border-radius);
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
            min-height: 300px;
        }

        .story-content {
            font-style: italic;
            line-height: 1.8;
            padding: 20px;
            background: rgba(232, 214, 255, 0.15);
            border-left: 3px solid var(--accent-color);
        }

        .music-box {
            background: linear-gradient(135deg, #f0e6ff 0%, #e1d6ff 100%);
            padding: 30px;
            border-radius: var(--border-radius);
            text-align: center;
        }

        footer {
            text-align: center;
            margin-top: 60px;
            padding: 30px;
            color: var(--accent-color);
            font-size: 0.9rem;
            opacity: 0.8;
        }

        @media (max-width: 768px) {
            .tabs {
                flex-direction: column;
                align-items: center;
            }
            
            .tab {
                width: 90%;
                margin: 5px 0;
            }
            
            .tab-content {
                padding: 25px;
            }
            
            h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>「幽」</h1>
            <p class="subtitle">你我终将如夏日般永逝-写在寒秋之前</p>
        </header>

        <div class="tabs-container">
            <div class="tabs">
                <button class="tab active" data-tab="project">Project</button>
                <button class="tab" data-tab="inspiration">Inspiration</button>
                <button class="tab" data-tab="youstory">YOU story</button>
                <button class="tab" data-tab="novels">My novels</button>
                <button class="tab" data-tab="mymusic">MY Music</button>
            </div>
        </div>

        <div class="tab-content active" id="project">
            <h2 class="section-title">Project</h2>
            <div class="content-box">
                <p>一些项目</p>
                <p>一些项目</p>
                <p>一些项目</p>
            </div>
        </div>

        <div class="tab-content" id="inspiration">
            <h2 class="section-title">Inspiration</h2>
            <div class="content-box">
                <p>灵感1</p>
                <p>灵感2</p>
                <p>灵感3</p>
            </div>
        </div>

        <div class="tab-content" id="youstory">
            <h2 class="section-title">YOU story</h2>
            <div class="story-content">
                <p>幽的随记</p>
                <p>幽的随记</p>
                <p>幽的随记</p>
            </div>
        </div>

        <div class="tab-content" id="novels">
            <h2 class="section-title">My novels</h2>
            <div class="content-box">
                <p>小说草案1</p>
                <p>小说草案2</p>
                <p>小说草案3</p>
            </div>
        </div>

        <div class="tab-content" id="mymusic">
            <h2 class="section-title">MY Music</h2>
            <div class="music-box">
                <p>歌词1</p>
                <p>歌词2</p>
                <p>歌词3</p>
            </div>
        </div>

        <footer>
            <p>© 2025 幽 | 存活千年</p>
        </footer>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const tabs = document.querySelectorAll('.tab');
            const tabContents = document.querySelectorAll('.tab-content');

            tabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    // 移除所有 active 类
                    tabs.forEach(t => t.classList.remove('active'));
                    tabContents.forEach(content => content.classList.remove('active'));

                    // 添加 active 类到当前 tab
                    tab.classList.add('active');

                    // 显示对应的内容
                    const tabId = tab.getAttribute('data-tab');
                    document.getElementById(tabId).classList.add('active');
                });
            });

            // 初始化时激活第一个 tab
            tabs[0].click();
        });
    </script>
</body>
</html>
