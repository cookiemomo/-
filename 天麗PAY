<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>天麗輕鬆pay</title>
    <style>
        :root {
            --primary: #4a90e2;
            --secondary: #50e3c2;
            --danger: #ff5a5f;
            --success: #43e97b;
            --dark: #2c3e50;
            --bg: #f4f7f9;
        }

        body {
            font-family: "PingFang TC", "Microsoft JhengHei", sans-serif;
            background-color: var(--bg);
            margin: 0;
            padding: 25px;
            color: var(--dark);
        }

        .container {
            max-width: 1200px;
            margin: auto;
            position: relative;
            padding-bottom: 50px; /* 為了放頁尾 */
        }

        header {
            text-align: center;
            margin-bottom: 40px;
        }

        header h1 {
            font-size: 2.5rem;
            color: var(--primary);
            margin: 0;
            letter-spacing: 2px;
        }

        header p {
            color: #7f8c8d;
            margin-top: 10px;
        }

        /* 儀表板 */
        .dashboard {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .dash-card {
            padding: 25px;
            border-radius: 20px;
            color: white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            position: relative;
            overflow: hidden;
        }

        .dash-label { font-size: 1rem; opacity: 0.9; }
        .dash-value { font-size: 1.8rem; font-weight: bold; margin-top: 10px; }

        .bg-pv { background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%); }
        .bg-orig { background: linear-gradient(135deg, #606c88 0%, #3f4c6b 100%); }
        .bg-final { background: linear-gradient(135deg, #ff5858 0%, #f09819 100%); }
        .bg-save { background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%); }

        /* 卡片佈局 */
        .main-card {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            margin-bottom: 30px;
        }

        .section-title {
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            color: var(--dark);
        }

        .section-title::before {
            content: '';
            width: 5px;
            height: 20px;
            background: var(--primary);
            margin-right: 12px;
            border-radius: 3px;
        }

        /* 門檻按鈕 */
        .tier-selector {
            display: flex;
            gap: 15px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .tier-btn {
            padding: 12px 25px;
            border: 2px solid #e0e6ed;
            background: white;
            border-radius: 12px;
            cursor: pointer;
            font-weight: 600;
            transition: 0.3s;
        }

        .tier-btn.active {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
            box-shadow: 0 5px 15px rgba(74, 144, 226, 0.3);
        }

        /* 表格優化 */
        .table-wrapper {
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 900px;
        }

        th {
            background: #f8fafc;
            padding: 15px;
            text-align: center;
            font-size: 0.85rem;
            color: #64748b;
            border-bottom: 2px solid #edf2f7;
        }

        td {
            padding: 12px;
            text-align: center;
            border-bottom: 1px solid #f1f5f9;
        }

        .prod-id { font-weight: bold; text-align: left; }
        
        input[type="number"] {
            width: 55px;
            padding: 8px;
            border: 1px solid #e2e8f0;
            border-radius: 8px;
            text-align: center;
            font-size: 1rem;
        }

        .badge-deduct {
            background: #fff0f0;
            color: var(--danger);
            padding: 4px 8px;
            border-radius: 6px;
            font-weight: bold;
            font-size: 0.8rem;
        }

        .final-qty {
            background: #fff9db;
            padding: 5px 12px;
            border-radius: 8px;
            font-weight: bold;
            color: #856404;
        }

        .shortage-warn {
            background: #fff5f5;
            color: #c53030;
            padding: 15px;
            border-radius: 12px;
            margin-bottom: 25px;
            text-align: center;
            font-weight: bold;
            border: 1px solid #feb2b2;
        }

        footer {
            text-align: right;
            margin-top: 30px;
            color: #bdc3c7;
            font-size: 0.8rem;
        }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>天麗輕鬆pay</h1>
        <p>專業購貨組合優化系統</p>
    </header>

    <!-- 儀表板結果區 -->
    <div id="result-display" style="display:none;">
        <div id="shortageMsg"></div>
        <div class="dashboard">
            <div class="dash-card bg-pv">
                <div class="dash-label">原始總需求 PV</div>
                <div class="dash-value" id="resPV">0</div>
            </div>
            <div class="dash-card bg-orig">
                <div class="dash-label">原本應付總額</div>
                <div class="dash-value" id="resOrig">0</div>
            </div>
            <div class="dash-card bg-final">
                <div class="dash-label">優化實付金額</div>
                <div class="dash-value" id="resFinal">0</div>
            </div>
            <div class="dash-card bg-save">
                <div class="dash-label">本次共節省</div>
                <div class="dash-value" id="resSave">0</div>
            </div>
        </div>
    </div>

    <!-- 門檻選擇 -->
    <div class="main-card">
        <div class="section-title">步驟 1：選擇目標獎勵門檻</div>
        <div class="tier-selector">
            <button class="tier-btn active" id="btn-0" onclick="setTier(0)">不計門檻</button>
            <button class="tier-btn" id="btn-50000" onclick="setTier(50000)">滿 5 萬 PV (送6A/9/12)</button>
            <button class="tier-btn" id="btn-100000" onclick="setTier(100000)">滿 10 萬 PV (送2萬幣)</button>
            <button class="tier-btn" id="btn-200000" onclick="setTier(200000)">滿 20 萬 PV (送5萬幣)</button>
        </div>

        <div class="section-title">步驟 2：輸入各人需求數量</div>
        <div class="table-wrapper">
            <table>
                <thead>
                    <tr>
                        <th>產品編號</th>
                        <th>單價/PV</th>
                        <th>媽</th>
                        <th>阿嬤</th>
                        <th>阿姨欠</th>
                        <th>備用</th>
                        <th>亦</th>
                        <th>蓉</th>
                        <th>總需求</th>
                    </tr>
                </thead>
                <tbody id="productRows"></tbody>
            </table>
        </div>
    </div>

    <!-- 最終清單 -->
    <div class="main-card" id="final-card" style="display:none;">
        <div class="section-title">步驟 3：查看優化下單建議 (已扣除贈品與抵扣)</div>
        <div class="table-wrapper">
            <table>
                <thead>
                    <tr style="background: #f8fafc;">
                        <th>產品編號</th>
                        <th>原始需求</th>
                        <th>規則變動</th>
                        <th>實際下單量</th>
                        <th>小計金額</th>
                    </tr>
                </thead>
                <tbody id="compareRows"></tbody>
            </table>
        </div>
    </div>

    <footer>
        Made by Man Ting Mao
    </footer>
</div>

<script>
    const products = [
        { id: 'A1', price: 1995, pv: 1700 }, { id: '1', price: 1995, pv: 1700 },
        { id: '2', price: 1995, pv: 1700 }, { id: '3', price: 3990, pv: 3500 },
        { id: '4', price: 4200, pv: 3600 }, { id: '5', price: 4200, pv: 3600 },
        { id: '6A', price: 3990, pv: 3500 }, { id: '8', price: 3990, pv: 3500 },
        { id: '9', price: 2415, pv: 1800 }, { id: '10', price: 3465, pv: 3000 },
        { id: '12', price: 2415, pv: 1800 }
    ];

    const initialData = {
        'A1': [0,0,0,1,0,0], '1': [0,0,0,0,0,1], '2': [0,0,0,1,0,0],
        '3': [4,0,0,1,0,0], '4': [6,1,2,1,0,0], '5': [8,2,3,1,0,0],
        '6A': [6,1,3,1,0,1], '8': [4,1,1,1,2,0], '9': [5,2,5,1,1,0],
        '10': [1,0,0,1,1,0], '12': [7,2,6,1,0,0]
    };

    let targetTier = 0;

    function init() {
        const tbody = document.getElementById('productRows');
        products.forEach(p => {
            let row = `<tr>
                <td class="prod-id">${p.id}</td>
                <td style="font-size:0.75rem; color:#94a3b8;">$${p.price}<br>${p.pv}PV</td>`;
            for(let i=0; i<6; i++) {
                row += `<td><input type="number" class="qty-in" data-pid="${p.id}" value="${initialData[p.id][i]}" oninput="calculate()"></td>`;
            }
            row += `<td id="sum-${p.id}" style="font-weight:bold;">0</td></tr>`;
            tbody.innerHTML += row;
        });
        calculate();
    }

    function setTier(val) {
        targetTier = val;
        document.querySelectorAll('.tier-btn').forEach(btn => btn.classList.remove('active'));
        document.getElementById('btn-' + val).classList.add('active');
        calculate();
    }

    function calculate() {
        let demand = {};
        let rawPV = 0;
        let rawCost = 0;

        products.forEach(p => {
            let q = 0;
            document.querySelectorAll(`.qty-in[data-pid="${p.id}"]`).forEach(el => q += parseInt(el.value) || 0);
            demand[p.id] = q;
            document.getElementById(`sum-${p.id}`).innerText = q;
            rawPV += q * p.pv;
            rawCost += q * p.price;
        });

        // 警告
        const shortage = document.getElementById('shortageMsg');
        if (targetTier > 0 && rawPV < targetTier) {
            shortage.innerHTML = `<div class="shortage-warn">⚠️ 目前點數 (${rawPV.toLocaleString()}) 未達門檻，尚差 ${(targetTier - rawPV).toLocaleString()} PV</div>`;
        } else { shortage.innerHTML = ""; }

        // 優化邏輯
        let finalBuy = {...demand};
        let deducted = {}; 
        products.forEach(p => deducted[p.id] = 0);

        if (rawPV >= 50000 && targetTier >= 50000) {
            ['6A', '9', '12'].forEach(id => { if(finalBuy[id] > 0) { finalBuy[id]--; deducted[id]++; } });
        }

        let coins = (rawPV >= 200000 && targetTier >= 200000) ? 50000 : (rawPV >= 100000 && targetTier >= 100000 ? 20000 : 0);
        if (coins > 0) {
            let sorted = [...products].sort((a,b) => b.price - a.price);
            let tempC = coins;
            sorted.forEach(p => {
                while(tempC >= p.pv && finalBuy[p.id] > 0) {
                    finalBuy[p.id]--; deducted[p.id]++; tempC -= p.pv;
                }
            });
        }

        // 渲染統計
        document.getElementById('resPV').innerText = rawPV.toLocaleString();
        document.getElementById('resOrig').innerText = "$" + rawCost.toLocaleString();
        let finalCost = 0;
        products.forEach(p => finalCost += finalBuy[p.id] * p.price);
        document.getElementById('resFinal').innerText = "$" + finalCost.toLocaleString();
        document.getElementById('resSave').innerText = "$" + (rawCost - finalCost).toLocaleString();
        document.getElementById('result-display').style.display = 'block';

        // 渲染結果對照表
        const comp = document.getElementById('compareRows');
        comp.innerHTML = "";
        products.forEach(p => {
            let sub = finalBuy[p.id] * p.price;
            let dedText = deducted[p.id] > 0 ? `<span class="badge-deduct">贈/抵 -${deducted[p.id]}</span>` : "-";
            comp.innerHTML += `<tr>
                <td class="prod-id">${p.id}</td>
                <td>${demand[p.id]}</td>
                <td>${dedText}</td>
                <td><span class="${deducted[p.id] > 0 ? 'final-qty' : ''}">${finalBuy[p.id]}</span></td>
                <td>$${sub.toLocaleString()}</td>
            </tr>`;
        });
        document.getElementById('final-card').style.display = 'block';
    }

    init();
</script>

</body>
</html>
