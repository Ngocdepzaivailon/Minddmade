# Minddmade
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mindmate - Người bạn tâm lý tuổi teen</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800&family=Quicksand:wght@500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --primary: #6C63FF;
            --secondary: #4FC3F7;
            --accent: #FF6B6B;
            --success: #4CAF50;
            --warning: #FFD54F;
            --light: #F8F9FE;
            --dark: #344767;
            --purple-gradient: linear-gradient(135deg, #6C63FF 0%, #8A7CFF 100%);
            --blue-gradient: linear-gradient(135deg, #4FC3F7 0%, #29B6F6 100%);
            --pink-gradient: linear-gradient(135deg, #FF6B6B 0%, #FF8E8E 100%);
            --green-gradient: linear-gradient(135deg, #4CAF50 0%, #66BB6A 100%);
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Nunito', sans-serif;
            background: linear-gradient(135deg, #e0f7fa 0%, #f3e5f5 100%);
            min-height: 100vh;
            color: var(--dark);
            padding: 20px;
        }

        .app-container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 25px;
            box-shadow: var(--shadow);
            overflow: hidden;
            display: flex;
            flex-direction: column;
            height: 90vh;
        }

        /* Header */
        .header {
            background: var(--purple-gradient);
            color: white;
            padding: 20px 30px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            display: flex;
            align-items: center;
        }

        .logo-icon {
            width: 50px;
            height: 50px;
            background: white;
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .logo-icon i {
            font-size: 24px;
            color: var(--primary);
        }

        .logo-text h1 {
            font-size: 24px;
            font-weight: 800;
            font-family: 'Quicksand', sans-serif;
        }

        .logo-text p {
            font-size: 14px;
            opacity: 0.9;
        }

        .nav-buttons {
            display: flex;
        }

        .nav-btn {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            margin-left: 10px;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 18px;
            color: white;
            transition: all 0.3s;
        }

        .nav-btn:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: scale(1.1);
        }

        /* Main Content */
        .main-content {
            display: flex;
            flex: 1;
            overflow: hidden;
        }

        /* Sidebar */
        .sidebar {
            width: 300px;
            background: var(--light);
            border-right: 1px solid #e9ecef;
            padding: 20px;
            display: flex;
            flex-direction: column;
        }

        .user-profile {
            display: flex;
            align-items: center;
            padding: 15px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            margin-bottom: 20px;
        }

        .avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--blue-gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
            margin-right: 15px;
        }

        .user-info h2 {
            font-size: 18px;
            margin-bottom: 5px;
        }

        .user-info p {
            font-size: 14px;
            color: var(--dark);
            opacity: 0.7;
            display: flex;
            align-items: center;
        }

        .user-info p i {
            color: var(--success);
            margin-right: 5px;
            font-size: 12px;
        }

        .sidebar-menu {
            list-style: none;
            margin-top: 20px;
        }

        .menu-item {
            padding: 15px;
            border-radius: 12px;
            margin-bottom: 10px;
            cursor: pointer;
            display: flex;
            align-items: center;
            transition: all 0.3s;
        }

        .menu-item:hover, .menu-item.active {
            background: white;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            color: var(--primary);
        }

        .menu-item i {
            margin-right: 12px;
            font-size: 20px;
        }

        .menu-item span {
            font-weight: 600;
        }

        /* Content Area */
        .content-area {
            flex: 1;
            display: flex;
            flex-direction: column;
        }

        .tab-content {
            flex: 1;
            padding: 30px;
            overflow-y: auto;
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        /* Dashboard Tab */
        .dashboard-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 25px;
            color: var(--primary);
            display: flex;
            align-items: center;
        }

        .dashboard-title i {
            margin-right: 12px;
        }

        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
            margin-bottom: 30px;
        }

        .dashboard-card {
            background: white;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            padding: 25px;
            display: flex;
            flex-direction: column;
            transition: all 0.3s;
        }

        .dashboard-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .card-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .card-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
            margin-right: 15px;
        }

        .card-1 .card-icon { background: var(--purple-gradient); }
        .card-2 .card-icon { background: var(--blue-gradient); }
        .card-3 .card-icon { background: var(--pink-gradient); }

        .card-title {
            font-size: 18px;
            font-weight: 700;
        }

        .card-content {
            font-size: 36px;
            font-weight: 800;
            margin-bottom: 15px;
        }

        .card-footer {
            font-size: 14px;
            color: var(--dark);
            opacity: 0.7;
        }

        .chart-container {
            background: white;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            padding: 25px;
            margin-bottom: 30px;
        }

        .chart-title {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
        }

        .chart-title i {
            color: var(--primary);
            margin-right: 10px;
        }

        /* Mood Diary Tab */
        .mood-diary-container {
            background: white;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            padding: 25px;
            margin-bottom: 30px;
        }

        .calendar-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .calendar-title {
            font-size: 20px;
            font-weight: 700;
        }

        .calendar-navigation button {
            background: var(--light);
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            margin: 0 5px;
            cursor: pointer;
            font-size: 16px;
            color: var(--dark);
        }

        .calendar-grid {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 10px;
        }

        .calendar-day {
            height: 50px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .calendar-day:hover {
            background: var(--light);
        }

        .calendar-day.active {
            background: var(--purple-gradient);
            color: white;
        }

        .day-name {
            font-size: 12px;
            opacity: 0.7;
            margin-bottom: 5px;
        }

        .mood-selector {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
        }

        .mood-option {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 15px;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s;
            width: 18%;
        }

        .mood-option:hover {
            background: var(--light);
        }

        .mood-option.active {
            background: white;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .mood-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            margin-bottom: 10px;
        }

        .mood-1 .mood-icon { background: #FF6B6B; color: white; }
        .mood-2 .mood-icon { background: #FFD54F; color: white; }
        .mood-3 .mood-icon { background: #4FC3F7; color: white; }
        .mood-4 .mood-icon { background: #66BB6A; color: white; }
        .mood-5 .mood-icon { background: #8A7CFF; color: white; }

        .mood-name {
            font-size: 14px;
            font-weight: 600;
        }

        /* Chat Tab */
        .chat-container {
            display: flex;
            flex-direction: column;
            height: 100%;
        }

        .chat-header {
            padding: 20px;
            background: white;
            border-bottom: 1px solid #e9ecef;
            display: flex;
            align-items: center;
        }

        .assistant-info {
            display: flex;
            align-items: center;
        }

        .assistant-avatar {
            width: 50px;
            height: 50px;
            border-radius: 15px;
            background: var(--blue-gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 22px;
            color: white;
            margin-right: 15px;
        }

        .assistant-details h2 {
            color: var(--primary);
            font-size: 20px;
            font-weight: 700;
        }

        .assistant-details p {
            font-size: 14px;
            color: var(--dark);
            opacity: 0.7;
            display: flex;
            align-items: center;
        }

        .assistant-details p i {
            color: var(--success);
            margin-right: 5px;
        }

        .chat-messages {
            flex: 1;
            padding: 25px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            background: #fafbfd;
        }

        .message {
            max-width: 75%;
            padding: 18px;
            margin-bottom: 20px;
            border-radius: 20px;
            position: relative;
            animation: fadeIn 0.4s;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            display: flex;
            flex-direction: column;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .bot-message {
            align-self: flex-start;
            background: white;
            border: 1px solid #e0e6ef;
            border-bottom-left-radius: 5px;
        }

        .user-message {
            align-self: flex-end;
            background: var(--primary);
            color: white;
            border-bottom-right-radius: 5px;
        }

        .message-content {
            line-height: 1.6;
            font-size: 16px;
        }

        .message-time {
            font-size: 12px;
            opacity: 0.7;
            margin-top: 10px;
            text-align: right;
        }

        .user-message .message-time {
            color: rgba(255, 255, 255, 0.8);
        }

        .chat-input-container {
            padding: 20px;
            display: flex;
            align-items: center;
            background: white;
            border-top: 1px solid #e9ecef;
        }

        .chat-input-wrapper {
            flex: 1;
            position: relative;
        }

        .chat-input {
            width: 100%;
            padding: 16px 20px;
            padding-right: 50px;
            border: 1px solid #e0e6ef;
            border-radius: 30px;
            font-size: 16px;
            outline: none;
            transition: all 0.3s;
            background: var(--light);
        }

        .chat-input:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(108, 99, 255, 0.2);
        }

        .emoji-btn {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            color: var(--dark);
            font-size: 20px;
            cursor: pointer;
        }

        .send-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--primary);
            color: white;
            border: none;
            margin-left: 15px;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 20px;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(108, 99, 255, 0.3);
        }

        .send-btn:hover {
            background: #5a52e0;
            transform: scale(1.05);
        }

        /* Resources Tab */
        .resources-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
        }

        .resource-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: all 0.3s;
        }

        .resource-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .resource-image {
            height: 160px;
            background-size: cover;
            background-position: center;
        }

        .resource-content {
            padding: 20px;
        }

        .resource-category {
            display: inline-block;
            padding: 5px 12px;
            border-radius: 20px;
            background: var(--light);
            color: var(--primary);
            font-size: 12px;
            font-weight: 600;
            margin-bottom: 12px;
        }

        .resource-title {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .resource-desc {
            font-size: 14px;
            color: var(--dark);
            opacity: 0.8;
            margin-bottom: 15px;
        }

        .resource-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .resource-duration {
            font-size: 13px;
            color: var(--dark);
            opacity: 0.7;
            display: flex;
            align-items: center;
        }

        .resource-duration i {
            margin-right: 5px;
        }

        .resource-link {
            color: var(--primary);
            font-weight: 600;
            font-size: 14px;
            text-decoration: none;
        }

        /* Emergency Tab */
        .emergency-card {
            background: white;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            padding: 30px;
            margin-bottom: 30px;
        }

        .emergency-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 20px;
            color: var(--accent);
            display: flex;
            align-items: center;
        }

        .emergency-title i {
            margin-right: 12px;
        }

        .emergency-text {
            margin-bottom: 25px;
            line-height: 1.7;
        }

        .contacts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }

        .contact-card {
            background: var(--light);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s;
        }

        .contact-card:hover {
            background: white;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .contact-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--pink-gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
            margin: 0 auto 15px;
        }

        .contact-name {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .contact-phone {
            font-size: 20px;
            font-weight: 800;
            color: var(--accent);
            margin-bottom: 15px;
            text-decoration: none;
            display: block;
        }

        .contact-btn {
            display: inline-block;
            padding: 10px 20px;
            background: var(--accent);
            color: white;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
        }

        .contact-btn:hover {
            background: #ff5252;
            transform: translateY(-2px);
        }

        /* Footer */
        .footer {
            padding: 15px 30px;
            background: var(--light);
            border-top: 1px solid #e9ecef;
            text-align: center;
            font-size: 14px;
            color: var(--dark);
            opacity: 0.7;
        }

        /* Responsive */
        @media (max-width: 992px) {
            .dashboard-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            .main-content {
                flex-direction: column;
            }

            .sidebar {
                width: 100%;
                border-right: none;
                border-bottom: 1px solid #e9ecef;
            }

            .dashboard-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="app-container">
        <!-- Header -->
        <div class="header">
            <div class="logo">
                <div class="logo-icon">
                    <i class="fas fa-brain"></i>
                </div>
                <div class="logo-text">
                    <h1>Mindmate</h1>
                    <p>Người bạn tâm lý tuổi teen</p>
                </div>
            </div>
            <div class="nav-buttons">
                <button class="nav-btn"><i class="fas fa-bell"></i></button>
                <button class="nav-btn"><i class="fas fa-cog"></i></button>
                <button class="nav-btn"><i class="fas fa-user"></i></button>
            </div>
        </div>

        <!-- Main Content -->
        <div class="main-content">
            <!-- Sidebar -->
            <div class="sidebar">
                <div class="user-profile">
                    <div class="avatar">
                        <i class="fas fa-user"></i>
                    </div>
                    <div class="user-info">
                        <h2>Nguyễn Văn A</h2>
                        <p><i class="fas fa-circle"></i> Tâm trạng: Bình thường</p>
                    </div>
                </div>

                <ul class="sidebar-menu">
                    <li class="menu-item active" data-tab="dashboard">
                        <i class="fas fa-home"></i>
                        <span>Trang chủ</span>
                    </li>
                    <li class="menu-item" data-tab="mood">
                        <i class="fas fa-smile"></i>
                        <span>Nhật ký cảm xúc</span>
                    </li>
                    <li class="menu-item" data-tab="chat">
                        <i class="fas fa-comments"></i>
                        <span>Trò chuyện với Mindy</span>
                    </li>
                    <li class="menu-item" data-tab="resources">
                        <i class="fas fa-book"></i>
                        <span>Tài nguyên sức khỏe</span>
                    </li>
                    <li class="menu-item" data-tab="tests">
                        <i class="fas fa-clipboard-list"></i>
                        <span>Bài kiểm tra tâm lý</span>
                    </li>
                    <li class="menu-item" data-tab="emergency">
                        <i class="fas fa-life-ring"></i>
                        <span>Hỗ trợ khẩn cấp</span>
                    </li>
                    <li class="menu-item" data-tab="goals">
                        <i class="fas fa-bullseye"></i>
                        <span>Mục tiêu cá nhân</span>
                    </li>
                </ul>
            </div>

            <!-- Content Area -->
            <div class="content-area">
                <!-- Dashboard Tab -->
                <div class="tab-content active" id="dashboard">
                    <h1 class="dashboard-title"><i class="fas fa-home"></i> Trang chủ</h1>
                    
                    <div class="dashboard-grid">
                        <div class="dashboard-card card-1">
                            <div class="card-header">
                                <div class="card-icon">
                                    <i class="fas fa-smile"></i>
                                </div>
                                <div class="card-title">Tâm trạng hôm nay</div>
                            </div>
                            <div class="card-content">Bình thường</div>
                            <div class="card-footer">Cập nhật 2 giờ trước</div>
                        </div>
                        
                        <div class="dashboard-card card-2">
                            <div class="card-header">
                                <div class="card-icon">
                                    <i class="fas fa-fire"></i>
                                </div>
                                <div class="card-title">Số ngày liên tiếp</div>
                            </div>
                            <div class="card-content">7</div>
                            <div class="card-footer">Bạn đang làm rất tốt!</div>
                        </div>
                        
                        <div class="dashboard-card card-3">
                            <div class="card-header">
                                <div class="card-icon">
                                    <i class="fas fa-tasks"></i>
                                </div>
                                <div class="card-title">Mục tiêu hoàn thành</div>
                            </div>
                            <div class="card-content">3/5</div>
                            <div class="card-footer">Tiếp tục phát huy nhé!</div>
                        </div>
                    </div>
                    
                    <div class="chart-container">
                        <div class="chart-title"><i class="fas fa-chart-line"></i> Biểu đồ cảm xúc 7 ngày qua</div>
                        <canvas id="moodChart"></canvas>
                    </div>
                    
                    <div class="chart-container">
                        <div class="chart-title"><i class="fas fa-lightbulb"></i> Hoạt động đề xuất hôm nay</div>
                        <div class="activities-grid">
                            <div class="activity">
                                <i class="fas fa-spa"></i>
                                <span>Thiền 5 phút</span>
                            </div>
                            <div class="activity">
                                <i class="fas fa-book"></i>
                                <span>Đọc 10 trang sách</span>
                            </div>
                            <div class="activity">
                                <i class="fas fa-music"></i>
                                <span>Nghe nhạc thư giãn</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Mood Diary Tab -->
                <div class="tab-content" id="mood">
                    <h1 class="dashboard-title"><i class="fas fa-smile"></i> Nhật ký cảm xúc</h1>
                    
                    <div class="mood-diary-container">
                        <div class="calendar-header">
                            <div class="calendar-title">Tháng 10, 2023</div>
                            <div class="calendar-navigation">
                                <button><i class="fas fa-chevron-left"></i></button>
                                <button><i class="fas fa-chevron-right"></i></button>
                            </div>
                        </div>
                        
                        <div class="calendar-grid">
                            <div class="calendar-day">
                                <div class="day-name">T2</div>
                                <div>1</div>
                            </div>
                            <div class="calendar-day">
                                <div class="day-name">T3</div>
                                <div>2</div>
                            </div>
                            <div class="calendar-day">
                                <div class="day-name">T4</div>
                                <div>3</div>
                            </div>
                            <div class="calendar-day">
                                <div class="day-name">T5</div>
                                <div>4</div>
                            </div>
                            <div class="calendar-day">
                                <div class="day-name">T6</div>
                                <div>5</div>
                            </div>
                            <div class="calendar-day">
                                <div class="day-name">T7</div>
                                <div>6</div>
                            </div>
                            <div class="calendar-day">
                                <div class="day-name">CN</div>
                                <div>7</div>
                            </div>
                            
                            <!-- More days would go here -->
                        </div>
                        
                        <div class="mood-selector">
                            <div class="mood-option mood-1">
                                <div class="mood-icon"><i class="fas fa-sad-tear"></i></div>
                                <div class="mood-name">Rất tệ</div>
                            </div>
                            <div class="mood-option mood-2">
                                <div class="mood-icon"><i class="fas fa-frown"></i></div>
                                <div class="mood-name">Không tốt</div>
                            </div>
                            <div class="mood-option mood-3 active">
                                <div class="mood-icon"><i class="fas fa-meh"></i></div>
                                <div class="mood-name">Bình thường</div>
                            </div>
                            <div class="mood-option mood-4">
                                <div class="mood-icon"><i class="fas fa-smile"></i></div>
                                <div class="mood-name">Khá tốt</div>
                            </div>
                            <div class="mood-option mood-5">
                                <div class="mood-icon"><i class="fas fa-laugh"></i></div>
                                <div class="mood-name">Tuyệt vời</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="chart-container">
                        <div class="chart-title"><i class="fas fa-chart-bar"></i> Thống kê cảm xúc tháng này</div>
                        <canvas id="moodStatsChart"></canvas>
                    </div>
                </div>
                
                <!-- Chat Tab -->
                <div class="tab-content" id="chat">
                    <div class="chat-container">
                        <div class="chat-header">
                            <div class="assistant-info">
                                <div class="assistant-avatar">
                                    <i class="fas fa-robot"></i>
                                </div>
                                <div class="assistant-details">
                                    <h2>Mindy - Trợ lý tâm lý</h2>
                                    <p><i class="fas fa-circle"></i> Đang trực tuyến</p>
                                </div>
                            </div>
                        </div>
                        
                        <div class="chat-messages" id="chat-messages">
                            <div class="message bot-message">
                                <div class="message-content">
                                    Chào bạn! Mình là Mindy - trợ lý tâm lý của bạn 😊<br>
                                    Hôm nay bạn cảm thấy thế nào? Mình luôn sẵn sàng lắng nghe và hỗ trợ bạn.
                                </div>
                                <div class="message-time">10:00 AM</div>
                            </div>
                            
                            <div class="message user-message">
                                <div class="message-content">
                                    Chào Mindy, hôm nay mình cảm thấy khá mệt mỏi và căng thẳng.
                                </div>
                                <div class="message-time">10:02 AM</div>
                            </div>
                            
                            <div class="message bot-message">
                                <div class="message-content">
                                    Mình rất tiếc khi nghe bạn đang cảm thấy như vậy 😔<br><br>
                                    Bạn có thể chia sẻ thêm về nguyên nhân khiến bạn căng thẳng không? 
                                    Đôi khi nói ra những điều trong lòng có thể giúp chúng ta cảm thấy nhẹ nhõm hơn.
                                </div>
                                <div class="message-time">10:03 AM</div>
                            </div>
                        </div>
                        
                        <div class="chat-input-container">
                            <div class="chat-input-wrapper">
                                <input type="text" class="chat-input" id="user-input" placeholder="Viết tin nhắn của bạn...">
                                <button class="emoji-btn">
                                    <i class="far fa-smile"></i>
                                </button>
                            </div>
                            <button class="send-btn" id="send-btn">
                                <i class="fas fa-paper-plane"></i>
                            </button>
                        </div>
                    </div>
                </div>
                
                <!-- Resources Tab -->
                <div class="tab-content" id="resources">
                    <h1 class="dashboard-title"><i class="fas fa-book"></i> Tài nguyên sức khỏe tâm thần</h1>
                    
                    <div class="resources-grid">
                        <div class="resource-card">
                            <div class="resource-image" style="background-image: url('https://images.unsplash.com/photo-1506126613408-eca07ce68773?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');"></div>
                            <div class="resource-content">
                                <div class="resource-category">Kỹ năng đối phó</div>
                                <div class="resource-title">7 Kỹ thuật giảm căng thẳng tức thì</div>
                                <div class="resource-desc">Hướng dẫn các phương pháp đơn giản giúp bạn giảm căng thẳng ngay lập tức trong các tình huống khó khăn.</div>
                                <div class="resource-footer">
                                    <div class="resource-duration"><i class="fas fa-clock"></i> 5 phút</div>
                                    <a href="#" class="resource-link">Xem ngay</a>
                                </div>
                            </div>
                        </div>
                        
                        <div class="resource-card">
                            <div class="resource-image" style="background-image: url('https://images.unsplash.com/photo-1491897554428-130a60dd4757?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');"></div>
                            <div class="resource-content">
                                <div class="resource-category">Thiền định</div>
                                <div class="resource-title">Hướng dẫn thiền cho người mới bắt đầu</div>
                                <div class="resource-desc">Khám phá sức mạnh của thiền định với loạt bài hướng dẫn dành cho người mới bắt đầu.</div>
                                <div class="resource-footer">
                                    <div class="resource-duration"><i class="fas fa-clock"></i> 10 phút</div>
                                    <a href="#" class="resource-link">Xem ngay</a>
                                </div>
                            </div>
                        </div>
                        
                        <div class="resource-card">
                            <div class="resource-image" style="background-image: url('https://images.unsplash.com/photo-1544367567-0f2fcb009e0b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');"></div>
                            <div class="resource-content">
                                <div class="resource-category">Tự chăm sóc</div>
                                <div class="resource-title">Xây dựng thói quen tự chăm sóc bản thân</div>
                                <div class="resource-desc">Các bước đơn giản để xây dựng thói quen tự chăm sóc bản thân mỗi ngày.</div>
                                <div class="resource-footer">
                                    <div class="resource-duration"><i class="fas fa-clock"></i> 8 phút</div>
                                    <a href="#" class="resource-link">Xem ngay</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Emergency Tab -->
                <div class="tab-content" id="emergency">
                    <h1 class="dashboard-title"><i class="fas fa-life-ring"></i> Hỗ trợ khẩn cấp</h1>
                    
                    <div class="emergency-card">
                        <div class="emergency-title"><i class="fas fa-exclamation-triangle"></i> Bạn đang gặp khủng hoảng?</div>
                        <div class="emergency-text">
                            <p>Nếu bạn đang có cảm giác muốn làm hại bản thân hoặc người khác, hoặc đang trải qua một cơn khủng hoảng tâm lý nghiêm trọng, hãy liên hệ ngay với các dịch vụ hỗ trợ khẩn cấp dưới đây. Có những người luôn sẵn sàng lắng nghe và giúp đỡ bạn.</p>
                            <p>Bạn không cô đơn trong hành trình này. Hãy mạnh dạn tìm kiếm sự giúp đỡ khi bạn cần.</p>
                        </div>
                        
                        <div class="contacts-grid">
                            <div class="contact-card">
                                <div class="contact-icon">
                                    <i class="fas fa-phone-alt"></i>
                                </div>
                                <div class="contact-name">Tổng đài Quốc gia</div>
                                <a href="tel:111" class="contact-phone">111</a>
                                <p>Bảo vệ Trẻ em</p>
                                <a href="#" class="contact-btn">Gọi ngay</a>
                            </div>
                            
                            <div class="contact-card">
                                <div class="contact-icon">
                                    <i class="fas fa-hands-helping"></i>
                                </div>
                                <div class="contact-name">Ngày mai tươi sáng</div>
                                <a href="tel:1900633069" class="contact-phone">1900 633 069</a>
                                <p>Hỗ trợ tâm lý</p>
                                <a href="#" class="contact-btn">Gọi ngay</a>
                            </div>
                            
                            <div class="contact-card">
                                <div class="contact-icon">
                                    <i class="fas fa-heart"></i>
                                </div>
                                <div class="contact-name">Trung tâm Pháp y Tâm thần</div>
                                <a href="tel:02437363731" class="contact-phone">(024) 3736 3731</a>
                                <p>Khu vực miền Bắc</p>
                                <a href="#" class="contact-btn">Gọi ngay</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>Mindmate - Người bạn tâm lý tuổi teen | © 2023 Bản quyền thuộc về Mindmate</p>
        </div>
    </div>

    <script>
        // Tab switching
        document.addEventListener('DOMContentLoaded', function() {
            const menuItems = document.querySelectorAll('.menu-item');
            const tabContents = document.querySelectorAll('.tab-content');
            
            menuItems.forEach(item => {
                item.addEventListener('click', function() {
                    const tabId = this.getAttribute('data-tab');
                    
                    // Remove active class from all items and contents
                    menuItems.forEach(i => i.classList.remove('active'));
                    tabContents.forEach(c => c.classList.remove('active'));
                    
                    // Add active class to current item and content
                    this.classList.add('active');
                    document.getElementById(tabId).classList.add('active');
                });
            });
            
            // Mood Chart
            const moodCtx = document.getElementById('moodChart').getContext('2d');
            const moodChart = new Chart(moodCtx, {
                type: 'line',
                data: {
                    labels: ['T2', 'T3', 'T4', 'T5', 'T6', 'T7', 'CN'],
                    datasets: [{
                        label: 'Mức độ hạnh phúc',
                        data: [3, 4, 3, 5, 4, 2, 4],
                        backgroundColor: 'rgba(108, 99, 255, 0.1)',
                        borderColor: '#6C63FF',
                        borderWidth: 3,
                        tension: 0.3,
                        pointBackgroundColor: '#6C63FF',
                        pointRadius: 5
                    }]
                },
                options: {
                    responsive: true,
                    scales: {
                        y: {
                            min: 1,
                            max: 5,
                            ticks: {
                                stepSize: 1,
                                callback: function(value) {
                                    const moods = ['', 'Rất tệ', 'Tệ', 'Bình thường', 'Tốt', 'Rất tốt'];
                                    return moods[value];
                                }
                            }
                        }
                    }
                }
            });
            
            // Mood Stats Chart
            const moodStatsCtx = document.getElementById('moodStatsChart').getContext('2d');
            const moodStatsChart = new Chart(moodStatsCtx, {
                type: 'bar',
                data: {
                    labels: ['Rất tệ', 'Tệ', 'Bình thường', 'Tốt', 'Rất tốt'],
                    datasets: [{
                        label: 'Số ngày',
                        data: [2, 3, 15, 7, 3],
                        backgroundColor: [
                            '#FF6B6B',
                            '#FFD54F',
                            '#4FC3F7',
                            '#66BB6A',
                            '#8A7CFF'
                        ]
                    }]
                },
                options: {
                    responsive: true
                }
            });
            
            // Chat functionality
            const chatMessages = document.getElementById('chat-messages');
            const userInput = document.getElementById('user-input');
            const sendBtn = document.getElementById('send-btn');
            
            function sendMessage() {
                const message = userInput.value.trim();
                if (message) {
                    addUserMessage(message);
                    userInput.value = '';
                    
                    // Simulate bot response after a delay
                    setTimeout(() => {
                        generateBotResponse(message);
                    }, 1000);
                }
            }
            
            function addUserMessage(text) {
                const messageDiv = document.createElement('div');
                messageDiv.classList.add('message', 'user-message');
                messageDiv.innerHTML = `
                    <div class="message-content">${text}</div>
                    <div class="message-time">${getCurrentTime()}</div>
                `;
                chatMessages.appendChild(messageDiv);
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
            
            function addBotMessage(text) {
                const messageDiv = document.createElement('div');
                messageDiv.classList.add('message', 'bot-message');
                messageDiv.innerHTML = `
                    <div class="message-content">${text}</div>
                    <div class="message-time">${getCurrentTime()}</div>
                `;
                chatMessages.appendChild(messageDiv);
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
            
            function generateBotResponse(userMessage) {
                userMessage = userMessage.toLowerCase();
                let response = '';
                
                if (userMessage.includes('buồn') || userMessage.includes('tồi tệ') || 
                    userMessage.includes('chán') || userMessage.includes('mệt mỏi')) {
                    response = "Mình hiểu cảm giác đó có thể rất khó khăn. Bạn đã trải qua điều này bao lâu rồi? Mình có một số bài tập thư giãn có thể giúp bạn, bạn có muốn thử không? 😊";
                } 
                else if (userMessage.includes('căng thẳng') || userMessage.includes('stress')) {
                    response = "Căng thẳng là phản ứng tự nhiên, nhưng chúng ta có thể học cách quản lý nó. Mình gợi ý bạn thử kỹ thuật thở 4-7-8:<br><br>💨 <strong>Hít vào</strong> từ từ bằng mũi trong 4 giây<br>⏳ <strong>Giữ hơi</strong> thở trong 7 giây<br>😮‍💨 <strong>Thở ra</strong> từ từ bằng miệng trong 8 giây<br><br>Lặp lại 4 lần. Bạn muốn mình hướng dẫn bạn qua từng bước không?";
                }
                else if (userMessage.includes('lo lắng') || userMessage.includes('bồn chồn')) {
                    response = "Khi cảm thấy lo lắng, bạn có thể thử phương pháp 'grounding' để kết nối với hiện tại:<br><br>👀 <strong>Nhìn</strong>: Tìm 5 vật bạn có thể nhìn thấy<br>✋ <strong>Chạm</strong>: Tìm 4 vật bạn có thể chạm vào<br>👂 <strong>Nghe</strong>: Lắng nghe 3 âm thanh xung quanh<br>👃 <strong>Ngửi</strong>: Nhận biết 2 mùi hương<br>👅 <strong>Nếm</strong>: Cảm nhận 1 vị giác trong miệng<br><br>Kỹ thuật này giúp đưa tâm trí bạn trở lại hiện tại. Bạn có muốn thử ngay bây giờ không?";
                }
                else if (userMessage.includes('cảm ơn') || userMessage.includes('thanks')) {
                    response = "Luôn hạnh phúc khi được hỗ trợ bạn! 😊 Nếu có bất cứ điều gì bạn muốn chia sẻ thêm, mình luôn sẵn sàng lắng nghe. Bạn có muốn thử một bài tập thư giãn nhỏ không?";
                }
                else {
                    const responses = [
                        "Mình hiểu bạn đang muốn chia sẻ điều gì đó quan trọng. Bạn có thể nói thêm cho mình biết chi tiết hơn không?",
                        "Cảm ơn bạn đã tin tưởng chia sẻ. Mình đang lắng nghe và muốn hiểu rõ hơn về tình huống của bạn.",
                        "Mỗi người trải qua những khó khăn khác nhau. Bạn đang cảm thấy thế nào về tình huống này?",
                        "Chia sẻ cảm xúc là bước đầu tiên quan trọng. Bạn có muốn nói thêm về những gì đang xảy ra không?",
                        "Mình ở đây để hỗ trợ bạn. Hãy cho mình biết thêm chi tiết để mình có thể giúp tốt hơn nhé!"
                    ];
                    response = responses[Math.floor(Math.random() * responses.length)];
                }
                
                addBotMessage(response);
            }
            
            function getCurrentTime() {
                const now = new Date();
                return now.getHours().toString().padStart(2, '0') + ':' + 
                       now.getMinutes().toString().padStart(2, '0');
            }
            
            sendBtn.addEventListener('click', sendMessage);
            userInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    sendMessage();
                }
            });
        });
    </script>
</body>
</html>
