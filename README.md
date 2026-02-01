<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🏆 Turnamen Catur Championship 2024</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #1a1a2e;
            --secondary: #16213e;
            --accent: #e94560;
            --gold: #ffd700;
            --silver: #c0c0c0;
            --bronze: #cd7f32;
            --text: #ffffff;
            --text-muted: #a0a0a0;
            --success: #00ff88;
            --warning: #ffaa00;
            --danger: #ff4444;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            min-height: 100vh;
            color: var(--text);
        }

        /* Header */
        .header {
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a3e 50%, #2d1b4e 100%);
            padding: 20px 0;
            border-bottom: 3px solid var(--accent);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-content {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo-icon {
            font-size: 3rem;
            animation: rotate 10s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotateY(0deg); }
            to { transform: rotateY(360deg); }
        }

        .logo-text h1 {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(45deg, var(--gold), #fff, var(--gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .logo-text p {
            font-size: 0.9rem;
            color: var(--accent);
        }

        .live-badge {
            background: var(--accent);
            color: white;
            padding: 8px 20px;
            border-radius: 25px;
            font-weight: 600;
            animation: pulse 2s infinite;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        @keyframes pulse {
            0%, 100% { box-shadow: 0 0 0 0 rgba(233, 69, 96, 0.7); }
            50% { box-shadow: 0 0 0 15px rgba(233, 69, 96, 0); }
        }

        /* Navigation */
        .nav {
            background: rgba(0,0,0,0.3);
            padding: 15px 0;
            position: sticky;
            top: 90px;
            z-index: 999;
            backdrop-filter: blur(10px);
        }

        .nav-content {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: center;
            gap: 10px;
            flex-wrap: wrap;
        }

        .nav-btn {
            background: transparent;
            border: 2px solid rgba(255,255,255,0.2);
            color: var(--text);
            padding: 12px 25px;
            border-radius: 30px;
            cursor: pointer;
            font-family: inherit;
            font-weight: 500;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .nav-btn:hover, .nav-btn.active {
            background: var(--accent);
            border-color: var(--accent);
            transform: translateY(-2px);
        }

        .nav-btn.admin-btn {
            border-color: var(--gold);
            color: var(--gold);
        }

        .nav-btn.admin-btn:hover, .nav-btn.admin-btn.active {
            background: var(--gold);
            color: #000;
        }

        /* Main Container */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 30px 20px;
        }

        /* Section */
        .section {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section-title {
            text-align: center;
            margin-bottom: 40px;
        }

        .section-title h2 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            background: linear-gradient(45deg, var(--gold), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .section-title p {
            color: var(--text-muted);
        }

        /* Info Cards */
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .info-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.05) 100%);
            border-radius: 20px;
            padding: 25px;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
            transition: transform 0.3s ease;
        }

        .info-card:hover {
            transform: translateY(-5px);
        }

        .info-card i {
            font-size: 2.5rem;
            color: var(--accent);
            margin-bottom: 15px;
        }

        .info-card h3 {
            font-size: 2rem;
            color: var(--gold);
        }

        .info-card p {
            color: var(--text-muted);
            margin-top: 5px;
        }

        /* Countdown */
        .countdown-container {
            background: linear-gradient(135deg, #2d1b4e 0%, #1a1a3e 100%);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            margin-bottom: 40px;
            border: 2px solid var(--accent);
        }

        .countdown-container h3 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--accent);
        }

        .countdown {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .countdown-item {
            background: rgba(0,0,0,0.3);
            padding: 20px 30px;
            border-radius: 15px;
            min-width: 100px;
        }

        .countdown-item .number {
            font-size: 3rem;
            font-weight: 800;
            color: var(--gold);
        }

        .countdown-item .label {
            font-size: 0.9rem;
            color: var(--text-muted);
        }

        /* Bracket Styles */
        .bracket-container {
            overflow-x: auto;
            padding: 20px 0;
        }

        .bracket {
            display: flex;
            gap: 60px;
            min-width: max-content;
            padding: 20px;
        }

        .round {
            display: flex;
            flex-direction: column;
            gap: 20px;
            min-width: 280px;
        }

        .round-title {
            text-align: center;
            padding: 15px;
            background: linear-gradient(135deg, var(--accent) 0%, #ff6b8a 100%);
            border-radius: 10px;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .match {
            background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.05) 100%);
            border-radius: 15px;
            padding: 15px;
            border: 1px solid rgba(255,255,255,0.1);
            position: relative;
        }

        .match.live {
            border-color: var(--success);
            box-shadow: 0 0 20px rgba(0, 255, 136, 0.3);
        }

        .match.live::before {
            content: '🔴 LIVE';
            position: absolute;
            top: -10px;
            right: 10px;
            background: #ff0000;
            padding: 3px 10px;
            border-radius: 10px;
            font-size: 0.7rem;
            font-weight: 700;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        .match-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
            font-size: 0.8rem;
            color: var(--text-muted);
        }

        .match-time {
            background: rgba(255,255,255,0.1);
            padding: 3px 10px;
            border-radius: 5px;
        }

        .player {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px;
            border-radius: 8px;
            margin: 5px 0;
            background: rgba(0,0,0,0.2);
            transition: all 0.3s ease;
        }

        .player.winner {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.2) 0%, rgba(0, 255, 136, 0.1) 100%);
            border-left: 3px solid var(--success);
        }

        .player.loser {
            opacity: 0.5;
        }

        .player-info {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .player-avatar {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent) 0%, var(--gold) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 0.9rem;
        }

        .player-name {
            font-weight: 500;
        }

        .player-rating {
            font-size: 0.8rem;
            color: var(--text-muted);
        }

        .player-score {
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--gold);
        }

        .vs-divider {
            text-align: center;
            color: var(--accent);
            font-weight: 700;
            font-size: 0.8rem;
        }

        /* Schedule Table */
        .schedule-container {
            overflow-x: auto;
        }

        .schedule-table {
            width: 100%;
            border-collapse: collapse;
            background: rgba(255,255,255,0.05);
            border-radius: 15px;
            overflow: hidden;
        }

        .schedule-table th,
        .schedule-table td {
            padding: 15px 20px;
            text-align: left;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .schedule-table th {
            background: linear-gradient(135deg, var(--accent) 0%, #ff6b8a 100%);
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.85rem;
        }

        .schedule-table tr:hover {
            background: rgba(255,255,255,0.05);
        }

        .status-badge {
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .status-upcoming {
            background: rgba(255, 170, 0, 0.2);
            color: var(--warning);
        }

        .status-live {
            background: rgba(255, 0, 0, 0.2);
            color: #ff4444;
            animation: pulse 2s infinite;
        }

        .status-completed {
            background: rgba(0, 255, 136, 0.2);
            color: var(--success);
        }

        .status-scheduled {
            background: rgba(255, 255, 255, 0.1);
            color: var(--text-muted);
        }

        /* Participants Grid */
        .participants-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
        }

        .participant-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.05) 100%);
            border-radius: 20px;
            padding: 25px;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .participant-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
        }

        .participant-card.champion {
            border: 2px solid var(--gold);
            box-shadow: 0 0 30px rgba(255, 215, 0, 0.3);
        }

        .participant-rank {
            position: absolute;
            top: 15px;
            left: 15px;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            font-size: 0.9rem;
        }

        .rank-1 { background: var(--gold); color: #000; }
        .rank-2 { background: var(--silver); color: #000; }
        .rank-3 { background: var(--bronze); color: #000; }
        .rank-other { background: rgba(255,255,255,0.2); }

        .participant-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent) 0%, var(--gold) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            font-weight: 800;
            margin: 0 auto 15px;
        }

        .participant-name {
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 5px;
        }

        .participant-country {
            color: var(--text-muted);
            margin-bottom: 15px;
        }

        .participant-stats {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        .stat {
            text-align: center;
        }

        .stat-value {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--gold);
        }

        .stat-label {
            font-size: 0.75rem;
            color: var(--text-muted);
        }

        /* Standings Table */
        .standings-table {
            width: 100%;
            border-collapse: collapse;
            background: rgba(255,255,255,0.05);
            border-radius: 15px;
            overflow: hidden;
        }

        .standings-table th,
        .standings-table td {
            padding: 15px 20px;
            text-align: center;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .standings-table th {
            background: linear-gradient(135deg, var(--accent) 0%, #ff6b8a 100%);
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.85rem;
        }

        .standings-table tr:hover {
            background: rgba(255,255,255,0.05);
        }

        .standings-table tr:nth-child(1) td {
            background: rgba(255, 215, 0, 0.1);
        }

        .standings-table tr:nth-child(2) td {
            background: rgba(192, 192, 192, 0.1);
        }

        .standings-table tr:nth-child(3) td {
            background: rgba(205, 127, 50, 0.1);
        }

        .player-cell {
            display: flex;
            align-items: center;
            gap: 10px;
            text-align: left;
        }

        .medal {
            font-size: 1.5rem;
        }

        /* Rules Section */
        .rules-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .rule-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.05) 100%);
            border-radius: 20px;
            padding: 25px;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .rule-card h3 {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 15px;
            color: var(--accent);
        }

        .rule-card ul {
            list-style: none;
        }

        .rule-card li {
            padding: 8px 0;
            padding-left: 25px;
            position: relative;
            color: var(--text-muted);
        }

        .rule-card li::before {
            content: '♟';
            position: absolute;
            left: 0;
            color: var(--gold);
        }

        /* Prize Pool */
        .prize-container {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .prize-card {
            text-align: center;
            padding: 30px;
            border-radius: 20px;
            min-width: 200px;
            transition: transform 0.3s ease;
        }

        .prize-card:hover {
            transform: translateY(-10px);
        }

        .prize-1 {
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.3) 0%, rgba(255, 215, 0, 0.1) 100%);
            border: 2px solid var(--gold);
            order: 2;
            transform: scale(1.1);
        }

        .prize-2 {
            background: linear-gradient(135deg, rgba(192, 192, 192, 0.3) 0%, rgba(192, 192, 192, 0.1) 100%);
            border: 2px solid var(--silver);
            order: 1;
        }

        .prize-3 {
            background: linear-gradient(135deg, rgba(205, 127, 50, 0.3) 0%, rgba(205, 127, 50, 0.1) 100%);
            border: 2px solid var(--bronze);
            order: 3;
        }

        .prize-icon {
            font-size: 4rem;
            margin-bottom: 15px;
        }

        .prize-place {
            font-size: 1.2rem;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .prize-amount {
            font-size: 2rem;
            font-weight: 800;
            color: var(--gold);
        }

        /* Admin Panel */
        .admin-section {
            background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.05) 100%);
            border-radius: 20px;
            padding: 30px;
            margin-top: 30px;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .admin-section h3 {
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--gold);
        }

        .admin-form {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 5px;
        }

        .form-group label {
            font-size: 0.9rem;
            color: var(--text-muted);
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            padding: 12px 15px;
            border-radius: 10px;
            border: 1px solid rgba(255,255,255,0.2);
            background: rgba(0,0,0,0.3);
            color: var(--text);
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent);
        }

        .btn {
            padding: 12px 25px;
            border-radius: 10px;
            border: none;
            font-family: inherit;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            justify-content: center;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--accent) 0%, #ff6b8a 100%);
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(233, 69, 96, 0.4);
        }

        .btn-success {
            background: linear-gradient(135deg, #00c853 0%, #00e676 100%);
            color: white;
        }

        .btn-warning {
            background: linear-gradient(135deg, #ff9800 0%, #ffc107 100%);
            color: #000;
        }

        .btn-danger {
            background: linear-gradient(135deg, #f44336 0%, #ff5252 100%);
            color: white;
        }

        .btn-info {
            background: linear-gradient(135deg, #2196f3 0%, #64b5f6 100%);
            color: white;
        }

        .btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(5px);
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 20px;
            padding: 30px;
            max-width: 500px;
            width: 90%;
            border: 2px solid var(--accent);
            animation: modalSlide 0.3s ease;
        }

        @keyframes modalSlide {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .modal-header h3 {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .modal-close {
            background: none;
            border: none;
            color: var(--text);
            font-size: 1.5rem;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .modal-close:hover {
            color: var(--accent);
        }

        .modal-body {
            margin-bottom: 20px;
        }

        .modal-footer {
            display: flex;
            gap: 10px;
            justify-content: flex-end;
        }

        /* Login Form */
        .login-container {
            text-align: center;
        }

        .login-icon {
            font-size: 4rem;
            color: var(--gold);
            margin-bottom: 20px;
        }

        .login-container h3 {
            margin-bottom: 10px;
        }

        .login-container p {
            color: var(--text-muted);
            margin-bottom: 25px;
        }

        .password-input-group {
            position: relative;
            margin-bottom: 20px;
        }

        .password-input-group input {
            width: 100%;
            padding: 15px 50px 15px 20px;
            border-radius: 10px;
            border: 2px solid rgba(255,255,255,0.2);
            background: rgba(0,0,0,0.3);
            color: var(--text);
            font-size: 1rem;
            font-family: inherit;
        }

        .password-input-group input:focus {
            outline: none;
            border-color: var(--gold);
        }

        .password-toggle {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            color: var(--text-muted);
            cursor: pointer;
        }

        .login-error {
            color: var(--danger);
            margin-bottom: 15px;
            display: none;
        }

        .login-error.show {
            display: block;
        }

        /* Player Management Table */
        .player-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        .player-table th,
        .player-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .player-table th {
            background: rgba(0,0,0,0.3);
            font-weight: 600;
            color: var(--gold);
        }

        .player-table tr:hover {
            background: rgba(255,255,255,0.05);
        }

        .player-actions {
            display: flex;
            gap: 5px;
        }

        .btn-sm {
            padding: 6px 12px;
            font-size: 0.8rem;
        }

        /* Admin Logged In Status */
        .admin-status {
            display: flex;
            align-items: center;
            gap: 15px;
            background: rgba(0,255,136,0.1);
            padding: 15px 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            border: 1px solid var(--success);
        }

        .admin-status i {
            font-size: 1.5rem;
            color: var(--success);
        }

        .admin-status-text {
            flex: 1;
        }

        .admin-status-text strong {
            color: var(--success);
        }

        /* Stats Chart */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .stats-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.05) 100%);
            border-radius: 20px;
            padding: 25px;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .stats-card h4 {
            margin-bottom: 20px;
            color: var(--accent);
        }

        .progress-bar {
            background: rgba(0,0,0,0.3);
            border-radius: 10px;
            height: 25px;
            margin: 10px 0;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: flex-end;
            padding-right: 10px;
            font-size: 0.8rem;
            font-weight: 600;
            transition: width 1s ease;
        }

        .progress-win {
            background: linear-gradient(135deg, #00c853 0%, #00e676 100%);
        }

        .progress-draw {
            background: linear-gradient(135deg, #ff9800 0%, #ffc107 100%);
            color: #000;
        }

        .progress-loss {
            background: linear-gradient(135deg, #e94560 0%, #ff6b8a 100%);
        }

        /* Footer */
        .footer {
            background: rgba(0,0,0,0.5);
            padding: 40px 20px;
            margin-top: 50px;
            text-align: center;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }

        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255,255,255,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text);
            font-size: 1.3rem;
            transition: all 0.3s ease;
            text-decoration: none;
        }

        .social-link:hover {
            background: var(--accent);
            transform: translateY(-5px);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }

            .logo-text h1 {
                font-size: 1.4rem;
            }

            .countdown-item .number {
                font-size: 2rem;
            }

            .prize-1 {
                transform: scale(1);
                order: 1;
            }

            .prize-2 { order: 2; }
            .prize-3 { order: 3; }

            .section-title h2 {
                font-size: 1.8rem;
            }

            .nav-btn {
                padding: 10px 15px;
                font-size: 0.85rem;
            }

            .player-table {
                font-size: 0.85rem;
            }

            .player-table th,
            .player-table td {
                padding: 8px 10px;
            }
        }

        /* Toast Notification */
        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            padding: 15px 25px;
            border-radius: 10px;
            font-weight: 600;
            transform: translateX(150%);
            transition: transform 0.3s ease;
            z-index: 3000;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .toast.show {
            transform: translateX(0);
        }

        .toast.success {
            background: var(--success);
            color: #000;
        }

        .toast.error {
            background: var(--danger);
            color: white;
        }

        .toast.warning {
            background: var(--warning);
            color: #000;
        }

        /* Filter Buttons */
        .filter-buttons {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .filter-btn {
            background: rgba(255,255,255,0.1);
            border: none;
            color: var(--text);
            padding: 10px 20px;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: inherit;
        }

        .filter-btn:hover, .filter-btn.active {
            background: var(--accent);
        }

        /* Empty State */
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            color: var(--text-muted);
        }

        .empty-state i {
            font-size: 4rem;
            margin-bottom: 20px;
            opacity: 0.5;
        }

        .empty-state h4 {
            margin-bottom: 10px;
            color: var(--text);
        }

        /* Tabs */
        .admin-tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .admin-tab {
            background: rgba(255,255,255,0.1);
            border: none;
            color: var(--text);
            padding: 12px 25px;
            border-radius: 10px;
            cursor: pointer;
            font-family: inherit;
            font-weight: 500;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .admin-tab:hover, .admin-tab.active {
            background: var(--gold);
            color: #000;
        }

        .admin-tab-content {
            display: none;
        }

        .admin-tab-content.active {
            display: block;
        }

        /* Confirmation Modal */
        .confirm-icon {
            font-size: 4rem;
            color: var(--warning);
            margin-bottom: 20px;
        }

        .confirm-text {
            text-align: center;
            margin-bottom: 20px;
        }

        .confirm-text h4 {
            margin-bottom: 10px;
        }

        .confirm-text p {
            color: var(--text-muted);
        }

        /* Search Box */
        .search-box {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }

        .search-box input {
            flex: 1;
            padding: 12px 20px;
            border-radius: 10px;
            border: 1px solid rgba(255,255,255,0.2);
            background: rgba(0,0,0,0.3);
            color: var(--text);
            font-family: inherit;
        }

        .search-box input:focus {
            outline: none;
            border-color: var(--accent);
        }

        /* Badge */
        .badge {
            display: inline-block;
            padding: 3px 10px;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
        }

        .badge-gm { background: var(--gold); color: #000; }
        .badge-im { background: var(--silver); color: #000; }
        .badge-fm { background: var(--bronze); color: #000; }
        .badge-cm { background: rgba(255,255,255,0.3); color: var(--text); }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="header-content">
            <div class="logo">
                <span class="logo-icon">♛</span>
                <div class="logo-text">
                    <h1>Turnamen Catur Kuda Indo</h1>
                    <p>CUP 1 2026 </p>
                </div>
            </div>
            <div class="live-badge">
                <span class="pulse-dot">●</span>
                <span id="liveStatus">TURNAMEN AKTIF</span>
            </div>
        </div>
    </header>

    <!-- Navigation -->
    <nav class="nav">
        <div class="nav-content">
            <button class="nav-btn active" onclick="showSection('dashboard', this)">
                <i class="fas fa-home"></i> Dashboard
            </button>
            <button class="nav-btn" onclick="showSection('bracket', this)">
                <i class="fas fa-sitemap"></i> Bracket
            </button>
            <button class="nav-btn" onclick="showSection('schedule', this)">
                <i class="fas fa-calendar-alt"></i> Jadwal
            </button>
            <button class="nav-btn" onclick="showSection('participants', this)">
                <i class="fas fa-users"></i> Peserta
            </button>
            <button class="nav-btn" onclick="showSection('standings', this)">
                <i class="fas fa-trophy"></i> Klasemen
            </button>
            <button class="nav-btn" onclick="showSection('stats', this)">
                <i class="fas fa-chart-bar"></i> Statistik
            </button>
            <button class="nav-btn" onclick="showSection('rules', this)">
                <i class="fas fa-book"></i> Peraturan
            </button>
            <button class="nav-btn admin-btn" onclick="accessAdmin(this)">
                <i class="fas fa-lock"></i> <span id="adminBtnText">Admin</span>
            </button>
        </div>
    </nav>

    <div class="container">
        <!-- Dashboard Section -->
        <section id="dashboard" class="section active">
            <div class="section-title">
                <h2>🏆 Dashboard Turnamen</h2>
                <p>Selamat datang di catur kuda indo 2026</p>
            </div>

            <!-- Countdown -->
            <div class="countdown-container">
                <h3><i class="fas fa-clock"></i> Turnamen Dimulai Dalam</h3>
                <div class="countdown">
                    <div class="countdown-item">
                        <div class="number" id="days">00</div>
                        <div class="label">Hari</div>
                    </div>
                    <div class="countdown-item">
                        <div class="number" id="hours">00</div>
                        <div class="label">Jam</div>
                    </div>
                    <div class="countdown-item">
                        <div class="number" id="minutes">00</div>
                        <div class="label">Menit</div>
                    </div>
                    <div class="countdown-item">
                        <div class="number" id="seconds">00</div>
                        <div class="label">Detik</div>
                    </div>
                </div>
            </div>

            <!-- Info Cards -->
            <div class="info-grid">
                <div class="info-card">
                    <i class="fas fa-users"></i>
                    <h3 id="totalParticipants">0</h3>
                    <p>Total Peserta</p>
                </div>
                <div class="info-card">
                    <i class="fas fa-gamepad"></i>
                    <h3 id="totalMatches">0</h3>
                    <p>Total Pertandingan</p>
                </div>
                <div class="info-card">
                    <i class="fas fa-check-circle"></i>
                    <h3 id="completedMatches">0</h3>
                    <p>Selesai</p>
                </div>
                <div class="info-card">
                    <i class="fas fa-money-bill-wave"></i>
                    <h3>1000,000</h3>
                    <p>Total Hadiah</p>
                </div>
            </div>

            <!-- Prize Pool -->
            <div class="section-title">
                <h2>💰 Hadiah Turnamen</h2>
            </div>
            <div class="prize-container">
                <div class="prize-card prize-3">
                    <div class="prize-icon">🏆</div>
                    <div class="prize-place">Juara 2</div>
                    <div class="prize-amount">300,000</div>
                </div>
                <div class="prize-card prize-1">
                    <div class="prize-icon">🏆</div>
                    <div class="prize-place">Juara 1</div>
                    <div class="prize-amount">500,000</div>
                </div>
                <div class="prize-card prize-3">
                    <div class="prize-icon">🏆</div>
                    <div class="prize-place">Juara 3</div>
                    <div class="prize-amount">200,000</div>
                </div>
                <div class="prize-card prize-3">
                    <div class="prize-icon">🏆</div>
                    <div class="prize-place">Juara 4</div>
                    <div class="prize-amount">100,000</div>
                </div>
            </div>
        </section>

        <!-- Bracket Section -->
        <section id="bracket" class="section">
            <div class="section-title">
                <h2>🏅 Bracket Turnamen</h2>
                <p>Format Single Elimination - 16 Peserta</p>
            </div>

            <div class="bracket-container">
                <div class="bracket" id="bracketContainer">
                    <!-- Will be generated dynamically -->
                </div>
            </div>
        </section>

        <!-- Schedule Section -->
        <section id="schedule" class="section">
            <div class="section-title">
                <h2>📅 Jadwal Pertandingan</h2>
                <p>Jadwal lengkap semua pertandingan</p>
            </div>

            <div class="filter-buttons">
                <button class="filter-btn active" onclick="filterSchedule('all', this)">Semua</button>
                <button class="filter-btn" onclick="filterSchedule('upcoming', this)">Akan Datang</button>
                <button class="filter-btn" onclick="filterSchedule('live', this)">Live</button>
                <button class="filter-btn" onclick="filterSchedule('completed', this)">Selesai</button>
            </div>

            <div class="schedule-container">
                <table class="schedule-table">
                    <thead>
                        <tr>
                            <th>No</th>
                            <th>Tanggal</th>
                            <th>Waktu</th>
                            <th>Babak</th>
                            <th>Pemain 1</th>
                            <th>VS</th>
                            <th>Pemain 2</th>
                            <th>Hasil</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody id="scheduleTable">
                        <!-- Will be generated dynamically -->
                    </tbody>
                </table>
            </div>
        </section>

        <!-- Participants Section -->
        <section id="participants" class="section">
            <div class="section-title">
                <h2>👥 Daftar Peserta</h2>
                <p id="participantsSubtitle">Daftar peserta turnamen</p>
            </div>

            <div class="participants-grid" id="participantsGrid">
                <!-- Will be generated dynamically -->
            </div>
        </section>

        <!-- Standings Section -->
        <section id="standings" class="section">
            <div class="section-title">
                <h2>📊 Klasemen Sementara</h2>
                <p>Peringkat berdasarkan performa turnamen</p>
            </div>

            <div class="schedule-container">
                <table class="standings-table">
                    <thead>
                        <tr>
                            <th>Peringkat</th>
                            <th>Pemain</th>
                            <th>Negara</th>
                            <th>Rating</th>
                            <th>Main</th>
                            <th>Menang</th>
                            <th>Seri</th>
                            <th>Kalah</th>
                            <th>Poin</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody id="standingsTable">
                        <!-- Will be generated dynamically -->
                    </tbody>
                </table>
            </div>
        </section>

        <!-- Statistics Section -->
        <section id="stats" class="section">
            <div class="section-title">
                <h2>📈 Statistik Turnamen</h2>
                <p>Data dan analisis pertandingan</p>
            </div>

            <div class="stats-grid">
                <div class="stats-card">
                    <h4><i class="fas fa-chart-pie"></i> Hasil Pertandingan</h4>
                    <div>
                        <p>Kemenangan Putih</p>
                        <div class="progress-bar">
                            <div class="progress-fill progress-win" style="width: 45%;">45%</div>
                        </div>
                    </div>
                    <div>
                        <p>Remis</p>
                        <div class="progress-bar">
                            <div class="progress-fill progress-draw" style="width: 30%;">30%</div>
                        </div>
                    </div>
                    <div>
                        <p>Kemenangan Hitam</p>
                        <div class="progress-bar">
                            <div class="progress-fill progress-loss" style="width: 25%;">25%</div>
                        </div>
                    </div>
                </div>

                <div class="stats-card">
                    <h4><i class="fas fa-clock"></i> Durasi Rata-rata</h4>
                    <div style="text-align: center; padding: 20px;">
                        <div style="font-size: 3rem; font-weight: 800; color: var(--gold);">2:45</div>
                        <p style="color: var(--text-muted);">Jam per pertandingan</p>
                    </div>
                </div>

                <div class="stats-card">
                    <h4><i class="fas fa-chess"></i> Pembukaan Populer</h4>
                    <div style="margin-top: 15px;">
                        <div style="display: flex; justify-content: space-between; padding: 10px 0; border-bottom: 1px solid rgba(255,255,255,0.1);">
                            <span>Sicilian Defense</span>
                            <span style="color: var(--gold);">35%</span>
                        </div>
                        <div style="display: flex; justify-content: space-between; padding: 10px 0; border-bottom: 1px solid rgba(255,255,255,0.1);">
                            <span>Queen's Gambit</span>
                            <span style="color: var(--gold);">25%</span>
                        </div>
                        <div style="display: flex; justify-content: space-between; padding: 10px 0; border-bottom: 1px solid rgba(255,255,255,0.1);">
                            <span>Ruy Lopez</span>
                            <span style="color: var(--gold);">20%</span>
                        </div>
                        <div style="display: flex; justify-content: space-between; padding: 10px 0;">
                            <span>English Opening</span>
                            <span style="color: var(--gold);">15%</span>
                        </div>
                    </div>
                </div>

                <div class="stats-card">
                    <h4><i class="fas fa-star"></i> Top Performers</h4>
                    <div style="margin-top: 15px;" id="topPerformers">
                        <!-- Will be generated dynamically -->
                    </div>
                </div>
            </div>
        </section>

        <!-- Rules Section -->
        <section id="rules" class="section">
            <div class="section-title">
                <h2>📜 Peraturan Turnamen</h2>
                <p>Aturan dan ketentuan yang berlaku</p>
            </div>

            <div class="rules-container">
                <div class="rule-card">
                    <h3><i class="fas fa-gavel"></i> Peraturan Umum</h3>
                    <ul>
                        <li>Semua pertandingan menggunakan aturan FIDE</li>
                        <li>Format: Single Elimination</li>
                        <li>Peserta wajib hadir 15 menit sebelum pertandingan</li>
                        <li>Keterlambatan lebih dari 10 menit = walkover</li>
                        <li>Penggunaan alat elektronik dilarang keras</li>
                    </ul>
                </div>

                <div class="rule-card">
                    <h3><i class="fas fa-clock"></i> Kontrol Waktu</h3>
                    <ul>
                        <li>Babak 16 & Perempat: 90 menit + 30 detik/langkah</li>
                        <li>Semi Final: 120 menit + 30 detik/langkah</li>
                        <li>Final: Classical - 120 menit + 30 detik/langkah</li>
                        <li>Tiebreak: Rapid 15+10, lalu Blitz 5+3</li>
                        <li>Armageddon jika masih seri</li>
                    </ul>
                </div>

                <div class="rule-card">
                    <h3><i class="fas fa-trophy"></i> Sistem Penilaian</h3>
                    <ul>
                        <li>Menang: 1 poin</li>
                        <li>Seri: 0.5 poin</li>
                        <li>Kalah: 0 poin</li>
                        <li>Setiap babak: Best of 2 games</li>
                        <li>Final: Best of 4 games</li>
                    </ul>
                </div>

                <div class="rule-card">
                    <h3><i class="fas fa-ban"></i> Larangan</h3>
                    <ul>
                        <li>Dilarang menggunakan engine/software catur</li>
                        <li>Dilarang berkomunikasi dengan pihak luar</li>
                        <li>Dilarang meninggalkan area pertandingan</li>
                        <li>Dilarang mengganggu lawan</li>
                        <li>Pelanggaran = diskualifikasi</li>
                    </ul>
                </div>

                <div class="rule-card">
                    <h3><i class="fas fa-gift"></i> Hadiah</h3>
                    <ul>
                        <li>Juara 1: $25,000 + Trofi</li>
                        <li>Juara 2: $15,000 + Medali Perak</li>
                        <li>Juara 3: $10,000 + Medali Perunggu</li>
                        <li>Best Game Award: $1,000</li>
                        <li>Semua peserta mendapat sertifikat</li>
                    </ul>
                </div>

                <div class="rule-card">
                    <h3><i class="fas fa-info-circle"></i> Informasi Tambahan</h3>
                    <ul>
                        <li>Lokasi: Grand Chess Hall, Jakarta</li>
                        <li>Tanggal: 10 - 20 Januari 2024</li>
                        <li>Live streaming di YouTube & Twitch</li>
                        <li>Komentar oleh GM Indonesia</li>
                        <li>Semua game akan di-broadcast</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Admin Section -->
        <section id="admin" class="section">
            <div class="section-title">
                <h2>⚙️ Panel Admin</h2>
                <p>Kelola turnamen dan update hasil</p>
            </div>

            <!-- Admin Status -->
            <div class="admin-status">
                <i class="fas fa-user-shield"></i>
                <div class="admin-status-text">
                    <strong>Admin Mode Aktif</strong>
                    <p style="margin: 0; font-size: 0.85rem; color: var(--text-muted);">Anda memiliki akses penuh untuk mengelola turnamen</p>
                </div>
                <button class="btn btn-danger btn-sm" onclick="logoutAdmin()">
                    <i class="fas fa-sign-out-alt"></i> Logout
                </button>
            </div>

            <!-- Admin Tabs -->
            <div class="admin-tabs">
                <button class="admin-tab active" onclick="showAdminTab('players', this)">
                    <i class="fas fa-users"></i> Kelola Peserta
                </button>
                <button class="admin-tab" onclick="showAdminTab('matches', this)">
                    <i class="fas fa-chess-board"></i> Update Match
                </button>
                <button class="admin-tab" onclick="showAdminTab('schedule', this)">
                    <i class="fas fa-calendar"></i> Atur Jadwal
                </button>
                <button class="admin-tab" onclick="showAdminTab('settings', this)">
                    <i class="fas fa-cog"></i> Pengaturan
                </button>
            </div>

            <!-- Tab: Kelola Peserta -->
            <div id="tab-players" class="admin-tab-content active">
                <div class="admin-section">
                    <h3><i class="fas fa-user-plus"></i> Tambah Peserta Baru</h3>
                    <form class="admin-form" onsubmit="addParticipant(event)">
                        <div class="form-group">
                            <label>Nama Pemain *</label>
                            <input type="text" id="playerName" placeholder="Masukkan nama lengkap" required>
                        </div>
                        <div class="form-group">
                            <label>Rating FIDE *</label>
                            <input type="number" id="playerRating" placeholder="Contoh: 2500" required min="1000" max="3000">
                        </div>
                        <div class="form-group">
                            <label>Negara *</label>
                            <input type="text" id="playerCountry" placeholder="Contoh: Indonesia" required>
                        </div>
                        <div class="form-group">
                            <label>Bendera Emoji</label>
                            <input type="text" id="playerFlag" placeholder="Contoh: 🇮🇩" maxlength="4">
                        </div>
                        <div class="form-group">
                            <label>Gelar</label>
                            <select id="playerTitle">
                                <option value="GM">Grandmaster (GM)</option>
                                <option value="IM">International Master (IM)</option>
                                <option value="FM">FIDE Master (FM)</option>
                                <option value="CM">Candidate Master (CM)</option>
                                <option value="">Tanpa Gelar</option>
                            </select>
                        </div>
                        <div class="form-group" style="justify-content: flex-end;">
                            <button type="submit" class="btn btn-success">
                                <i class="fas fa-plus"></i> Tambah Peserta
                            </button>
                        </div>
                    </form>
                </div>

                <div class="admin-section">
                    <h3><i class="fas fa-list"></i> Daftar Peserta (<span id="playerCount">0</span>)</h3>
                    
                    <div class="search-box">
                        <input type="text" id="searchPlayer" placeholder="Cari peserta..." oninput="searchPlayers()">
                        <button class="btn btn-info" onclick="searchPlayers()">
                            <i class="fas fa-search"></i>
                        </button>
                    </div>

                    <div style="display: flex; gap: 10px; margin-bottom: 20px; flex-wrap: wrap;">
                        <button class="btn btn-danger" onclick="confirmResetAll()">
                            <i class="fas fa-trash-alt"></i> Reset Semua Peserta
                        </button>
                        <button class="btn btn-warning" onclick="loadSampleData()">
                            <i class="fas fa-database"></i> Load Data Contoh
                        </button>
                        <button class="btn btn-info" onclick="exportPlayers()">
                            <i class="fas fa-download"></i> Export Data
                        </button>
                        <button class="btn btn-primary" onclick="showImportModal()">
                            <i class="fas fa-upload"></i> Import Data
                        </button>
                    </div>

                    <div class="schedule-container">
                        <table class="player-table" id="playerTableAdmin">
                            <thead>
                                <tr>
                                    <th>No</th>
                                    <th>Nama</th>
                                    <th>Gelar</th>
                                    <th>Negara</th>
                                    <th>Rating</th>
                                    <th>W/D/L</th>
                                    <th>Status</th>
                                    <th>Aksi</th>
                                </tr>
                            </thead>
                            <tbody id="playerListAdmin">
                                <!-- Will be generated dynamically -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <!-- Tab: Update Match -->
            <div id="tab-matches" class="admin-tab-content">
                <div class="admin-section">
                    <h3><i class="fas fa-edit"></i> Update Hasil Pertandingan</h3>
                    <form class="admin-form" onsubmit="updateMatch(event)">
                        <div class="form-group">
                            <label>Pilih Pertandingan</label>
                            <select id="matchSelect">
                                <option value="">-- Pilih Match --</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label>Skor Pemain 1</label>
                            <input type="number" id="score1" step="0.5" min="0" max="10" placeholder="0">
                        </div>
                        <div class="form-group">
                            <label>Skor Pemain 2</label>
                            <input type="number" id="score2" step="0.5" min="0" max="10" placeholder="0">
                        </div>
                        <div class="form-group">
                            <label>Status</label>
                            <select id="matchStatus">
                                <option value="scheduled">Dijadwalkan</option>
                                <option value="live">Live</option>
                                <option value="completed">Selesai</option>
                            </select>
                        </div>
                        <div class="form-group" style="justify-content: flex-end;">
                            <button type="submit" class="btn btn-success">
                                <i class="fas fa-save"></i> Simpan Hasil
                            </button>
                        </div>
                    </form>
                </div>

                <div class="admin-section">
                    <h3><i class="fas fa-random"></i> Generate Bracket Otomatis</h3>
                    <p style="color: var(--text-muted); margin-bottom: 15px;">
                        Generate bracket secara otomatis berdasarkan rating pemain atau acak.
                    </p>
                    <div style="display: flex; gap: 10px; flex-wrap: wrap;">
                        <button class="btn btn-primary" onclick="generateBracket('rating')">
                            <i class="fas fa-sort-amount-down"></i> By Rating
                        </button>
                        <button class="btn btn-warning" onclick="generateBracket('random')">
                            <i class="fas fa-random"></i> Acak
                        </button>
                    </div>
                </div>
            </div>

            <!-- Tab: Atur Jadwal -->
            <div id="tab-schedule" class="admin-tab-content">
                <div class="admin-section">
                    <h3><i class="fas fa-calendar-plus"></i> Atur Jadwal Pertandingan</h3>
                    <form class="admin-form" onsubmit="addSchedule(event)">
                        <div class="form-group">
                            <label>Tanggal</label>
                            <input type="date" id="matchDate" required>
                        </div>
                        <div class="form-group">
                            <label>Waktu</label>
                            <input type="time" id="matchTime" required>
                        </div>
                        <div class="form-group">
                            <label>Babak</label>
                            <select id="matchRound">
                                <option value="Babak 16">Babak 16 Besar</option>
                                <option value="Perempat Final">Perempat Final</option>
                                <option value="Semi Final">Semi Final</option>
                                <option value="Final">Final</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label>Tempat</label>
                            <input type="text" id="matchVenue" placeholder="Lokasi pertandingan">
                        </div>
                        <div class="form-group" style="justify-content: flex-end;">
                            <button type="submit" class="btn btn-warning">
                                <i class="fas fa-calendar-check"></i> Tambah Jadwal
                            </button>
                        </div>
                    </form>
                </div>
            </div>

            <!-- Tab: Pengaturan -->
            <div id="tab-settings" class="admin-tab-content">
                <div class="admin-section">
                    <h3><i class="fas fa-key"></i> Ubah Password Admin</h3>
                    <form class="admin-form" onsubmit="changePassword(event)">
                        <div class="form-group">
                            <label>Password Lama</label>
                            <input type="password" id="oldPassword" placeholder="Masukkan password lama" required>
                        </div>
                        <div class="form-group">
                            <label>Password Baru</label>
                            <input type="password" id="newPassword" placeholder="Masukkan password baru" required minlength="4">
                        </div>
                        <div class="form-group">
                            <label>Konfirmasi Password</label>
                            <input type="password" id="confirmPassword" placeholder="Ulangi password baru" required>
                        </div>
                        <div class="form-group" style="justify-content: flex-end;">
                            <button type="submit" class="btn btn-primary">
                                <i class="fas fa-save"></i> Ubah Password
                            </button>
                        </div>
                    </form>
                </div>

                <div class="admin-section">
                    <h3><i class="fas fa-download"></i> Export & Backup Data</h3>
                    <p style="color: var(--text-muted); margin-bottom: 15px;">
                        Download semua data turnamen untuk backup.
                    </p>
                    <div style="display: flex; gap: 10px; flex-wrap: wrap;">
                        <button class="btn btn-success" onclick="exportAllData()">
                            <i class="fas fa-file-export"></i> Export Semua Data
                        </button>
                        <button class="btn btn-info" onclick="window.print()">
                            <i class="fas fa-print"></i> Print Bracket
                        </button>
                    </div>
                </div>

                <div class="admin-section">
                    <h3><i class="fas fa-info-circle"></i> Info Password Default</h3>
                    <div style="background: rgba(255,170,0,0.1); padding: 15px; border-radius: 10px; border: 1px solid var(--warning);">
                        <p style="color: var(--warning); margin: 0;">
                            <i class="fas fa-exclamation-triangle"></i> 
                            Password default: <strong>admin123</strong><br>
                            <small style="color: var(--text-muted);">Segera ubah password setelah login pertama kali!</small>
                        </p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <div class="social-links">
                <a href="#" class="social-link"><i class="fab fa-youtube"></i></a>
                <a href="#" class="social-link"><i class="fab fa-twitch"></i></a>
                <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                <a href="#" class="social-link"><i class="fab fa-discord"></i></a>
            </div>
            <p style="color: var(--text-muted); margin-bottom: 10px;">
                ♛ Chess Championship 2024 ♛
            </p>
            <p style="color: var(--text-muted); font-size: 0.9rem;">
                © 2024 All Rights Reserved | Organized by International Chess Federation
            </p>
        </div>
    </footer>

    <!-- Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3><i class="fas fa-lock"></i> Login Admin</h3>
                <button class="modal-close" onclick="closeModal('loginModal')">&times;</button>
            </div>
            <div class="modal-body">
                <div class="login-container">
                    <div class="login-icon">🔐</div>
                    <h3>Masuk ke Panel Admin</h3>
                    <p>Masukkan password untuk mengakses panel admin</p>
                    
                    <div class="login-error" id="loginError">
                        <i class="fas fa-exclamation-circle"></i> Password salah! Silakan coba lagi.
                    </div>
                    
                    <form onsubmit="loginAdmin(event)">
                        <div class="password-input-group">
                            <input type="password" id="adminPassword" placeholder="Masukkan password" required>
                            <button type="button" class="password-toggle" onclick="togglePassword()">
                                <i class="fas fa-eye" id="eyeIcon"></i>
                            </button>
                        </div>
                        <button type="submit" class="btn btn-primary" style="width: 100%;">
                            <i class="fas fa-sign-in-alt"></i> Login
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <!-- Confirm Reset Modal -->
    <div class="modal" id="confirmResetModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3><i class="fas fa-exclamation-triangle" style="color: var(--warning);"></i> Konfirmasi</h3>
                <button class="modal-close" onclick="closeModal('confirmResetModal')">&times;</button>
            </div>
            <div class="modal-body">
                <div class="confirm-text">
                    <div class="confirm-icon">⚠️</div>
                    <h4>Apakah Anda yakin?</h4>
                    <p>Semua data peserta akan dihapus dan tidak dapat dikembalikan!</p>
                </div>
            </div>
            <div class="modal-footer">
                <button class="btn" style="background: rgba(255,255,255,0.1);" onclick="closeModal('confirmResetModal')">
                    Batal
                </button>
                <button class="btn btn-danger" onclick="resetAllPlayers()">
                    <i class="fas fa-trash-alt"></i> Ya, Hapus Semua
                </button>
            </div>
        </div>
    </div>

    <!-- Edit Player Modal -->
    <div class="modal" id="editPlayerModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3><i class="fas fa-user-edit"></i> Edit Peserta</h3>
                <button class="modal-close" onclick="closeModal('editPlayerModal')">&times;</button>
            </div>
            <div class="modal-body">
                <form onsubmit="saveEditPlayer(event)">
                    <input type="hidden" id="editPlayerId">
                    <div class="form-group">
                        <label>Nama Pemain</label>
                        <input type="text" id="editPlayerName" required>
                    </div>
                    <div class="form-group">
                        <label>Rating</label>
                        <input type="number" id="editPlayerRating" required>
                    </div>
                    <div class="form-group">
                        <label>Negara</label>
                        <input type="text" id="editPlayerCountry" required>
                    </div>
                    <div class="form-group">
                        <label>Bendera</label>
                        <input type="text" id="editPlayerFlag" maxlength="4">
                    </div>
                    <div class="form-group">
                        <label>Gelar</label>
                        <select id="editPlayerTitle">
                            <option value="GM">Grandmaster (GM)</option>
                            <option value="IM">International Master (IM)</option>
                            <option value="FM">FIDE Master (FM)</option>
                            <option value="CM">Candidate Master (CM)</option>
                            <option value="">Tanpa Gelar</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Status</label>
                        <select id="editPlayerStatus">
                            <option value="active">Aktif</option>
                            <option value="pending">Menunggu</option>
                            <option value="playing">Bermain</option>
                            <option value="eliminated">Tersingkir</option>
                        </select>
                    </div>
                    <div class="modal-footer" style="padding: 0; margin-top: 20px;">
                        <button type="button" class="btn" style="background: rgba(255,255,255,0.1);" onclick="closeModal('editPlayerModal')">
                            Batal
                        </button>
                        <button type="submit" class="btn btn-success">
                            <i class="fas fa-save"></i> Simpan
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </div>

    <!-- Import Modal -->
    <div class="modal" id="importModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3><i class="fas fa-upload"></i> Import Data Peserta</h3>
                <button class="modal-close" onclick="closeModal('importModal')">&times;</button>
            </div>
            <div class="modal-body">
                <p style="color: var(--text-muted); margin-bottom: 15px;">
                    Paste data JSON peserta di bawah ini:
                </p>
                <div class="form-group">
                    <textarea id="importData" rows="10" placeholder='[{"name":"Nama","rating":2500,"country":"Indonesia","flag":"🇮🇩","title":"GM"}]' style="width: 100%; resize: vertical;"></textarea>
                </div>
            </div>
            <div class="modal-footer">
                <button class="btn" style="background: rgba(255,255,255,0.1);" onclick="closeModal('importModal')">
                    Batal
                </button>
                <button class="btn btn-success" onclick="importPlayers()">
                    <i class="fas fa-upload"></i> Import
                </button>
            </div>
        </div>
    </div>

    <!-- Toast Notification -->
    <div class="toast" id="toast">
        <i class="fas fa-check-circle" id="toastIcon"></i> 
        <span id="toastMessage">Berhasil!</span>
    </div>

    <script>
        // ==================== CONFIGURATION ====================
        const CONFIG = {
            defaultPassword: 'admin123',
            storageKeys: {
                players: 'chess_tournament_players',
                matches: 'chess_tournament_matches',
                password: 'chess_tournament_password',
                isLoggedIn: 'chess_tournament_logged_in'
            }
        };

        // ==================== DATA ====================
        let participants = [];
        let matches = [];
        let isAdminLoggedIn = false;

        // Sample Data
        const samplePlayers = [
            { id: 1, name: "Magnus Carlsen", country: "Norway", flag: "🇳🇴", rating: 2847, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 2, name: "Fabiano Caruana", country: "USA", flag: "🇺🇸", rating: 2820, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 3, name: "Hikaru Nakamura", country: "USA", flag: "🇺🇸", rating: 2802, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 4, name: "Ding Liren", country: "China", flag: "🇨🇳", rating: 2799, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 5, name: "Ian Nepomniachtchi", country: "Russia", flag: "🇷🇺", rating: 2793, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 6, name: "Alireza Firouzja", country: "France", flag: "🇫🇷", rating: 2785, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 7, name: "Wesley So", country: "USA", flag: "🇺🇸", rating: 2776, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 8, name: "Anish Giri", country: "Netherlands", flag: "🇳🇱", rating: 2764, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 9, name: "Levon Aronian", country: "USA", flag: "🇺🇸", rating: 2751, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 10, name: "Praggnanandhaa R", country: "India", flag: "🇮🇳", rating: 2747, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 11, name: "Viswanathan Anand", country: "India", flag: "🇮🇳", rating: 2745, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 12, name: "Maxime Vachier-Lagrave", country: "France", flag: "🇫🇷", rating: 2742, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 13, name: "Shakhriyar Mamedyarov", country: "Azerbaijan", flag: "🇦🇿", rating: 2738, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 14, name: "Dommaraju Gukesh", country: "India", flag: "🇮🇳", rating: 2730, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 15, name: "Peter Svidler", country: "Russia", flag: "🇷🇺", rating: 2715, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" },
            { id: 16, name: "Richard Rapport", country: "Romania", flag: "🇷🇴", rating: 2710, title: "GM", wins: 0, draws: 0, losses: 0, status: "pending" }
        ];

        // ==================== INITIALIZATION ====================
        document.addEventListener('DOMContentLoaded', function() {
            loadData();
            checkLoginStatus();
            renderAll();
            startCountdown();
        });

        function loadData() {
            const savedPlayers = localStorage.getItem(CONFIG.storageKeys.players);
            const savedMatches = localStorage.getItem(CONFIG.storageKeys.matches);
            
            if (savedPlayers) {
                participants = JSON.parse(savedPlayers);
            }
            if (savedMatches) {
                matches = JSON.parse(savedMatches);
            }
        }

        function saveData() {
            localStorage.setItem(CONFIG.storageKeys.players, JSON.stringify(participants));
            localStorage.setItem(CONFIG.storageKeys.matches, JSON.stringify(matches));
        }

        function checkLoginStatus() {
            isAdminLoggedIn = localStorage.getItem(CONFIG.storageKeys.isLoggedIn) === 'true';
            updateAdminButton();
        }

        function getPassword() {
            return localStorage.getItem(CONFIG.storageKeys.password) || CONFIG.defaultPassword;
        }

        // ==================== NAVIGATION ====================
        function showSection(sectionId, btn) {
            if (sectionId === 'admin' && !isAdminLoggedIn) {
                showModal('loginModal');
                return;
            }

            document.querySelectorAll('.section').forEach(section => {
                section.classList.remove('active');
            });
            
            document.getElementById(sectionId).classList.add('active');
            
            document.querySelectorAll('.nav-btn').forEach(b => {
                b.classList.remove('active');
            });
            if (btn) btn.classList.add('active');
            
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function accessAdmin(btn) {
            if (isAdminLoggedIn) {
                showSection('admin', btn);
            } else {
                showModal('loginModal');
            }
        }

        function showAdminTab(tabId, btn) {
            document.querySelectorAll('.admin-tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            document.getElementById('tab-' + tabId).classList.add('active');
            
            document.querySelectorAll('.admin-tab').forEach(b => {
                b.classList.remove('active');
            });
            btn.classList.add('active');
        }

        // ==================== MODAL FUNCTIONS ====================
        function showModal(modalId) {
            document.getElementById(modalId).classList.add('active');
        }

        function closeModal(modalId) {
            document.getElementById(modalId).classList.remove('active');
        }

        // ==================== ADMIN LOGIN ====================
        function loginAdmin(e) {
            e.preventDefault();
            const password = document.getElementById('adminPassword').value;
            const correctPassword = getPassword();
            
            if (password === correctPassword) {
                isAdminLoggedIn = true;
                localStorage.setItem(CONFIG.storageKeys.isLoggedIn, 'true');
                closeModal('loginModal');
                document.getElementById('adminPassword').value = '';
                document.getElementById('loginError').classList.remove('show');
                updateAdminButton();
                showSection('admin', document.querySelector('.admin-btn'));
                showToast('Login berhasil! Selamat datang, Admin.', 'success');
            } else {
                document.getElementById('loginError').classList.add('show');
            }
        }

        function logoutAdmin() {
            isAdminLoggedIn = false;
            localStorage.setItem(CONFIG.storageKeys.isLoggedIn, 'false');
            updateAdminButton();
            showSection('dashboard', document.querySelector('.nav-btn'));
            showToast('Logout berhasil!', 'success');
        }

        function updateAdminButton() {
            const btnText = document.getElementById('adminBtnText');
            const adminBtn = document.querySelector('.admin-btn');
            
            if (isAdminLoggedIn) {
                btnText.textContent = 'Admin ✓';
                adminBtn.innerHTML = '<i class="fas fa-unlock"></i> <span id="adminBtnText">Admin ✓</span>';
            } else {
                btnText.textContent = 'Admin';
                adminBtn.innerHTML = '<i class="fas fa-lock"></i> <span id="adminBtnText">Admin</span>';
            }
        }

        function togglePassword() {
            const input = document.getElementById('adminPassword');
            const icon = document.getElementById('eyeIcon');
            
            if (input.type === 'password') {
                input.type = 'text';
                icon.classList.remove('fa-eye');
                icon.classList.add('fa-eye-slash');
            } else {
                input.type = 'password';
                icon.classList.remove('fa-eye-slash');
                icon.classList.add('fa-eye');
            }
        }

        function changePassword(e) {
            e.preventDefault();
            const oldPass = document.getElementById('oldPassword').value;
            const newPass = document.getElementById('newPassword').value;
            const confirmPass = document.getElementById('confirmPassword').value;
            
            if (oldPass !== getPassword()) {
                showToast('Password lama salah!', 'error');
                return;
            }
            
            if (newPass !== confirmPass) {
                showToast('Password baru tidak cocok!', 'error');
                return;
            }
            
            localStorage.setItem(CONFIG.storageKeys.password, newPass);
            showToast('Password berhasil diubah!', 'success');
            e.target.reset();
        }

        // ==================== PLAYER MANAGEMENT ====================
        function addParticipant(e) {
            e.preventDefault();
            
            const name = document.getElementById('playerName').value.trim();
            const rating = parseInt(document.getElementById('playerRating').value);
            const country = document.getElementById('playerCountry').value.trim();
            const flag = document.getElementById('playerFlag').value.trim() || '🏳️';
            const title = document.getElementById('playerTitle').value;
            
            const newPlayer = {
                id: Date.now(),
                name: name,
                country: country,
                flag: flag,
                rating: rating,
                title: title,
                wins: 0,
                draws: 0,
                losses: 0,
                status: 'pending'
            };
            
            participants.push(newPlayer);
            saveData();
            renderAll();
            
            showToast(`Peserta "${name}" berhasil ditambahkan!`, 'success');
            e.target.reset();
        }

        function editPlayer(id) {
            const player = participants.find(p => p.id === id);
            if (!player) return;
            
            document.getElementById('editPlayerId').value = player.id;
            document.getElementById('editPlayerName').value = player.name;
            document.getElementById('editPlayerRating').value = player.rating;
            document.getElementById('editPlayerCountry').value = player.country;
            document.getElementById('editPlayerFlag').value = player.flag || '';
            document.getElementById('editPlayerTitle').value = player.title || '';
            document.getElementById('editPlayerStatus').value = player.status || 'pending';
            
            showModal('editPlayerModal');
        }

        function saveEditPlayer(e) {
            e.preventDefault();
            
            const id = parseInt(document.getElementById('editPlayerId').value);
            const playerIndex = participants.findIndex(p => p.id === id);
            
            if (playerIndex === -1) return;
            
            participants[playerIndex] = {
                ...participants[playerIndex],
                name: document.getElementById('editPlayerName').value.trim(),
                rating: parseInt(document.getElementById('editPlayerRating').value),
                country: document.getElementById('editPlayerCountry').value.trim(),
                flag: document.getElementById('editPlayerFlag').value.trim() || '🏳️',
                title: document.getElementById('editPlayerTitle').value,
                status: document.getElementById('editPlayerStatus').value
            };
            
            saveData();
            renderAll();
            closeModal('editPlayerModal');
            showToast('Data peserta berhasil diperbarui!', 'success');
        }

        function deletePlayer(id) {
            const player = participants.find(p => p.id === id);
            if (!player) return;
            
            if (confirm(`Hapus peserta "${player.name}"?`)) {
                participants = participants.filter(p => p.id !== id);
                saveData();
                renderAll();
                showToast(`Peserta "${player.name}" berhasil dihapus!`, 'success');
            }
        }

        function confirmResetAll() {
            showModal('confirmResetModal');
        }

        function resetAllPlayers() {
            participants = [];
            matches = [];
            saveData();
            renderAll();
            closeModal('confirmResetModal');
            showToast('Semua data peserta berhasil dihapus!', 'warning');
        }

        function loadSampleData() {
            if (confirm('Load data contoh 16 pemain? Data yang ada akan ditimpa.')) {
                participants = JSON.parse(JSON.stringify(samplePlayers));
                saveData();
                renderAll();
                showToast('Data contoh berhasil dimuat!', 'success');
            }
        }

        function searchPlayers() {
            const query = document.getElementById('searchPlayer').value.toLowerCase();
            const rows = document.querySelectorAll('#playerListAdmin tr');
            
            rows.forEach(row => {
                const name = row.querySelector('td:nth-child(2)')?.textContent.toLowerCase() || '';
                const country = row.querySelector('td:nth-child(4)')?.textContent.toLowerCase() || '';
                
                if (name.includes(query) || country.includes(query)) {
                    row.style.display = '';
                } else {
                    row.style.display = 'none';
                }
            });
        }

        // ==================== IMPORT/EXPORT ====================
        function exportPlayers() {
            const dataStr = JSON.stringify(participants, null, 2);
            const dataBlob = new Blob([dataStr], { type: 'application/json' });
            const url = URL.createObjectURL(dataBlob);
            
            const a = document.createElement('a');
            a.href = url;
            a.download = 'chess_tournament_players.json';
            a.click();
            
            showToast('Data peserta berhasil di-export!', 'success');
        }

        function showImportModal() {
            showModal('importModal');
        }

        function importPlayers() {
            const dataStr = document.getElementById('importData').value.trim();
            
            try {
                const importedData = JSON.parse(dataStr);
                
                if (!Array.isArray(importedData)) {
                    throw new Error('Data harus berupa array');
                }
                
                importedData.forEach((player, index) => {
                    const newPlayer = {
                        id: Date.now() + index,
                        name: player.name || 'Unknown',
                        country: player.country || 'Unknown',
                        flag: player.flag || '🏳️',
                        rating: player.rating || 1500,
                        title: player.title || '',
                        wins: player.wins || 0,
                        draws: player.draws || 0,
                        losses: player.losses || 0,
                        status: player.status || 'pending'
                    };
                    participants.push(newPlayer);
                });
                
                saveData();
                renderAll();
                closeModal('importModal');
                document.getElementById('importData').value = '';
                showToast(`${importedData.length} peserta berhasil di-import!`, 'success');
            } catch (error) {
                showToast('Format data tidak valid! Pastikan format JSON benar.', 'error');
            }
        }

        function exportAllData() {
            const allData = {
                participants: participants,
                matches: matches,
                exportDate: new Date().toISOString()
            };
            
            const dataStr = JSON.stringify(allData, null, 2);
            const dataBlob = new Blob([dataStr], { type: 'application/json' });
            const url = URL.createObjectURL(dataBlob);
            
            const a = document.createElement('a');
            a.href = url;
            a.download = 'chess_tournament_backup.json';
            a.click();
            
            showToast('Semua data berhasil di-export!', 'success');
        }

        // ==================== BRACKET GENERATION ====================
        function generateBracket(type) {
            if (participants.length < 2) {
                showToast('Minimal 2 peserta untuk generate bracket!', 'error');
                return;
            }
            
            let sortedPlayers;
            
            if (type === 'rating') {
                sortedPlayers = [...participants].sort((a, b) => b.rating - a.rating);
            } else {
                sortedPlayers = [...participants].sort(() => Math.random() - 0.5);
            }
            
            // Generate matches for Round of 16 (or fewer)
            matches = [];
            const numPlayers = Math.min(sortedPlayers.length, 16);
            const numMatches = Math.floor(numPlayers / 2);
            
            for (let i = 0; i < numMatches; i++) {
                matches.push({
                    id: i + 1,
                    round: 'Babak 16',
                    player1: sortedPlayers[i],
                    player2: sortedPlayers[numPlayers - 1 - i],
                    score1: null,
                    score2: null,
                    status: 'scheduled',
                    date: '',
                    time: ''
                });
            }
            
            saveData();
            renderAll();
            showToast(`Bracket berhasil di-generate (${type === 'rating' ? 'by rating' : 'acak'})!`, 'success');
        }

        // ==================== RENDER FUNCTIONS ====================
        function renderAll() {
            renderParticipants();
            renderAdminPlayerList();
            renderBracket();
            renderSchedule();
            renderStandings();
            renderTopPerformers();
            updateStats();
            updateMatchSelect();
        }

        function renderParticipants() {
            const grid = document.getElementById('participantsGrid');
            
            if (participants.length === 0) {
                grid.innerHTML = `
                    <div class="empty-state" style="grid-column: 1/-1;">
                        <i class="fas fa-users"></i>
                        <h4>Belum Ada Peserta</h4>
                        <p>Silakan tambahkan peserta melalui panel admin</p>
                    </div>
                `;
                document.getElementById('participantsSubtitle').textContent = 'Belum ada peserta terdaftar';
                return;
            }
            
            document.getElementById('participantsSubtitle').textContent = `${participants.length} peserta terdaftar`;
            
            const sortedParticipants = [...participants].sort((a, b) => {
                const pointsA = a.wins + (a.draws * 0.5);
                const pointsB = b.wins + (b.draws * 0.5);
                if (pointsB !== pointsA) return pointsB - pointsA;
                return b.rating - a.rating;
            });
            
            grid.innerHTML = sortedParticipants.map((player, index) => {
                const rank = index + 1;
                const points = player.wins + (player.draws * 0.5);
                const initials = player.name.split(' ').map(n => n[0]).join('').substring(0, 2);
                
                return `
                    <div class="participant-card ${rank === 1 && points > 0 ? 'champion' : ''}">
                        <div class="participant-rank ${rank <= 3 ? 'rank-' + rank : 'rank-other'}">${rank}</div>
                        <div class="participant-avatar">${initials}</div>
                        <div class="participant-name">${player.title ? player.title + ' ' : ''}${player.name}</div>
                        <div class="participant-country">${player.flag} ${player.country}</div>
                        <div style="color: var(--gold); font-size: 1.1rem;">Rating: ${player.rating}</div>
                        <div class="participant-stats">
                            <div class="stat">
                                <div class="stat-value" style="color: var(--success);">${player.wins}</div>
                                <div class="stat-label">Menang</div>
                            </div>
                            <div class="stat">
                                <div class="stat-value" style="color: var(--warning);">${player.draws}</div>
                                <div class="stat-label">Seri</div>
                            </div>
                            <div class="stat">
                                <div class="stat-value" style="color: var(--accent);">${player.losses}</div>
                                <div class="stat-label">Kalah</div>
                            </div>
                            <div class="stat">
                                <div class="stat-value">${points}</div>
                                <div class="stat-label">Poin</div>
                            </div>
                        </div>
                        <div style="margin-top: 15px;">
                            <span class="status-badge ${getStatusClass(player.status)}">${getStatusText(player.status)}</span>
                        </div>
                    </div>
                `;
            }).join('');
        }

        function renderAdminPlayerList() {
            const tbody = document.getElementById('playerListAdmin');
            document.getElementById('playerCount').textContent = participants.length;
            
            if (participants.length === 0) {
                tbody.innerHTML = `
                    <tr>
                        <td colspan="8" style="text-align: center; padding: 40px; color: var(--text-muted);">
                            <i class="fas fa-inbox" style="font-size: 2rem; margin-bottom: 10px; display: block;"></i>
                            Belum ada peserta. Tambahkan peserta baru atau load data contoh.
                        </td>
                    </tr>
                `;
                return;
            }
            
            tbody.innerHTML = participants.map((player, index) => {
                const titleClass = player.title ? `badge badge-${player.title.toLowerCase()}` : '';
                return `
                    <tr>
                        <td>${index + 1}</td>
                        <td>
                            <strong>${player.name}</strong>
                        </td>
                        <td>
                            ${player.title ? `<span class="${titleClass}">${player.title}</span>` : '-'}
                        </td>
                        <td>${player.flag} ${player.country}</td>
                        <td><strong>${player.rating}</strong></td>
                        <td>
                            <span style="color: var(--success);">${player.wins}</span>/
                            <span style="color: var(--warning);">${player.draws}</span>/
                            <span style="color: var(--accent);">${player.losses}</span>
                        </td>
                        <td>
                            <span class="status-badge ${getStatusClass(player.status)}">${getStatusText(player.status)}</span>
                        </td>
                        <td>
                            <div class="player-actions">
                                <button class="btn btn-info btn-sm" onclick="editPlayer(${player.id})" title="Edit">
                                    <i class="fas fa-edit"></i>
                                </button>
                                <button class="btn btn-danger btn-sm" onclick="deletePlayer(${player.id})" title="Hapus">
                                    <i class="fas fa-trash"></i>
                                </button>
                            </div>
                        </td>
                    </tr>
                `;
            }).join('');
        }

        function renderBracket() {
            const container = document.getElementById('bracketContainer');
            
            if (matches.length === 0) {
                container.innerHTML = `
                    <div class="empty-state" style="min-width: 100%; padding: 60px;">
                        <i class="fas fa-sitemap"></i>
                        <h4>Bracket Belum Dibuat</h4>
                        <p>Generate bracket melalui panel admin</p>
                    </div>
                `;
                return;
            }
            
            // Group matches by round
            const rounds = {};
            matches.forEach(match => {
                if (!rounds[match.round]) {
                    rounds[match.round] = [];
                }
                rounds[match.round].push(match);
            });
            
            container.innerHTML = Object.keys(rounds).map(roundName => {
                return `
                    <div class="round">
                        <div class="round-title">${roundName}</div>
                        ${rounds[roundName].map(match => renderMatch(match)).join('')}
                    </div>
                `;
            }).join('');
        }

        function renderMatch(match) {
            const p1 = match.player1 || { name: 'TBD', rating: '-' };
            const p2 = match.player2 || { name: 'TBD', rating: '-' };
            const p1Initials = p1.name !== 'TBD' ? p1.name.split(' ').map(n => n[0]).join('').substring(0, 2) : '?';
            const p2Initials = p2.name !== 'TBD' ? p2.name.split(' ').map(n => n[0]).join('').substring(0, 2) : '?';
            
            const isLive = match.status === 'live';
            const isCompleted = match.status === 'completed';
            
            let p1Class = '';
            let p2Class = '';
            
            if (isCompleted && match.score1 !== null && match.score2 !== null) {
                if (match.score1 > match.score2) {
                    p1Class = 'winner';
                    p2Class = 'loser';
                } else if (match.score2 > match.score1) {
                    p1Class = 'loser';
                    p2Class = 'winner';
                }
            }
            
            return `
                <div class="match ${isLive ? 'live' : ''}" data-match-id="${match.id}">
                    <div class="match-header">
                        <span>Match #${match.id}</span>
                        <span class="match-time">${isLive ? 'LIVE' : (match.time || 'TBD')}</span>
                    </div>
                    <div class="player ${p1Class}">
                        <div class="player-info">
                            <div class="player-avatar">${p1Initials}</div>
                            <div>
                                <div class="player-name">${p1.name}</div>
                                <div class="player-rating">Rating: ${p1.rating}</div>
                            </div>
                        </div>
                        <div class="player-score">${match.score1 !== null ? match.score1 : '-'}</div>
                    </div>
                    <div class="vs-divider">VS</div>
                    <div class="player ${p2Class}">
                        <div class="player-info">
                            <div class="player-avatar">${p2Initials}</div>
                            <div>
                                <div class="player-name">${p2.name}</div>
                                <div class="player-rating">Rating: ${p2.rating}</div>
                            </div>
                        </div>
                        <div class="player-score">${match.score2 !== null ? match.score2 : '-'}</div>
                    </div>
                </div>
            `;
        }

        function renderSchedule() {
            const tbody = document.getElementById('scheduleTable');
            
            if (matches.length === 0) {
                tbody.innerHTML = `
                    <tr>
                        <td colspan="9" style="text-align: center; padding: 40px; color: var(--text-muted);">
                            <i class="fas fa-calendar-times" style="font-size: 2rem; margin-bottom: 10px; display: block;"></i>
                            Belum ada jadwal pertandingan
                        </td>
                    </tr>
                `;
                return;
            }
            
            tbody.innerHTML = matches.map((match, index) => {
                const p1 = match.player1 || { name: 'TBD' };
                const p2 = match.player2 || { name: 'TBD' };
                const isWinner1 = match.status === 'completed' && match.score1 > match.score2;
                const isWinner2 = match.status === 'completed' && match.score2 > match.score1;
                
                return `
                    <tr data-status="${match.status}">
                        <td>${index + 1}</td>
                        <td>${match.date || 'TBD'}</td>
                        <td>${match.time || 'TBD'}</td>
                        <td>${match.round}</td>
                        <td>${isWinner1 ? '<strong>' : ''}${p1.name}${isWinner1 ? '</strong>' : ''}</td>
                        <td>VS</td>
                        <td>${isWinner2 ? '<strong>' : ''}${p2.name}${isWinner2 ? '</strong>' : ''}</td>
                        <td>${match.score1 !== null ? `${match.score1} - ${match.score2}` : '- - -'}</td>
                        <td><span class="status-badge status-${match.status}">${getMatchStatusText(match.status)}</span></td>
                    </tr>
                `;
            }).join('');
        }

        function renderStandings() {
            const tbody = document.getElementById('standingsTable');
            
            if (participants.length === 0) {
                tbody.innerHTML = `
                    <tr>
                        <td colspan="10" style="text-align: center; padding: 40px; color: var(--text-muted);">
                            Belum ada data klasemen
                        </td>
                    </tr>
                `;
                return;
            }
            
            const sortedPlayers = [...participants].sort((a, b) => {
                const pointsA = a.wins + (a.draws * 0.5);
                const pointsB = b.wins + (b.draws * 0.5);
                if (pointsB !== pointsA) return pointsB - pointsA;
                return b.rating - a.rating;
            });
            
            const medals = ['🥇', '🥈', '🥉'];
            
            tbody.innerHTML = sortedPlayers.map((player, index) => {
                const rank = index + 1;
                const points = player.wins + (player.draws * 0.5);
                const played = player.wins + player.draws + player.losses;
                const initials = player.name.split(' ').map(n => n[0]).join('').substring(0, 2);
                
                return `
                    <tr>
                        <td>${rank <= 3 ? `<span class="medal">${medals[rank-1]}</span>` : ''} ${rank}</td>
                        <td class="player-cell">
                            <div class="player-avatar" style="width:30px;height:30px;font-size:0.8rem;">${initials}</div>
                            ${player.name}
                        </td>
                        <td>${player.flag} ${player.country}</td>
                        <td>${player.rating}</td>
                        <td>${played}</td>
                        <td style="color: var(--success);">${player.wins}</td>
                        <td style="color: var(--warning);">${player.draws}</td>
                        <td style="color: var(--accent);">${player.losses}</td>
                        <td><strong>${points}</strong></td>
                        <td><span class="status-badge ${getStatusClass(player.status)}">${getStatusText(player.status)}</span></td>
                    </tr>
                `;
            }).join('');
        }

        function renderTopPerformers() {
            const container = document.getElementById('topPerformers');
            
            if (participants.length === 0) {
                container.innerHTML = '<p style="color: var(--text-muted);">Belum ada data</p>';
                return;
            }
            
            const sortedPlayers = [...participants]
                .sort((a, b) => {
                    const played_a = a.wins + a.draws + a.losses;
                    const played_b = b.wins + b.draws + b.losses;
                    const winRate_a = played_a > 0 ? (a.wins / played_a) * 100 : 0;
                    const winRate_b = played_b > 0 ? (b.wins / played_b) * 100 : 0;
                    return winRate_b - winRate_a;
                })
                .slice(0, 3);
            
            const medals = ['🥇', '🥈', '🥉'];
            
            container.innerHTML = sortedPlayers.map((player, index) => {
                const played = player.wins + player.draws + player.losses;
                const winRate = played > 0 ? Math.round((player.wins / played) * 100) : 0;
                
                return `
                    <div style="display: flex; align-items: center; gap: 15px; padding: 10px 0; border-bottom: 1px solid rgba(255,255,255,0.1);">
                        <span style="font-size: 1.5rem;">${medals[index]}</span>
                        <div>
                            <div style="font-weight: 600;">${player.name}</div>
                            <div style="font-size: 0.8rem; color: var(--text-muted);">${winRate}% Win Rate</div>
                        </div>
                    </div>
                `;
            }).join('');
        }

        function updateStats() {
            document.getElementById('totalParticipants').textContent = participants.length;
            document.getElementById('totalMatches').textContent = matches.length;
            document.getElementById('completedMatches').textContent = matches.filter(m => m.status === 'completed').length;
        }

        function updateMatchSelect() {
            const select = document.getElementById('matchSelect');
            select.innerHTML = '<option value="">-- Pilih Match --</option>';
            
            matches.forEach(match => {
                const p1 = match.player1 ? match.player1.name : 'TBD';
                const p2 = match.player2 ? match.player2.name : 'TBD';
                select.innerHTML += `<option value="${match.id}">Match #${match.id} - ${p1} vs ${p2}</option>`;
            });
        }

        // ==================== MATCH MANAGEMENT ====================
        function updateMatch(e) {
            e.preventDefault();
            
            const matchId = parseInt(document.getElementById('matchSelect').value);
            const score1 = parseFloat(document.getElementById('score1').value) || 0;
            const score2 = parseFloat(document.getElementById('score2').value) || 0;
            const status = document.getElementById('matchStatus').value;
            
            if (!matchId) {
                showToast('Pilih pertandingan terlebih dahulu!', 'error');
                return;
            }
            
            const matchIndex = matches.findIndex(m => m.id === matchId);
            if (matchIndex === -1) return;
            
            const match = matches[matchIndex];
            
            // Update player stats if match completed
            if (status === 'completed' && match.status !== 'completed') {
                if (match.player1 && match.player2) {
                    const p1Index = participants.findIndex(p => p.id === match.player1.id);
                    const p2Index = participants.findIndex(p => p.id === match.player2.id);
                    
                    if (p1Index !== -1 && p2Index !== -1) {
                        if (score1 > score2) {
                            participants[p1Index].wins++;
                            participants[p2Index].losses++;
                            participants[p2Index].status = 'eliminated';
                        } else if (score2 > score1) {
                            participants[p2Index].wins++;
                            participants[p1Index].losses++;
                            participants[p1Index].status = 'eliminated';
                        } else {
                            participants[p1Index].draws++;
                            participants[p2Index].draws++;
                        }
                    }
                }
            }
            
            matches[matchIndex] = {
                ...match,
                score1: score1,
                score2: score2,
                status: status
            };
            
            saveData();
            renderAll();
            showToast('Hasil pertandingan berhasil diupdate!', 'success');
            e.target.reset();
        }

        function addSchedule(e) {
            e.preventDefault();
            
            const date = document.getElementById('matchDate').value;
            const time = document.getElementById('matchTime').value;
            const round = document.getElementById('matchRound').value;
            
            // Find matches without schedule in this round
            const matchesToUpdate = matches.filter(m => m.round === round && !m.date);
            
            if (matchesToUpdate.length > 0) {
                matchesToUpdate.forEach(match => {
                    const matchIndex = matches.findIndex(m => m.id === match.id);
                    matches[matchIndex].date = date;
                    matches[matchIndex].time = time;
                });
                saveData();
                renderAll();
                showToast(`Jadwal berhasil ditambahkan untuk ${matchesToUpdate.length} pertandingan!`, 'success');
            } else {
                showToast('Tidak ada pertandingan yang perlu dijadwalkan di babak ini.', 'warning');
            }
            
            e.target.reset();
        }

        function filterSchedule(filter, btn) {
            const rows = document.querySelectorAll('#scheduleTable tr');
            const buttons = document.querySelectorAll('.filter-btn');
            
            buttons.forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            
            rows.forEach(row => {
                const status = row.dataset.status;
                if (filter === 'all' || status === filter) {
                    row.style.display = '';
                } else {
                    row.style.display = 'none';
                }
            });
        }

        // ==================== HELPER FUNCTIONS ====================
        function getStatusClass(status) {
            const classes = {
                'active': 'status-completed',
                'eliminated': 'status-live',
                'playing': 'status-live',
                'pending': 'status-scheduled'
            };
            return classes[status] || 'status-scheduled';
        }

        function getStatusText(status) {
            const texts = {
                'active': '✅ Aktif',
                'eliminated': '❌ Tersingkir',
                'playing': '🔴 Bermain',
                'pending': '⏳ Menunggu'
            };
            return texts[status] || 'Pending';
        }

        function getMatchStatusText(status) {
            const texts = {
                'scheduled': 'Dijadwalkan',
                'upcoming': 'Akan Datang',
                'live': '🔴 LIVE',
                'completed': 'Selesai'
            };
            return texts[status] || status;
        }

        // ==================== COUNTDOWN ====================
        function startCountdown() {
            const finalDate = new Date();
            finalDate.setDate(finalDate.getDate() + 10);
            
            setInterval(() => {
                const now = new Date().getTime();
                const distance = finalDate.getTime() - now;
                
                if (distance < 0) {
                    document.getElementById('days').textContent = '00';
                    document.getElementById('hours').textContent = '00';
                    document.getElementById('minutes').textContent = '00';
                    document.getElementById('seconds').textContent = '00';
                    return;
                }
                
                const days = Math.floor(distance / (1000 * 60 * 60 * 24));
                const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((distance % (1000 * 60)) / 1000);
                
                document.getElementById('days').textContent = String(days).padStart(2, '0');
                document.getElementById('hours').textContent = String(hours).padStart(2, '0');
                document.getElementById('minutes').textContent = String(minutes).padStart(2, '0');
                document.getElementById('seconds').textContent = String(seconds).padStart(2, '0');
            }, 1000);
        }

        // ==================== TOAST ====================
        function showToast(message, type = 'success') {
            const toast = document.getElementById('toast');
            const toastMessage = document.getElementById('toastMessage');
            const toastIcon = document.getElementById('toastIcon');
            
            toast.className = 'toast ' + type;
            toastMessage.textContent = message;
            
            if (type === 'success') {
                toastIcon.className = 'fas fa-check-circle';
            } else if (type === 'error') {
                toastIcon.className = 'fas fa-times-circle';
            } else if (type === 'warning') {
                toastIcon.className = 'fas fa-exclamation-triangle';
            }
            
            toast.classList.add('show');
            
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }
    </script>
</body>
</html>
