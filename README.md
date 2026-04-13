<!DOCTYPE html>
<html lang="mn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мөст сумын ЕБС - Дүнгийн систем</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #1a5276;
            --primary-light: #2980b9;
            --primary-dark: #0e2f44;
            --accent: #e67e22;
            --success: #27ae60;
            --danger: #e74c3c;
            --warning: #f39c12;
            --bg: #f0f4f8;
            --card: #ffffff;
            --text: #2c3e50;
            --text-light: #7f8c8d;
            --border: #dce1e6;
            --shadow: 0 4px 20px rgba(0,0,0,0.08);
            --shadow-hover: 0 8px 30px rgba(0,0,0,0.12);
            --radius: 12px;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: var(--bg);
            color: var(--text);
            min-height: 100vh;
        }

        /* ===== HEADER ===== */
        .header {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary), var(--primary-light));
            color: white;
            padding: 0;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-top {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 12px 24px;
            flex-wrap: wrap;
            gap: 10px;
        }

        .school-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .school-logo {
            width: 55px;
            height: 55px;
            background: rgba(255,255,255,0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 28px;
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255,255,255,0.3);
        }

        .school-name h1 {
            font-size: 1.2em;
            font-weight: 700;
            letter-spacing: 0.5px;
        }

        .school-name p {
            font-size: 0.8em;
            opacity: 0.85;
            margin-top: 2px;
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .user-badge {
            background: rgba(255,255,255,0.15);
            padding: 8px 16px;
            border-radius: 25px;
            font-size: 0.85em;
            backdrop-filter: blur(10px);
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .user-badge .role-icon {
            font-size: 1.1em;
        }

        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.9em;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            text-decoration: none;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .btn:active {
            transform: translateY(0);
        }

        .btn-primary {
            background: var(--primary-light);
            color: white;
        }

        .btn-accent {
            background: var(--accent);
            color: white;
        }

        .btn-success {
            background: var(--success);
            color: white;
        }

        .btn-danger {
            background: var(--danger);
            color: white;
        }

        .btn-outline {
            background: rgba(255,255,255,0.15);
            color: white;
            border: 1px solid rgba(255,255,255,0.3);
        }

        .btn-outline:hover {
            background: rgba(255,255,255,0.25);
        }

        .btn-sm {
            padding: 6px 14px;
            font-size: 0.8em;
        }

        .btn-lg {
            padding: 14px 32px;
            font-size: 1em;
        }

        /* ===== LOGIN PAGE ===== */
        .login-page {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
        }

        .login-container {
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
            width: 100%;
            max-width: 900px;
            display: flex;
            min-height: 550px;
        }

        .login-left {
            flex: 1;
            background: linear-gradient(135deg, var(--primary-dark), var(--primary));
            color: white;
            padding: 50px 40px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        .login-left .big-logo {
            font-size: 80px;
            margin-bottom: 20px;
            filter: drop-shadow(0 4px 8px rgba(0,0,0,0.3));
        }

        .login-left h2 {
            font-size: 1.6em;
            margin-bottom: 10px;
        }

        .login-left p {
            opacity: 0.8;
            font-size: 0.95em;
            line-height: 1.6;
        }

        .login-right {
            flex: 1;
            padding: 50px 40px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .login-right h3 {
            font-size: 1.5em;
            margin-bottom: 8px;
            color: var(--primary);
        }

        .login-right .subtitle {
            color: var(--text-light);
            margin-bottom: 30px;
            font-size: 0.9em;
        }

        .tab-switcher {
            display: flex;
            background: var(--bg);
            border-radius: 10px;
            padding: 4px;
            margin-bottom: 25px;
        }

        .tab-switcher button {
            flex: 1;
            padding: 10px;
            border: none;
            background: transparent;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.9em;
            color: var(--text-light);
            transition: all 0.3s;
        }

        .tab-switcher button.active {
            background: white;
            color: var(--primary);
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 18px;
        }

        .form-group label {
            display: block;
            margin-bottom: 6px;
            font-weight: 600;
            font-size: 0.85em;
            color: var(--text);
        }

        .form-group input,
        .form-group select {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid var(--border);
            border-radius: 10px;
            font-size: 0.95em;
            transition: all 0.3s;
            background: var(--bg);
        }

        .form-group input:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--primary-light);
            background: white;
            box-shadow: 0 0 0 4px rgba(41,128,185,0.1);
        }

        .gmail-input-group {
            display: flex;
            gap: 8px;
        }

        .gmail-input-group input {
            flex: 1;
        }

        .gmail-btn {
            padding: 12px 16px;
            background: #db4437;
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1.1em;
            transition: all 0.3s;
            white-space: nowrap;
        }

        .gmail-btn:hover {
            background: #c23326;
            transform: scale(1.05);
        }

        .divider {
            display: flex;
            align-items: center;
            margin: 20px 0;
            color: var(--text-light);
            font-size: 0.85em;
        }

        .divider::before,
        .divider::after {
            content: '';
            flex: 1;
            height: 1px;
            background: var(--border);
        }

        .divider span {
            padding: 0 15px;
        }

        .login-btn {
            width: 100%;
            padding: 14px;
            background: linear-gradient(135deg, var(--primary), var(--primary-light));
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 1em;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
        }

        .login-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(26,82,118,0.4);
        }

        .error-msg {
            background: #fde8e8;
            color: var(--danger);
            padding: 10px 14px;
            border-radius: 8px;
            font-size: 0.85em;
            margin-bottom: 15px;
            display: none;
            align-items: center;
            gap: 8px;
        }

        .success-msg {
            background: #e8fde8;
            color: var(--success);
            padding: 10px 14px;
            border-radius: 8px;
            font-size: 0.85em;
            margin-bottom: 15px;
            display: none;
            align-items: center;
            gap: 8px;
        }

        /* ===== MAIN LAYOUT ===== */
        .main-layout {
            display: flex;
            min-height: calc(100vh - 80px);
        }

        /* ===== SIDEBAR ===== */
        .sidebar {
            width: 260px;
            background: white;
            box-shadow: 2px 0 15px rgba(0,0,0,0.05);
            padding: 20px 0;
            flex-shrink: 0;
        }

        .sidebar-menu {
            list-style: none;
        }

        .sidebar-menu li {
            margin-bottom: 2px;
        }

        .sidebar-menu a {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 12px 24px;
            color: var(--text);
            text-decoration: none;
            font-size: 0.9em;
            font-weight: 500;
            transition: all 0.3s;
            border-left: 3px solid transparent;
        }

        .sidebar-menu a:hover {
            background: var(--bg);
            color: var(--primary);
        }

        .sidebar-menu a.active {
            background: rgba(41,128,185,0.08);
            color: var(--primary);
            border-left-color: var(--primary);
            font-weight: 600;
        }

        .sidebar-menu a .menu-icon {
            font-size: 1.2em;
            width: 24px;
            text-align: center;
        }

        .sidebar-section {
            padding: 15px 24px 8px;
            font-size: 0.75em;
            font-weight: 700;
            text-transform: uppercase;
            color: var(--text-light);
            letter-spacing: 1px;
        }

        /* ===== CONTENT ===== */
        .content {
            flex: 1;
            padding: 24px;
            overflow-y: auto;
        }

        .page-header {
            margin-bottom: 24px;
        }

        .page-header h2 {
            font-size: 1.5em;
            color: var(--primary-dark);
            margin-bottom: 4px;
        }

        .page-header p {
            color: var(--text-light);
            font-size: 0.9em;
        }

        /* ===== CARDS ===== */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 16px;
            margin-bottom: 24px;
        }

        .stat-card {
            background: white;
            border-radius: var(--radius);
            padding: 20px;
            box-shadow: var(--shadow);
            display: flex;
            align-items: center;
            gap: 16px;
            transition: all 0.3s;
        }

        .stat-card:hover {
            box-shadow: var(--shadow-hover);
            transform: translateY(-3px);
        }

        .stat-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5em;
        }

        .stat-icon.blue { background: rgba(41,128,185,0.1); color: var(--primary-light); }
        .stat-icon.green { background: rgba(39,174,96,0.1); color: var(--success); }
        .stat-icon.orange { background: rgba(230,126,34,0.1); color: var(--accent); }
        .stat-icon.red { background: rgba(231,76,60,0.1); color: var(--danger); }

        .stat-info h4 {
            font-size: 1.4em;
            color: var(--text);
        }

        .stat-info p {
            font-size: 0.8em;
            color: var(--text-light);
        }

        .card {
            background: white;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            overflow: hidden;
            margin-bottom: 20px;
        }

        .card-header {
            padding: 18px 24px;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 10px;
        }

        .card-header h3 {
            font-size: 1.1em;
            color: var(--primary-dark);
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .card-body {
            padding: 24px;
        }

        /* ===== TABLES ===== */
        .table-container {
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        table th,
        table td {
            padding: 12px 16px;
            text-align: left;
            border-bottom: 1px solid var(--border);
            font-size: 0.9em;
        }

        table th {
            background: var(--bg);
            font-weight: 700;
            color: var(--primary-dark);
            font-size: 0.8em;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            position: sticky;
            top: 0;
        }

        table tr:hover {
            background: rgba(41,128,185,0.03);
        }

        table tr:last-child td {
            border-bottom: none;
        }

        /* ===== GRADE BADGES ===== */
        .grade-badge {
            display: inline-block;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.8em;
            font-weight: 700;
        }

        .grade-excellent { background: #e8f5e9; color: #2e7d32; }
        .grade-good { background: #e3f2fd; color: #1565c0; }
        .grade-average { background: #fff3e0; color: #e65100; }
        .grade-poor { background: #ffebee; color: #c62828; }

        /* ===== MODAL ===== */
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            padding: 20px;
            backdrop-filter: blur(4px);
        }

        .modal-overlay.active {
            display: flex;
        }

        .modal {
            background: white;
            border-radius: 16px;
            width: 100%;
            max-width: 600px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            animation: modalIn 0.3s ease;
        }

        @keyframes modalIn {
            from { opacity: 0; transform: scale(0.9) translateY(20px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        .modal-header {
            padding: 20px 24px;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .modal-header h3 {
            font-size: 1.1em;
            color: var(--primary-dark);
        }

        .modal-close {
            width: 36px;
            height: 36px;
            border: none;
            background: var(--bg);
            border-radius: 50%;
            cursor: pointer;
            font-size: 1.2em;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .modal-close:hover {
            background: var(--danger);
            color: white;
        }

        .modal-body {
            padding: 24px;
        }

        .modal-footer {
            padding: 16px 24px;
            border-top: 1px solid var(--border);
            display: flex;
            justify-content: flex-end;
            gap: 10px;
        }

        /* ===== FORMS INSIDE MODAL ===== */
        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
        }

        /* ===== STUDENT VIEW ===== */
        .student-score-card {
            background: linear-gradient(135deg, var(--primary), var(--primary-light));
            color: white;
            border-radius: 16px;
            padding: 30px;
            margin-bottom: 24px;
            text-align: center;
        }

        .student-score-card .student-name {
            font-size: 1.3em;
            font-weight: 700;
            margin-bottom: 5px;
        }

        .student-score-card .student-id {
            opacity: 0.8;
            font-size: 0.9em;
        }

        .student-score-card .avg-score {
            font-size: 3em;
            font-weight: 800;
            margin: 15px 0 5px;
        }

        .student-score-card .avg-label {
            opacity: 0.8;
            font-size: 0.9em;
        }

        .subject-score {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 14px 20px;
            border-bottom: 1px solid var(--border);
            transition: background 0.3s;
        }

        .subject-score:hover {
            background: var(--bg);
        }

        .subject-score:last-child {
            border-bottom: none;
        }

        .subject-info {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .subject-icon {
            width: 40px;
            height: 40px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1em;
        }

        .subject-name {
            font-weight: 600;
        }

        .subject-exam {
            font-size: 0.8em;
            color: var(--text-light);
        }

        .score-value {
            font-size: 1.3em;
            font-weight: 700;
        }

        /* ===== SEARCH & FILTER ===== */
        .search-bar {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .search-bar input,
        .search-bar select {
            padding: 10px 16px;
            border: 2px solid var(--border);
            border-radius: 10px;
            font-size: 0.9em;
            transition: all 0.3s;
        }

        .search-bar input:focus,
        .search-bar select:focus {
            outline: none;
            border-color: var(--primary-light);
            box-shadow: 0 0 0 4px rgba(41,128,185,0.1);
        }

        .search-bar input {
            flex: 1;
            min-width: 200px;
        }

        /* ===== EMPTY STATE ===== */
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            color: var(--text-light);
        }

        .empty-state .empty-icon {
            font-size: 4em;
            margin-bottom: 15px;
            opacity: 0.5;
        }

        .empty-state h4 {
            font-size: 1.1em;
            margin-bottom: 8px;
            color: var(--text);
        }

        /* ===== TOAST ===== */
        .toast-container {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 2000;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .toast {
            padding: 14px 20px;
            border-radius: 10px;
            color: white;
            font-size: 0.9em;
            font-weight: 500;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            animation: toastIn 0.4s ease, toastOut 0.4s ease 2.6s forwards;
            display: flex;
            align-items: center;
            gap: 10px;
            max-width: 350px;
        }

        .toast.success { background: var(--success); }
        .toast.error { background: var(--danger); }
        .toast.info { background: var(--primary-light); }

        @keyframes toastIn {
            from { opacity: 0; transform: translateX(100px); }
            to { opacity: 1; transform: translateX(0); }
        }

        @keyframes toastOut {
            from { opacity: 1; transform: translateX(0); }
            to { opacity: 0; transform: translateX(100px); }
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            .login-container {
                flex-direction: column;
                max-width: 450px;
            }

            .login-left {
                padding: 30px 20px;
            }

            .login-left .big-logo {
                font-size: 50px;
            }

            .login-right {
                padding: 30px 20px;
            }

            .main-layout {
                flex-direction: column;
            }

            .sidebar {
                width: 100%;
                padding: 10px 0;
                overflow-x: auto;
            }

            .sidebar-menu {
                display: flex;
                flex-wrap: nowrap;
            }

            .sidebar-menu a {
                padding: 10px 16px;
                white-space: nowrap;
                border-left: none;
                border-bottom: 3px solid transparent;
                font-size: 0.8em;
            }

            .sidebar-menu a.active {
                border-left: none;
                border-bottom-color: var(--primary);
            }

            .sidebar-section {
                display: none;
            }

            .content {
                padding: 16px;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .stats-grid {
                grid-template-columns: 1fr 1fr;
            }

            .header-top {
                padding: 10px 16px;
            }

            .school-name h1 {
                font-size: 1em;
            }
        }

        @media (max-width: 480px) {
            .stats-grid {
                grid-template-columns: 1fr;
            }
        }

        /* ===== PRINT ===== */
        @media print {
            .header, .sidebar, .btn, .search-bar {
                display: none !important;
            }
            .content {
                padding: 0;
            }
            .card {
                box-shadow: none;
                border: 1px solid #ddd;
            }
        }

        /* ===== HIDDEN ===== */
        .hidden {
            display: none !important;
        }

        /* ===== PROGRESS BAR ===== */
        .progress-bar {
            width: 100%;
            height: 8px;
            background: var(--bg);
            border-radius: 4px;
            overflow: hidden;
            margin-top: 8px;
        }

        .progress-fill {
            height: 100%;
            border-radius: 4px;
            transition: width 0.5s ease;
        }

        .progress-fill.green { background: var(--success); }
        .progress-fill.blue { background: var(--primary-light); }
        .progress-fill.orange { background: var(--accent); }
        .progress-fill.red { background: var(--danger); }

        /* ===== CHIP ===== */
        .chip {
            display: inline-block;
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 0.75em;
            font-weight: 600;
            margin: 2px;
        }

        .chip-blue { background: #e3f2fd; color: #1565c0; }
        .chip-green { background: #e8f5e9; color: #2e7d32; }
    </style>
</head>
<body>

<!-- ==================== TOAST CONTAINER ==================== -->
<div class="toast-container" id="toastContainer"></div>

<!-- ==================== LOGIN PAGE ==================== -->
<div id="loginPage" class="login-page">
    <div class="login-container">
        <div class="login-left">
            <div class="big-logo">🏫</div>
            <h2>Мөст сумын ЕБС</h2>
            <p>Ховд аймаг, Мөст сум<br>Ерөнхий боловсролын сургууль</p>
            <br>
            <p style="font-size:0.85em; opacity:0.7;">Дүнгийн мэдээллийн систем<br>Багш, сурагчдад зориулсан</p>
        </div>
        <div class="login-right">
            <h3 id="authTitle">Нэвтрэх</h3>
            <p class="subtitle">Дүнгийн системд нэвтэрнэ үү</p>

            <div class="tab-switcher">
                <button class="active" onclick="switchAuthTab('login')">Нэвтрэх</button>
                <button onclick="switchAuthTab('register')">Бүртгүүлэх</button>
            </div>

            <div id="authError" class="error-msg">
                <span>⚠️</span>
                <span id="authErrorText"></span>
            </div>

            <div id="authSuccess" class="success-msg">
                <span>✅</span>
                <span id="authSuccessText"></span>
            </div>

            <!-- LOGIN FORM -->
            <form id="loginForm" onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label>📧 Имэйл хаяг</label>
                    <input type="email" id="loginEmail" placeholder="таны@gmail.com" required>
                </div>
                <div class="form-group">
                    <label>🔒 Нууц үг</label>
                    <input type="password" id="loginPassword" placeholder="Нууц үгээ оруулна уу" required>
                </div>
                <button type="submit" class="login-btn">🔓 Нэвтрэх</button>
            </form>

            <!-- REGISTER FORM -->
            <form id="registerForm" class="hidden" onsubmit="handleRegister(event)">
                <div class="form-group">
                    <label>👤 Бүтэн нэр</label>
                    <input type="text" id="regName" placeholder="Овог Нэр" required>
                </div>
                <div class="form-group">
                    <label>📧 Gmail хаяг</label>
                    <div class="gmail-input-group">
                        <input type="email" id="regEmail" placeholder="таны@gmail.com" required>
                    </div>
                    <small style="color:var(--text-light); font-size:0.75em; margin-top:4px; display:block;">Gmail хаягаар бүртгүүлнэ үү</small>
                </div>
                <div class="form-group">
                    <label>🔑 Нууц үг</label>
                    <input type="password" id="regPassword" placeholder="Дор хаяж 6 тэмдэгт" minlength="6" required>
                </div>
                <div class="form-group">
                    <label>🎭 Хэрэглэгчийн төрөл</label>
                    <select id="regRole" required>
                        <option value="">-- Сонгоно уу --</option>
                        <option value="teacher">👨‍🏫 Багш</option>
                        <option value="student">👨‍🎓 Сурагч</option>
                    </select>
                </div>
                <div class="form-group hidden" id="regStudentIdGroup">
                    <label>🆔 Сурагчийн ID код</label>
                    <input type="text" id="regStudentId" placeholder="Жишээ: MST-2024-001">
                    <small style="color:var(--text-light); font-size:0.75em; margin-top:4px; display:block;">Багшаас авсан ID кодоо оруулна уу</small>
                </div>
                <div class="form-group hidden" id="regSubjectGroup">
                    <label>📚 Хичээл</label>
                    <select id="regSubject">
                        <option value="">-- Сонгоно уу --</option>
                        <option value="Математик">Математик</option>
                        <option value="Монгол хэл">Монгол хэл</option>
                        <option value="Англи хэл">Англи хэл</option>
                        <option value="Физик">Физик</option>
                        <option value="Хими">Хими</option>
                        <option value="Биологи">Биологи</option>
                        <option value="Түүх">Түүх</option>
                        <option value="Газарзүй">Газарзүй</option>
                        <option value="Нийгэм судлал">Нийгэм судлал</option>
                        <option value="Зураг зүй">Зураг зүй</option>
                        <option value="Хөгжим">Хөгжим</option>
                        <option value="Биеийн тамир">Биеийн тамир</option>
                        <option value="Технологи">Технологи</option>
                        <option value="Мэдээлэл зүй">Мэдээлэл зүй</option>
                    </select>
                </div>
                <button type="submit" class="login-btn">✅ Бүртгүүлэх</button>
            </form>
        </div>
    </div>
</div>

<!-- ==================== MAIN APP ==================== -->
<div id="mainApp" class="hidden">
    <!-- HEADER -->
    <div class="header">
        <div class="header-top">
            <div class="school-info">
                <div class="school-logo">🏫</div>
                <div class="school-name">
                    <h1>Мөст сумын Ерөнхий боловсролын сургууль</h1>
                    <p>📍 Ховд аймаг, Мөст сум | Дүнгийн мэдээллийн систем</p>
                </div>
            </div>
            <div class="header-actions">
                <div class="user-badge">
                    <span class="role-icon" id="userRoleIcon">👨‍🏫</span>
                    <span id="userDisplayName"></span>
                </div>
                <button class="btn btn-outline btn-sm" onclick="handleLogout()">🚪 Гарах</button>
            </div>
        </div>
    </div>

    <!-- MAIN LAYOUT -->
    <div class="main-layout">
        <!-- SIDEBAR -->
        <nav class="sidebar">
            <!-- Teacher Menu -->
            <div id="teacherMenu">
                <div class="sidebar-section">Үндсэн цэс</div>
                <ul class="sidebar-menu">
                    <li><a href="#" class="active" onclick="showPage('dashboard', this)"><span class="menu-icon">📊</span> Ерөнхий харагдац</a></li>
                    <li><a href="#" onclick="showPage('students', this)"><span class="menu-icon">👨‍🎓</span> Сурагчид</a></li>
                    <li><a href="#" onclick="showPage('scores', this)"><span class="menu-icon">📝</span> Дүн оруулах</a></li>
                    <li><a href="#" onclick="showPage('scoreTable', this)"><span class="menu-icon">📋</span> Дүнгийн хүснэгт</a></li>
                    <li><a href="#" onclick="showPage('reports', this)"><span class="menu-icon">📈</span> Тайлан</a></li>
                </ul>
                <div class="sidebar-section">Тохиргоо</div>
                <ul class="sidebar-menu">
                    <li><a href="#" onclick="showPage('settings', this)"><span class="menu-icon">⚙️</span> Тохиргоо</a></li>
                </ul>
            </div>

            <!-- Student Menu -->
            <div id="studentMenu" class="hidden">
                <div class="sidebar-section">Үндсэн цэс</div>
                <ul class="sidebar-menu">
                    <li><a href="#" class="active" onclick="showPage('myScores', this)"><span class="menu-icon">📊</span> Миний дүн</a></li>
                    <li><a href="#" onclick="showPage('mySubjects', this)"><span class="menu-icon">📚</span> Хичээлүүд</a></li>
                    <li><a href="#" onclick="showPage('myProfile', this)"><span class="menu-icon">👤</span> Миний профиль</a></li>
                </ul>
            </div>
        </nav>

        <!-- CONTENT AREA -->
        <div class="content">

            <!-- ===== TEACHER: DASHBOARD ===== -->
            <div id="page-dashboard" class="page">
                <div class="page-header">
                    <h2>📊 Ерөнхий харагдац</h2>
                    <p>Сургуулийн нийт мэдээллийг эндээс харна уу</p>
                </div>
                <div class="stats-grid" id="teacherStats"></div>
                <div class="card">
                    <div class="card-header">
                        <h3>📋 Сүүлд оруулсан дүнгүүд</h3>
                    </div>
                    <div class="card-body">
                        <div class="table-container">
                            <table id="recentScoresTable">
                                <thead>
                                    <tr>
                                        <th>Сурагч</th>
                                        <th>ID</th>
                                        <th>Хичээл</th>
                                        <th>Шалгалт</th>
                                        <th>Оноо</th>
                                        <th>Огноо</th>
                                    </tr>
                                </thead>
                                <tbody></tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- ===== TEACHER: STUDENTS ===== -->
            <div id="page-students" class="page hidden">
                <div class="page-header">
                    <h2>👨‍🎓 Сурагчдын жагсаалт</h2>
                    <p>Сурагчдыг нэмж, удирдана уу</p>
                </div>
                <div class="search-bar">
                    <input type="text" id="studentSearch" placeholder="🔍 Сурагч хайх..." oninput="filterStudents()">
                    <button class="btn btn-primary" onclick="openModal('addStudentModal')">➕ Сурагч нэмэх</button>
                    <button class="btn btn-accent" onclick="openModal('bulkAddModal')">📥 Олноор нэмэх</button>
                </div>
                <div class="card">
                    <div class="card-body">
                        <div class="table-container">
                            <table id="studentsTable">
                                <thead>
                                    <tr>
                                        <th>ID код</th>
                                        <th>Нэр</th>
                                        <th>Анги</th>
                                        <th>Gmail</th>
                                        <th>Хичээлийн тоо</th>
                                        <th>Дундаж</th>
                                        <th>Үйлдэл</th>
                                    </tr>
                                </thead>
                                <tbody></tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- ===== TEACHER: ADD SCORE ===== -->
            <div id="page-scores" class="page hidden">
                <div class="page-header">
                    <h2>📝 Дүн оруулах</h2>
                    <p>Сурагчийн шалгалтын дүнг оруулна уу</p>
                </div>
                <div class="card">
                    <div class="card-header">
                        <h3>📝 Шинэ дүн нэмэх</h3>
                    </div>
                    <div class="card-body">
                        <form onsubmit="handleAddScore(event)">
                            <div class="form-row">
                                <div class="form-group">
                                    <label>👨‍🎓 Сурагч</label>
                                    <select id="scoreStudent" required>
                                        <option value="">-- Сурагч сонгоно уу --</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <label>📚 Хичээл</label>
                                    <select id="scoreSubject" required>
                                        <option value="">-- Хичээл сонгоно уу --</option>
                                        <option>Математик</option>
                                        <option>Монгол хэл</option>
                                        <option>Англи хэл</option>
                                        <option>Физик</option>
                                        <option>Хими</option>
                                        <option>Биологи</option>
                                        <option>Түүх</option>
                                        <option>Газарзүй</option>
                                        <option>Нийгэм судлал</option>
                                        <option>Зураг зүй</option>
                                        <option>Хөгжим</option>
                                        <option>Биеийн тамир</option>
                                        <option>Технологи</option>
                                        <option>Мэдээлэл зүй</option>
                                    </select>
                                </div>
                            </div>
                            <div class="form-row">
                                <div class="form-group">
                                    <label>📋 Шалгалтын төрөл</label>
                                    <select id="scoreExamType" required>
                                        <option value="">-- Сонгоно уу --</option>
                                        <option>Улирлын шалгалт</option>
                                        <option>Хагас жилийн шалгалт</option>
                                        <option>Жилийн эцсийн шалгалт</option>
                                        <option>Ангийн ажлын дүн</option>
                                        <option>Гэрийн даалгавар</option>
                                        <option>Туршилт</option>
                                    </select>
                                </div>
                                <div class="form-group">
                                    <label>📅 Огноо</label>
                                    <input type="date" id="scoreDate" required>
                                </div>
                            </div>
                            <div class="form-row">
                                <div class="form-group">
                                    <label>💯 Оноо (0-100)</label>
                                    <input type="number" id="scoreValue" min="0" max="100" placeholder="0-100" required>
                                </div>
                                <div class="form-group">
                                    <label>💬 Тайлбар (заавал биш)</label>
                                    <input type="text" id="scoreNote" placeholder="Тайлбар бичих...">
                                </div>
                            </div>
                            <button type="submit" class="btn btn-success btn-lg">💾 Дүн хадгалах</button>
                        </form>
                    </div>
                </div>
            </div>

            <!-- ===== TEACHER: SCORE TABLE ===== -->
            <div id="page-scoreTable" class="page hidden">
                <div class="page-header">
                    <h2>📋 Дүнгийн хүснэгт</h2>
                    <p>Бүх сурагчдын дүнг эндээс харна уу</p>
                </div>
                <div class="search-bar">
                    <input type="text" id="scoreTableSearch" placeholder="🔍 Сурагч эсвэл хичээл хайх..." oninput="filterScoreTable()">
                    <select id="scoreTableSubject" onchange="filterScoreTable()">
                        <option value="">Бүх хичээл</option>
                        <option>Математик</option>
                        <option>Монгол хэл</option>
                        <option>Англи хэл</option>
                        <option>Физик</option>
                        <option>Хими</option>
                        <option>Биологи</option>
                        <option>Түүх</option>
                        <option>Газарзүй</option>
                        <option>Нийгэм судлал</option>
                        <option>Зураг зүй</option>
                        <option>Хөгжим</option>
                        <option>Биеийн тамир</option>
                        <option>Технологи</option>
                        <option>Мэдээлэл зүй</option>
                    </select>
                    <select id="scoreTableExam" onchange="filterScoreTable()">
                        <option value="">Бүх шалгалт</option>
                        <option>Улирлын шалгалт</option>
                        <option>Хагас жилийн шалгалт</option>
                        <option>Жилийн эцсийн шалгалт</option>
                        <option>Ангийн ажлын дүн</option>
                        <option>Гэрийн даалгавар</option>
                        <option>Туршилт</option>
                    </select>
                </div>
                <div class="card">
                    <div class="card-body">
                        <div class="table-container">
                            <table id="allScoresTable">
                                <thead>
                                    <tr>
                                        <th>Сурагч</th>
                                        <th>ID</th>
                                        <th>Хичээл</th>
                                        <th>Шалгалт</th>
                                        <th>Оноо</th>
                                        <th>Үнэлгээ</th>
                                        <th>Огноо</th>
                                        <th>Тайлбар</th>
                                        <th>Үйлдэл</th>
                                    </tr>
                                </thead>
                                <tbody></tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- ===== TEACHER: REPORTS ===== -->
            <div id="page-reports" class="page hidden">
                <div class="page-header">
                    <h2>📈 Тайлан</h2>
                    <p>Сурагчдын дүнгийн дүн шинжилгээ</p>
                </div>
                <div class="card">
                    <div class="card-header">
                        <h3>📊 Хичээлийн дундаж дүн</h3>
                    </div>
                    <div class="card-body" id="subjectReport"></div>
                </div>
                <div class="card">
                    <div class="card-header">
                        <h3>🏆 Амжилттай сурагчид</h3>
                    </div>
                    <div class="card-body" id="topStudents"></div>
                </div>
            </div>

            <!-- ===== TEACHER: SETTINGS ===== -->
            <div id="page-settings" class="page hidden">
                <div class="page-header">
                    <h2>⚙️ Тохиргоо</h2>
                    <p>Системийн тохиргоог эндээс удирдана уу</p>
                </div>
                <div class="card">
                    <div class="card-header">
                        <h3>🗄️ Өгөгдлийн удирдлага</h3>
                    </div>
                    <div class="card-body">
                        <p style="margin-bottom:15px; color:var(--text-light);">Өгөгдлөө нөөцлөх, сэргээх, эсвэл бүх өгөгдлийг устгах боломжтой.</p>
                        <div style="display:flex; gap:10px; flex-wrap:wrap;">
                            <button class="btn btn-primary" onclick="exportData()">📤 Өгөгдөл экспортлох</button>
                            <button class="btn btn-accent" onclick="document.getElementById('importFile').click()">📥 Өгөгдөл импортлох</button>
                            <input type="file" id="importFile" accept=".json" style="display:none" onchange="importData(event)">
                            <button class="btn btn-danger" onclick="clearAllData()">🗑️ Бүх өгөгдлийг устгах</button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- ===== STUDENT: MY SCORES ===== -->
            <div id="page-myScores" class="page">
                <div class="page-header">
                    <h2>📊 Миний дүн</h2>
                    <p>Өөрийн шалгалтын дүнг хянах</p>
                </div>
                <div id="studentScoreOverview"></div>
                <div class="card">
                    <div class="card-header">
                        <h3>📝 Бүх дүнгийн жагсаалт</h3>
                    </div>
                    <div class="card-body" id="studentAllScores"></div>
                </div>
            </div>

            <!-- ===== STUDENT: MY SUBJECTS ===== -->
            <div id="page-mySubjects" class="page hidden">
                <div class="page-header">
                    <h2>📚 Хичээлүүд</h2>
                    <p>Хичээл бүрийн дүнгийн дэлгэрэнгүй</p>
                </div>
                <div id="studentSubjects"></div>
            </div>

            <!-- ===== STUDENT: MY PROFILE ===== -->
            <div id="page-myProfile" class="page hidden">
                <div class="page-header">
                    <h2>👤 Миний профиль</h2>
                    <p>Хэрэглэгчийн мэдээлэл</p>
                </div>
                <div class="card">
                    <div class="card-body" id="studentProfile"></div>
                </div>
            </div>

        </div>
    </div>
</div>

<!-- ==================== MODALS ==================== -->

<!-- ADD STUDENT MODAL -->
<div class="modal-overlay" id="addStudentModal">
    <div class="modal">
        <div class="modal-header">
            <h3>➕ Сурагч нэмэх</h3>
            <button class="modal-close" onclick="closeModal('addStudentModal')">✕</button>
        </div>
        <div class="modal-body">
            <form onsubmit="handleAddStudent(event)">
                <div class="form-group">
                    <label>🆔 Сурагчийн ID код</label>
                    <input type="text" id="newStudentId" placeholder="Жишээ: MST-2024-001" required>
                    <small style="color:var(--text-light); font-size:0.75em; margin-top:4px; display:block;">Энэ ID-ээр сурагч нэвтэрнэ</small>
                </div>
                <div class="form-group">
                    <label>👤 Бүтэн нэр</label>
                    <input type="text" id="newStudentName" placeholder="Овог Нэр" required>
                </div>
                <div class="form-group">
                    <label>🏫 Анги</label>
                    <select id="newStudentGrade" required>
                        <option value="">-- Сонгоно уу --</option>
                        <option>1-р анги</option>
                        <option>2-р анги</option>
                        <option>3-р анги</option>
                        <option>4-р анги</option>
                        <option>5-р анги</option>
                        <option>6-р анги</option>
                        <option>7-р анги</option>
                        <option>8-р анги</option>
                        <option>9-р анги</option>
                        <option>10-р анги</option>
                        <option>11-р анги</option>
                        <option>12-р анги</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>📧 Gmail (заавал биш)</label>
                    <input type="email" id="newStudentEmail" placeholder="сурагч@gmail.com">
                </div>
                <div class="form-group">
                    <label>🔒 Сурагчийн нууц үг</label>
                    <input type="password" id="newStudentPassword" placeholder="Сурагчийн нэвтрэх нууц үг" minlength="4" required>
                </div>
                <button type="submit" class="btn btn-success btn-lg" style="width:100%;">💾 Хадгалах</button>
            </form>
        </div>
    </div>
</div>

<!-- BULK ADD STUDENT MODAL -->
<div class="modal-overlay" id="bulkAddModal">
    <div class="modal">
        <div class="modal-header">
            <h3>📥 Олноор сурагч нэмэх</h3>
            <button class="modal-close" onclick="closeModal('bulkAddModal')">✕</button>
        </div>
        <div class="modal-body">
            <p style="margin-bottom:15px; color:var(--text-light); font-size:0.9em;">Мөр бүрд нэг сурагч. Хэлбэр: <strong>ID, Нэр, Анги</strong></p>
            <div class="form-group">
                <label>📋 Сурагчдын жагсаалт</label>
                <textarea id="bulkStudents" rows="10" style="width:100%; padding:12px; border:2px solid var(--border); border-radius:10px; font-family:monospace; font-size:0.9em; resize:vertical;" placeholder="MST-001, Бат-Эрдэнэ, 5-р анги&#10;MST-002, Сарнай, 5-р анги&#10;MST-003, Тэмүүлэн, 6-р анги"></textarea>
            </div>
            <div class="form-group">
                <label>🔒 Нууц үг (бүгдэд ижил)</label>
                <input type="text" id="bulkPassword" value="student123" placeholder="Анхны нууц үг">
            </div>
            <button class="btn btn-success btn-lg" style="width:100%;" onclick="handleBulkAdd()">📥 Бүгдийг нэмэх</button>
        </div>
    </div>
</div>

<!-- EDIT SCORE MODAL -->
<div class="modal-overlay" id="editScoreModal">
    <div class="modal">
        <div class="modal-header">
            <h3>✏️ Дүн засварлах</h3>
            <button class="modal-close" onclick="closeModal('editScoreModal')">✕</button>
        </div>
        <div class="modal-body">
            <form onsubmit="handleEditScore(event)">
                <input type="hidden" id="editScoreId">
                <div class="form-group">
                    <label>💯 Оноо (0-100)</label>
                    <input type="number" id="editScoreValue" min="0" max="100" required>
                </div>
                <div class="form-group">
                    <label>💬 Тайлбар</label>
                    <input type="text" id="editScoreNote">
                </div>
                <button type="submit" class="btn btn-success btn-lg" style="width:100%;">💾 Засварлах</button>
            </form>
        </div>
    </div>
</div>

<!-- STUDENT ID LOGIN MODAL -->
<div class="modal-overlay" id="studentIdModal">
    <div class="modal" style="max-width:400px;">
        <div class="modal-header">
            <h3>🆔 Сурагчийн ID-ээр нэвтрэх</h3>
            <button class="modal-close" onclick="closeModal('studentIdModal')">✕</button>
        </div>
        <div class="modal-body">
            <form onsubmit="handleStudentIdLogin(event)">
                <div class="form-group">
                    <label>🆔 Сурагчийн ID код</label>
                    <input type="text" id="studentIdInput" placeholder="Жишээ: MST-2024-001" required>
                </div>
                <div class="form-group">
                    <label>🔒 Нууц үг</label>
                    <input type="password" id="studentIdPassword" placeholder="Нууц үг" required>
                </div>
                <button type="submit" class="btn btn-primary btn-lg" style="width:100%;">🔓 Нэвтрэх</button>
            </form>
        </div>
    </div>
</div>


<script>
// ==================== DATABASE (LocalStorage) ====================
const DB = {
    get(key) {
        try {
            return JSON.parse(localStorage.getItem('most_school_' + key)) || [];
        } catch { return []; }
    },
    set(key, data) {
        localStorage.setItem('most_school_' + key, JSON.stringify(data));
    },
    getConfig(key) {
        return localStorage.getItem('most_school_config_' + key);
    },
    setConfig(key, val) {
        localStorage.setItem('most_school_config_' + key, val);
    }
};

// ==================== GLOBALS ====================
let currentUser = null;

// ==================== INIT ====================
function init() {
    const savedSession = DB.getConfig('currentSession');
    if (savedSession) {
        try {
            currentUser = JSON.parse(savedSession);
            showMainApp();
        } catch {
            showLoginPage();
        }
    } else {
        showLoginPage();
    }
}

// ==================== AUTH ====================
function switchAuthTab(tab) {
    document.querySelectorAll('.tab-switcher button').forEach((b, i) => {
        b.classList.toggle('active', (tab === 'login' && i === 0) || (tab === 'register' && i === 1));
    });
    document.getElementById('loginForm').classList.toggle('hidden', tab !== 'login');
    document.getElementById('registerForm').classList.toggle('hidden', tab !== 'register');
    document.getElementById('authTitle').textContent = tab === 'login' ? 'Нэвтрэх' : 'Бүртгүүлэх';
    hideMessages();
}

function hideMessages() {
    document.getElementById('authError').style.display = 'none';
    document.getElementById('authSuccess').style.display = 'none';
}

function showError(msg) {
    const el = document.getElementById('authError');
    document.getElementById('authErrorText').textContent = msg;
    el.style.display = 'flex';
    document.getElementById('authSuccess').style.display = 'none';
}

function showSuccess(msg) {
    const el = document.getElementById('authSuccess');
    document.getElementById('authSuccessText').textContent = msg;
    el.style.display = 'flex';
    document.getElementById('authError').style.display = 'none';
}

function handleRegister(e) {
    e.preventDefault();
    const name = document.getElementById('regName').value.trim();
    const email = document.getElementById('regEmail').value.trim().toLowerCase();
    const password = document.getElementById('regPassword').value;
    const role = document.getElementById('regRole').value;

    if (!email.endsWith('@gmail.com') && !email.endsWith('@googlemail.com')) {
        showError('Gmail хаяг ашиглана уу (@gmail.com)');
        return;
    }

    const users = DB.get('users');
    if (users.find(u => u.email === email)) {
        showError('Энэ имэйл хаяг аль хэдийн бүртгэгдсэн байна');
        return;
    }

    const user = {
        id: Date.now().toString(),
        name,
        email,
        password,
        role,
        createdAt: new Date().toISOString()
    };

    if (role === 'student') {
        const studentId = document.getElementById('regStudentId').value.trim();
        if (!studentId) {
            showError('Сурагчийн ID кодыг оруулна уу');
            return;
        }
        // Check if this student ID was pre-created by teacher
        const students = DB.get('students');
        const existingStudent = students.find(s => s.id === studentId);
        if (existingStudent) {
            if (existingStudent.email && existingStudent.email !== email) {
                showError('Энэ ID код өөр имэйлээр бүртгэгдсэн байна');
                return;
            }
            existingStudent.email = email;
            existingStudent.userId = user.id;
            DB.set('students', students);
        } else {
            // Create student record
            students.push({
                id: studentId,
                name,
                grade: '',
                email,
                userId: user.id,
                createdAt: new Date().toISOString()
            });
            DB.set('students', students);
        }
        user.studentId = studentId;
    }

    if (role === 'teacher') {
        user.subject = document.getElementById('regSubject').value;
    }

    users.push(user);
    DB.set('users', users);

    showSuccess('Амжилттай бүртгэгдлээ! Одоо нэвтэрнэ үү.');
    setTimeout(() => {
        switchAuthTab('login');
        document.getElementById('loginEmail').value = email;
    }, 1500);
}

// Handle role change visibility
document.getElementById('regRole').addEventListener('change', function() {
    document.getElementById('regStudentIdGroup').classList.toggle('hidden', this.value !== 'student');
    document.getElementById('regSubjectGroup').classList.toggle('hidden', this.value !== 'teacher');
});

function handleLogin(e) {
    e.preventDefault();
    const email = document.getElementById('loginEmail').value.trim().toLowerCase();
    const password = document.getElementById('loginPassword').value;

    const users = DB.get('users');
    const user = users.find(u => u.email === email && u.password === password);

    if (!user) {
        showError('Имэйл эсвэл нууц үг буруу байна');
        return;
    }

    currentUser = user;
    DB.setConfig('currentSession', JSON.stringify(user));
    showMainApp();
    showToast('success', `${user.name} сайн байна уу!`);
}

function handleStudentIdLogin(e) {
    e.preventDefault();
    const studentId = document.getElementById('studentIdInput').value.trim();
    const password = document.getElementById('studentIdPassword').value;

    const students = DB.get('students');
    const student = students.find(s => s.id === studentId);

    if (!student) {
        showToast('error', 'Олдсонгүй: ' + studentId);
        return;
    }

    // Check if student has a user account with password
    if (student.userId) {
        const users = DB.get('users');
        const user = users.find(u => u.id === student.userId && u.password === password);
        if (!user) {
            showToast('error', 'Нууц үг буруу байна');
            return;
        }
        currentUser = user;
    } else {
        // Create a temporary user for direct student ID access
        const user = {
            id: student.userId || 'student_' + Date.now(),
            name: student.name,
            email: student.email || student.id + '@most.school',
            password: password,
            role: 'student',
            studentId: student.id,
            createdAt: new Date().toISOString()
        };

        // Save or update
        const users = DB.get('users');
        const existing = users.find(u => u.studentId === student.id);
        if (existing) {
            existing.password = password;
            currentUser = existing;
        } else {
            user.id = 'student_' + Date.now();
            student.userId = user.id;
            DB.set('students', students);
            users.push(user);
            currentUser = user;
        }
        DB.set('users', users);
    }

    DB.setConfig('currentSession', JSON.stringify(currentUser));
    closeModal('studentIdModal');
    showMainApp();
    showToast('success', `${student.name} сайн байна уу!`);
}

function handleLogout() {
    currentUser = null;
    DB.setConfig('currentSession', '');
    showLoginPage();
    showToast('info', 'Амжилттай гарлаа');
}

// ==================== NAVIGATION ====================
function showLoginPage() {
    document.getElementById('loginPage').classList.remove('hidden');
    document.getElementById('mainApp').classList.add('hidden');
}

function showMainApp() {
    document.getElementById('loginPage').classList.add('hidden');
    document.getElementById('mainApp').classList.remove('hidden');

    document.getElementById('userDisplayName').textContent = currentUser.name;
    document.getElementById('userRoleIcon').textContent = currentUser.role === 'teacher' ? '👨‍🏫' : '👨‍🎓';

    if (currentUser.role === 'teacher') {
        document.getElementById('teacherMenu').classList.remove('hidden');
        document.getElementById('studentMenu').classList.add('hidden');
        showPage('dashboard', document.querySelector('#teacherMenu .sidebar-menu a.active'));
    } else {
        document.getElementById('teacherMenu').classList.add('hidden');
        document.getElementById('studentMenu').classList.remove('hidden');
        showPage('myScores', document.querySelector('#studentMenu .sidebar-menu a.active'));
    }
}

function showPage(pageId, clickedLink) {
    // Hide all pages
    document.querySelectorAll('.page').forEach(p => p.classList.add('hidden'));

    // Show target page
    const target = document.getElementById('page-' + pageId);
    if (target) target.classList.remove('hidden');

    // Update sidebar active
    const menu = currentUser.role === 'teacher' ? 'teacherMenu' : 'studentMenu';
    document.querySelectorAll(`#${menu} .sidebar-menu a`).forEach(a => a.classList.remove('active'));
    if (clickedLink) clickedLink.classList.add('active');

    // Load page data
    switch(pageId) {
        case 'dashboard': loadTeacherDashboard(); break;
        case 'students': loadStudents(); break;
        case 'scores': loadScoreForm(); break;
        case 'scoreTable': loadScoreTable(); break;
        case 'reports': loadReports(); break;
        case 'myScores': loadMyScores(); break;
        case 'mySubjects': loadMySubjects(); break;
        case 'myProfile': loadMyProfile(); break;
    }
}

// ==================== TOAST ====================
function showToast(type, message) {
    const container = document.getElementById('toastContainer');
    const toast = document.createElement('div');
    toast.className = `toast ${type}`;
    const icons = { success: '✅', error: '❌', info: 'ℹ️' };
    toast.innerHTML = `<span>${icons[type] || 'ℹ️'}</span><span>${message}</span>`;
    container.appendChild(toast);
    setTimeout(() => toast.remove(), 3000);
}

// ==================== MODAL ====================
function openModal(id) {
    document.getElementById(id).classList.add('active');
}

function closeModal(id) {
    document.getElementById(id).classList.remove('active');
}

// Close modal on overlay click
document.querySelectorAll('.modal-overlay').forEach(overlay => {
    overlay.addEventListener('click', function(e) {
        if (e.target === this) {
            this.classList.remove('active');
        }
    });
});

// ==================== TEACHER: DASHBOARD ====================
function loadTeacherDashboard() {
    const students = DB.get('students');
    const scores = DB.get('scores');
    const users = DB.get('users');

    const avgScore = scores.length > 0
        ? (scores.reduce((sum, s) => sum + parseInt(s.score), 0) / scores.length).toFixed(1)
        : '—';

    const excellent = scores.filter(s => s.score >= 90).length;
    const good = scores.filter(s => s.score >= 75 && s.score < 90).length;
    const average = scores.filter(s => s.score >= 50 && s.score < 75).length;
    const poor = scores.filter(s => s.score < 50).length;

    document.getElementById('teacherStats').innerHTML = `
        <div class="stat-card">
            <div class="stat-icon blue">👨‍🎓</div>
            <div class="stat-info">
                <h4>${students.length}</h4>
                <p>Нийт сурагч</p>
            </div>
        </div>
        <div class="stat-card">
            <div class="stat-icon green">📝</div>
            <div class="stat-info">
                <h4>${scores.length}</h4>
                <p>Нийт дүн</p>
            </div>
        </div>
        <div class="stat-card">
            <div class="stat-icon orange">📊</div>
            <div class="stat-info">
                <h4>${avgScore}</h4>
                <p>Дундаж оноо</p>
            </div>
        </div>
        <div class="stat-card">
            <div class="stat-icon red">🏆</div>
            <div class="stat-info">
                <h4>${excellent}</h4>
                <p>Онц (90+) дүн</p>
            </div>
        </div>
    `;

    // Recent scores
    const recent = scores.slice(-10).reverse();
    const tbody = document.querySelector('#recentScoresTable tbody');
    if (recent.length === 0) {
        tbody.innerHTML = `<tr><td colspan="6"><div class="empty-state"><div class="empty-icon">📝</div><h4>Одоогоор дүн оруулаагүй байна</h4></div></td></tr>`;
    } else {
        tbody.innerHTML = recent.map(s => {
            const student = students.find(st => st.id === s.studentId);
            return `<tr>
                <td><strong>${student ? student.name : 'Тодорхойгүй'}</strong></td>
                <td><span class="chip chip-blue">${s.studentId}</span></td>
                <td>${s.subject}</td>
                <td>${s.examType}</td>
                <td><strong>${getGradeBadge(s.score)}</strong></td>
                <td>${formatDate(s.date)}</td>
            </tr>`;
        }).join('');
    }
}

// ==================== TEACHER: STUDENTS ====================
function loadStudents() {
    const students = DB.get('students');
    const scores = DB.get('scores');
    const tbody = document.querySelector('#studentsTable tbody');

    if (students.length === 0) {
        tbody.innerHTML = `<tr><td colspan="7"><div class="empty-state"><div class="empty-icon">👨‍🎓</div><h4>Сурагч бүртгэгдээгүй байна</h4><p>Дээрх "Сурагч нэмэх" товчийг дарна уу</p></div></td></tr>`;
        return;
    }

    tbody.innerHTML = students.map(s => {
        const studentScores = scores.filter(sc => sc.studentId === s.id);
        const avg = studentScores.length > 0
            ? (studentScores.reduce((sum, sc) => sum + parseInt(sc.score), 0) / studentScores.length).toFixed(1)
            : '—';
        return `<tr>
            <td><span class="chip chip-blue">${s.id}</span></td>
            <td><strong>${s.name}</strong></td>
            <td>${s.grade || '—'}</td>
            <td>${s.email || '—'}</td>
            <td>${studentScores.length}</td>
            <td>${avg !== '—' ? getGradeBadge(avg) : '—'}</td>
            <td>
                <button class="btn btn-danger btn-sm" onclick="deleteStudent('${s.id}')">🗑️</button>
            </td>
        </tr>`;
    }).join('');
}

function filterStudents() {
    const query = document.getElementById('studentSearch').value.toLowerCase();
    const rows = document.querySelectorAll('#studentsTable tbody tr');
    rows.forEach(row => {
        const text = row.textContent.toLowerCase();
        row.style.display = text.includes(query) ? '' : 'none';
    });
}

function handleAddStudent(e) {
    e.preventDefault();
    const id = document.getElementById('newStudentId').value.trim();
    const name = document.getElementById('newStudentName').value.trim();
    const grade = document.getElementById('newStudentGrade').value;
    const email = document.getElementById('newStudentEmail').value.trim();
    const password = document.getElementById('newStudentPassword').value;

    const students = DB.get('students');
    if (students.find(s => s.id === id)) {
        showToast('error', 'Энэ ID код аль хэдийн бүртгэгдсэн байна');
        return;
    }

    students.push({
        id,
        name,
        grade,
        email,
        userId: null,
        createdAt: new Date().toISOString()
    });
    DB.set('students', students);

    // Also create a user account for direct login
    const users = DB.get('users');
    const user = {
        id: 'student_' + Date.now(),
        name,
        email: email || id + '@most.school',
        password,
        role: 'student',
        studentId: id,
        createdAt: new Date().toISOString()
    };
    users.push(user);
    DB.set('users', users);

    // Link
    const studentRecord = students.find(s => s.id === id);
    if (studentRecord) {
        studentRecord.userId = user.id;
        DB.set('students', students);
    }

    closeModal('addStudentModal');
    loadStudents();
    showToast('success', `${name} (${id}) амжилттай нэмэгдлээ`);

    // Reset form
    e.target.reset();
}

function handleBulkAdd() {
    const text = document.getElementById('bulkStudents').value.trim();
    const password = document.getElementById('bulkPassword').value || 'student123';

    if (!text) {
        showToast('error', 'Сурагчдын жагсаалтыг оруулна уу');
        return;
    }

    const lines = text.split('\n').filter(l => l.trim());
    const students = DB.get('students');
    const users = DB.get('users');
    let added = 0;

    lines.forEach(line => {
        const parts = line.split(',').map(p => p.trim());
        if (parts.length >= 2) {
            const id = parts[0];
            const name = parts[1];
            const grade = parts[2] || '';

            if (!students.find(s => s.id === id)) {
                students.push({
                    id,
                    name,
                    grade,
                    email: '',
                    userId: null,
                    createdAt: new Date().toISOString()
                });

                const user = {
                    id: 'student_' + Date.now() + '_' + added,
                    name,
                    email: id + '@most.school',
                    password,
                    role: 'student',
                    studentId: id,
                    createdAt: new Date().toISOString()
                };
                users.push(user);

                const s = students.find(st => st.id === id);
                if (s) s.userId = user.id;

                added++;
            }
        }
    });

    DB.set('students', students);
    DB.set('users', users);

    closeModal('bulkAddModal');
    loadStudents();
    showToast('success', `${added} сурагч амжилттай нэмэгдлээ`);
    document.getElementById('bulkStudents').value = '';
}

function deleteStudent(id) {
    if (!confirm('Энэ сурагчийг устгах уу? Бүх дүн хамт устах болно.')) return;

    let students = DB.get('students');
    let scores = DB.get('scores');
    let users = DB.get('users');

    const student = students.find(s => s.id === id);
    students = students.filter(s => s.id !== id);
    scores = scores.filter(s => s.studentId !== id);

    if (student && student.userId) {
        users = users.filter(u => u.id !== student.userId);
    }

    DB.set('students', students);
    DB.set('scores', scores);
    DB.set('users', users);

    loadStudents();
    showToast('success', 'Сурагч амжилттай устгагдлаа');
}

// ==================== TEACHER: ADD SCORE ====================
function loadScoreForm() {
    const students = DB.get('students');
    const select = document.getElementById('scoreStudent');
    select.innerHTML = '<option value="">-- Сурагч сонгоно уу --</option>';
    students.sort((a, b) => a.name.localeCompare(b.name)).forEach(s => {
        select.innerHTML += `<option value="${s.id}">${s.name} (${s.id})${s.grade ? ' - ' + s.grade : ''}</option>`;
    });

    // Set today's date
    document.getElementById('scoreDate').value = new Date().toISOString().split('T')[0];
}

function handleAddScore(e) {
    e.preventDefault();
    const studentId = document.getElementById('scoreStudent').value;
    const subject = document.getElementById('scoreSubject').value;
    const examType = document.getElementById('scoreExamType').value;
    const date = document.getElementById('scoreDate').value;
    const score = parseInt(document.getElementById('scoreValue').value);
    const note = document.getElementById('scoreNote').value.trim();

    const scores = DB.get('scores');
    scores.push({
        id: 'score_' + Date.now(),
        studentId,
        subject,
        examType,
        date,
        score,
        note,
        teacherId: currentUser.id,
        createdAt: new Date().toISOString()
    });
    DB.set('scores', scores);

    showToast('success', 'Дүн амжилттай хадгалагдлаа');
    e.target.reset();
    document.getElementById('scoreDate').value = new Date().toISOString().split('T')[0];
}

// ==================== TEACHER: SCORE TABLE ====================
function loadScoreTable() {
    const scores = DB.get('scores');
    const students = DB.get('students');
    const tbody = document.querySelector('#allScoresTable tbody');

    if (scores.length === 0) {
        tbody.innerHTML = `<tr><td colspan="9"><div class="empty-state"><div class="empty-icon">📋</div><h4>Одоогоор дүн оруулаагүй байна</h4></div></td></tr>`;
        return;
    }

    renderScoreTable(scores, students, tbody);
}

function renderScoreTable(scores, students, tbody) {
    tbody.innerHTML = scores.slice().reverse().map(s => {
        const student = students.find(st => st.id === s.studentId);
        return `<tr>
            <td><strong>${student ? student.name : 'Тодорхойгүй'}</strong></td>
            <td><span class="chip chip-blue">${s.studentId}</span></td>
            <td>${s.subject}</td>
            <td><span class="chip chip-green">${s.examType}</span></td>
            <td><strong>${getGradeBadge(s.score)}</strong></td>
            <td>${getGradeLabel(s.score)}</td>
            <td>${formatDate(s.date)}</td>
            <td>${s.note || '—'}</td>
            <td>
                <button class="btn btn-primary btn-sm" onclick="editScore('${s.id}')">✏️</button>
                <button class="btn btn-danger btn-sm" onclick="deleteScore('${s.id}')">🗑️</button>
            </td>
        </tr>`;
    }).join('');
}

function filterScoreTable() {
    const search = document.getElementById('scoreTableSearch').value.toLowerCase();
    const subject = document.getElementById('scoreTableSubject').value;
    const exam = document.getElementById('scoreTableExam').value;

    let scores = DB.get('scores');
    const students = DB.get('students');

    if (search) {
        scores = scores.filter(s => {
            const student = students.find(st => st.id === s.studentId);
            const name = student ? student.name.toLowerCase() : '';
            return name.includes(search) || s.studentId.toLowerCase().includes(search) || s.subject.toLowerCase().includes(search);
        });
    }
    if (subject) {
        scores = scores.filter(s => s.subject === subject);
    }
    if (exam) {
        scores = scores.filter(s => s.examType === exam);
    }

    const tbody = document.querySelector('#allScoresTable tbody');
    renderScoreTable(scores, students, tbody);
}

function editScore(id) {
    const scores = DB.get('scores');
    const score = scores.find(s => s.id === id);
    if (!score) return;

    document.getElementById('editScoreId').value = id;
    document.getElementById('editScoreValue').value = score.score;
    document.getElementById('editScoreNote').value = score.note || '';
    openModal('editScoreModal');
}

function handleEditScore(e) {
    e.preventDefault();
    const id = document.getElementById('editScoreId').value;
    const score = parseInt(document.getElementById('editScoreValue').value);
    const note = document.getElementById('editScoreNote').value.trim();

    const scores = DB.get('scores');
    const idx = scores.findIndex(s => s.id === id);
    if (idx !== -1) {
        scores[idx].score = score;
        scores[idx].note = note;
        DB.set('scores', scores);
    }

    closeModal('editScoreModal');
    loadScoreTable();
    showToast('success', 'Дүн амжилттай засварлагдлаа');
}

function deleteScore(id) {
    if (!confirm('Энэ дүнг устгах уу?')) return;
    let scores = DB.get('scores');
    scores = scores.filter(s => s.id !== id);
    DB.set('scores', scores);
    loadScoreTable();
    showToast('success', 'Дүн устгагдлаа');
}

// ==================== TEACHER: REPORTS ====================
function loadReports() {
    const scores = DB.get('scores');
    const students = DB.get('students');

    // Subject averages
    const subjectData = {};
    scores.forEach(s => {
        if (!subjectData[s.subject]) {
            subjectData[s.subject] = { scores: [], total: 0, count: 0 };
        }
        subjectData[s.subject].scores.push(s);
        subjectData[s.subject].total += s.score;
        subjectData[s.subject].count++;
    });

    let subjectHTML = '';
    Object.keys(subjectData).forEach(subject => {
        const data = subjectData[subject];
        const avg = (data.total / data.count).toFixed(1);
        const pct = avg;
        const colorClass = pct >= 90 ? 'green' : pct >= 75 ? 'blue' : pct >= 50 ? 'orange' : 'red';

        subjectHTML += `
            <div style="margin-bottom:20px;">
                <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:6px;">
                    <strong>${subject}</strong>
                    <span>${avg} оноо (${data.count} дүн)</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill ${colorClass}" style="width:${pct}%"></div>
                </div>
            </div>
        `;
    });

    document.getElementById('subjectReport').innerHTML = subjectHTML || '<div class="empty-state"><p>Өгөгдөл байхгүй</p></div>';

    // Top students
    const studentAvg = {};
    scores.forEach(s => {
        if (!studentAvg[s.studentId]) {
            studentAvg[s.studentId] = { total: 0, count: 0 };
        }
        studentAvg[s.studentId].total += s.score;
        studentAvg[s.studentId].count++;
    });

    const topStudents = Object.keys(studentAvg)
        .map(id => ({
            id,
            avg: (studentAvg[id].total / studentAvg[id].count).toFixed(1),
            count: studentAvg[id].count
        }))
        .sort((a, b) => b.avg - a.avg)
        .slice(0, 10);

    let topHTML = '<table><thead><tr><th>#</th><th>Сурагч</th><th>ID</th><th>Дундаж</th><th>Дүнгийн тоо</th></tr></thead><tbody>';
    topStudents.forEach((s, i) => {
        const student = students.find(st => st.id === s.id);
        const medal = i === 0 ? '🥇' : i === 1 ? '🥈' : i === 2 ? '🥉' : `${i + 1}`;
        topHTML += `<tr>
            <td>${medal}</td>
            <td><strong>${student ? student.name : 'Тодорхойгүй'}</strong></td>
            <td><span class="chip chip-blue">${s.id}</span></td>
            <td><strong>${getGradeBadge(s.avg)}</strong></td>
            <td>${s.count}</td>
        </tr>`;
    });
    topHTML += '</tbody></table>';

    document.getElementById('topStudents').innerHTML = topStudents.length > 0 ? topHTML : '<div class="empty-state"><p>Өгөгдөл байхгүй</p></div>';
}

// ==================== STUDENT: MY SCORES ====================
function loadMyScores() {
    const studentId = currentUser.studentId || currentUser.email?.split('@')[0];
    const students = DB.get('students');
    const scores = DB.get('scores');

    const student = students.find(s => s.id === studentId || s.userId === currentUser.id);
    const myScores = scores.filter(s => s.studentId === (student ? student.id : studentId));

    const avg = myScores.length > 0
        ? (myScores.reduce((sum, s) => sum + parseInt(s.score), 0) / myScores.length).toFixed(1)
        : 0;

    const maxScore = myScores.length > 0 ? Math.max(...myScores.map(s => s.score)) : 0;
    const minScore = myScores.length > 0 ? Math.min(...myScores.map(s => s.score)) : 0;

    document.getElementById('studentScoreOverview').innerHTML = `
        <div class="student-score-card">
            <div class="student-name">${student ? student.name : currentUser.name}</div>
            <div class="student-id">ID: ${student ? student.id : studentId} ${student && student.grade ? '| ' + student.grade : ''}</div>
            <div class="avg-score">${avg}</div>
            <div class="avg-label">Дундаж оноо</div>
            <div style="display:flex; justify-content:center; gap:30px; margin-top:20px;">
                <div>
                    <div style="font-size:1.5em; font-weight:700;">${maxScore}</div>
                    <div style="opacity:0.8; font-size:0.85em;">Хамгийн өндөр</div>
                </div>
                <div>
                    <div style="font-size:1.5em; font-weight:700;">${minScore}</div>
                    <div style="opacity:0.8; font-size:0.85em;">Хамгийн бага</div>
                </div>
                <div>
                    <div style="font-size:1.5em; font-weight:700;">${myScores.length}</div>
                    <div style="opacity:0.8; font-size:0.85em;">Нийт дүн</div>
                </div>
            </div>
        </div>
    `;

    if (myScores.length === 0) {
        document.getElementById('studentAllScores').innerHTML = '<div class="empty-state"><div class="empty-icon">📝</div><h4>Одоогоор дүн оруулаагүй байна</h4></div>';
        return;
    }

    let html = '';
    myScores.slice().reverse().forEach(s => {
        html += `
            <div class="subject-score">
                <div class="subject-info">
                    <div class="subject-icon" style="background:rgba(41,128,185,0.1); color:var(--primary-light);">📚</div>
                    <div>
                        <div class="subject-name">${s.subject}</div>
                        <div class="subject-exam">${s.examType} • ${formatDate(s.date)}</div>
                    </div>
                </div>
                <div class="score-value">${getGradeBadge(s.score)}</div>
            </div>
        `;
    });

    document.getElementById('studentAllScores').innerHTML = html;
}

// ==================== STUDENT: MY SUBJECTS ====================
function loadMySubjects() {
    const studentId = currentUser.studentId;
    const scores = DB.get('scores');
    const myScores = scores.filter(s => s.studentId === studentId);

    const subjectData = {};
    myScores.forEach(s => {
        if (!subjectData[s.subject]) {
            subjectData[s.subject] = [];
        }
        subjectData[s.subject].push(s);
    });

    let html = '';
    Object.keys(subjectData).forEach(subject => {
        const scores = subjectData[subject];
        const avg = (scores.reduce((sum, s) => sum + s.score, 0) / scores.length).toFixed(1);

        html += `
            <div class="card">
                <div class="card-header">
                    <h3>📚 ${subject}</h3>
                    <span>${getGradeBadge(avg)} <small style="color:var(--text-light); margin-left:8px;">Дундаж: ${avg}</small></span>
                </div>
                <div class="card-body">
        `;

        scores.forEach(s => {
            html += `
                <div class="subject-score">
                    <div class="subject-info">
                        <div class="subject-icon" style="background:rgba(39,174,96,0.1); color:var(--success);">📝</div>
                        <div>
                            <div class="subject-name">${s.examType}</div>
                            <div class="subject-exam">${formatDate(s.date)}${s.note ? ' • ' + s.note : ''}</div>
                        </div>
                    </div>
                    <div class="score-value">${getGradeBadge(s.score)}</div>
                </div>
            `;
        });

        html += '</div></div>';
    });

    document.getElementById('studentSubjects').innerHTML = html || '<div class="empty-state"><div class="empty-icon">📚</div><h4>Хичээлийн дүн байхгүй</h4></div>';
}

// ==================== STUDENT: MY PROFILE ====================
function loadMyProfile() {
    const studentId = currentUser.studentId;
    const students = DB.get('students');
    const student = students.find(s => s.id === studentId);

    const scores = DB.get('scores');
    const myScores = scores.filter(s => s.studentId === studentId);
    const subjects = [...new Set(myScores.map(s => s.subject))];

    let profileHTML = `
        <div style="text-align:center; margin-bottom:30px;">
            <div style="width:80px; height:80px; background:var(--primary); color:white; border-radius:50%; display:flex; align-items:center; justify-content:center; font-size:2em; margin:0 auto 15px;">👨‍🎓</div>
            <h3>${currentUser.name}</h3>
            <p style="color:var(--text-light);">${currentUser.email}</p>
        </div>
        <div style="display:grid; grid-template-columns:1fr 1fr; gap:20px;">
            <div style="background:var(--bg); padding:16px; border-radius:10px;">
                <div style="font-size:0.8em; color:var(--text-light); margin-bottom:4px;">🆔 Сурагчийн ID</div>
                <div style="font-weight:700;">${studentId || '—'}</div>
            </div>
            <div style="background:var(--bg); padding:16px; border-radius:10px;">
                <div style="font-size:0.8em; color:var(--text-light); margin-bottom:4px;">🏫 Анги</div>
                <div style="font-weight:700;">${student ? student.grade : '—'}</div>
            </div>
            <div style="background:var(--bg); padding:16px; border-radius:10px;">
                <div style="font-size:0.8em; color:var(--text-light); margin-bottom:4px;">📚 Хичээлийн тоо</div>
                <div style="font-weight:700;">${subjects.length}</div>
            </div>
            <div style="background:var(--bg); padding:16px; border-radius:10px;">
                <div style="font-size:0.8em; color:var(--text-light); margin-bottom:4px;">📝 Нийт дүн</div>
                <div style="font-weight:700;">${myScores.length}</div>
            </div>
        </div>
        ${subjects.length > 0 ? `
        <div style="margin-top:20px;">
            <h4 style="margin-bottom:10px;">📚 Хичээлүүд:</h4>
            ${subjects.map(s => `<span class="chip chip-green" style="margin:4px;">${s}</span>`).join('')}
        </div>
        ` : ''}
    `;

    document.getElementById('studentProfile').innerHTML = profileHTML;
}

// ==================== SETTINGS ====================
function exportData() {
    const data = {
        students: DB.get('students'),
        scores: DB.get('scores'),
        users: DB.get('users'),
        exportDate: new Date().toISOString(),
        school: 'Мөст сумын ЕБС'
    };

    const blob = new Blob([JSON.stringify(data, null, 2)], { type: 'application/json' });
    const url = URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.href = url;
    a.download = `most_school_backup_${new Date().toISOString().split('T')[0]}.json`;
    a.click();
    URL.revokeObjectURL(url);
    showToast('success', 'Өгөгдөл экспортлогдлоо');
}

function importData(e) {
    const file = e.target.files[0];
    if (!file) return;

    const reader = new FileReader();
    reader.onload = function(ev) {
        try {
            const data = JSON.parse(ev.target.result);
            if (data.students) DB.set('students', data.students);
            if (data.scores) DB.set('scores', data.scores);
            if (data.users) DB.set('users', data.users);
            showToast('success', 'Өгөгдөл амжилттай импортлогдлоо');
            if (currentUser.role === 'teacher') loadTeacherDashboard();
        } catch {
            showToast('error', 'Файлын формат буруу байна');
        }
    };
    reader.readAsText(file);
}

function clearAllData() {
    if (!confirm('⚠️ БҮХ ӨГӨГДЛИЙГ УСТГАХ УУ?\n\nЭнэ үйлдлийг буцаах боломжгүй!')) return;
    if (!confirm('Дахин баталгаажуулна уу: Бүх сурагч, дүн, хэрэглэгчийн мэдээлэл устах болно.')) return;

    localStorage.removeItem('most_school_students');
    localStorage.removeItem('most_school_scores');
    localStorage.removeItem('most_school_users');

    showToast('info', 'Бүх өгөгдөл устгагдлаа');
    setTimeout(() => location.reload(), 1000);
}

// ==================== HELPERS ====================
function getGradeBadge(score) {
    score = parseInt(score);
    if (score >= 90) return `<span class="grade-badge grade-excellent">${score} - Онц</span>`;
    if (score >= 75) return `<span class="grade-badge grade-good">${score} - Сайн</span>`;
    if (score >= 50) return `<span class="grade-badge grade-average">${score} - Хангалттай</span>`;
    return `<span class="grade-badge grade-poor">${score} - Хангалтгүй</span>`;
}

function getGradeLabel(score) {
    score = parseInt(score);
    if (score >= 90) return 'Онц';
    if (score >= 75) return 'Сайн';
    if (score >= 50) return 'Хангалттай';
    return 'Хангалтгүй';
}

function formatDate(dateStr) {
    if (!dateStr) return '—';
    const d = new Date(dateStr);
    return d.toLocaleDateString('mn-MN', { year: 'numeric', month: 'long', day: 'numeric' });
}

// ==================== INIT ====================
init();
</script>

</body>
</html>
