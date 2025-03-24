<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>بوت التداول الآلي</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>بوت التداول الذكي</h1>
            <div class="balance-card">
                <h3>الرصيد الحالي</h3>
                <p id="currentBalance">0.00 USDT</p>
            </div>
            <div class="price-card">
                <h3>السعر الحالي</h3>
                <p id="currentPrice">0.00 USDT</p>
            </div>
        </div>

        <div class="trading-controls">
            <div class="settings-panel">
                <h2>إعدادات التداول</h2>
                
                <div class="setting-group">
                    <label>زوج التداول:</label>
                    <select id="tradingPair">
                        <option value="BTCUSDT">BTC/USDT</option>
                        <option value="ETHUSDT">ETH/USDT</option>
                        <option value="BNBUSDT">BNB/USDT</option>
                        <option value="ADAUSDT">ADA/USDT</option>
                        <option value="DOGEUSDT">DOGE/USDT</option>
                    </select>
                </div>

                <div class="setting-group">
                    <label>مبلغ الصفقة (USDT):</label>
                    <input type="number" id="tradeAmount" step="0.1" placeholder="أدخل مبلغ الصفقة">
                </div>

                <div class="setting-group">
                    <label>سعر الدخول:</label>
                    <input type="number" id="entryPrice" step="0.00000001" placeholder="سعر الشراء">
                </div>

                <div class="setting-group">
                    <label>سعر الخروج:</label>
                    <input type="number" id="exitPrice" step="0.00000001" placeholder="سعر البيع">
                </div>

                <button id="addTrade" class="btn primary">إضافة صفقة جديدة</button>

                <div id="activeTradesList" class="active-trades">
                    <h3>الصفقات النشطة</h3>
                    <div class="trades-container"></div>
                </div>

                <div class="setting-group">
                    <label>استراتيجية التداول:</label>
                    <select id="tradingStrategy">
                        <option value="smart">ذكي - تحليل السوق</option>
                        <option value="conservative">متحفظ</option>
                        <option value="aggressive">هجومي</option>
                    </select>
                </div>

                <div class="setting-group">
                    <label>نسبة المخاطرة:</label>
                    <input type="range" id="riskLevel" min="1" max="100" value="20">
                    <span id="riskValue">20%</span>
                </div>

                <div class="setting-group">
                    <label>حد الخسارة:</label>
                    <input type="number" id="stopLoss" min="0" step="0.1" value="5">
                </div>

                <div class="setting-group">
                    <label>هدف الربح:</label>
                    <input type="number" id="takeProfit" min="0" step="0.1" value="10">
                </div>
            </div>

            <div class="actions">
                <button id="startBot" class="btn primary">تشغيل البوت</button>
                <button id="stopBot" class="btn danger" disabled>إيقاف البوت</button>
                <button id="withdrawProfits" class="btn success" disabled>سحب الأرباح</button>
            </div>
        </div>

        <div class="stats-panel">
            <div class="stat-card">
                <h3>الأرباح اليومية</h3>
                <p id="dailyProfits">0.00 USDT</p>
            </div>
            <div class="stat-card">
                <h3>عدد الصفقات</h3>
                <p id="totalTrades">0</p>
            </div>
            <div class="stat-card">
                <h3>نسبة النجاح</h3>
                <p id="successRate">0%</p>
            </div>
        </div>

        <div class="trades-history">
            <h2>سجل التداولات</h2>
            <div id="tradesLog"></div>
        </div>
    </div>

    <script type="module" src="config.js"></script>
    <script type="module" src="bot.js"></script>
</body>
</html>
