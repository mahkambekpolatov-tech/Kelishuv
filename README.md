<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>USK Pharm & ICP IT Company - Interaktiv Moliyaviy Doska</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen p-6">

    <div class="max-w-7xl mx-auto">
        <!-- Sarlavha va Logotiplar -->
        <header class="bg-gradient-to-r from-blue-700 to-indigo-800 text-white p-6 rounded-2xl shadow-lg mb-8 flex flex-col md:flex-row items-center justify-between gap-6">
            <div class="flex items-center gap-4">
                <!-- USK Pharm Logotipi -->
                <div class="w-16 h-16 rounded-xl overflow-hidden shadow-md border-2 border-white/20 bg-slate-900 flex-shrink-0">
                    <img src="12086.jpg" alt="USK Pharm Logo" class="w-full h-full object-cover">
                </div>
                <div>
                    <h1 class="text-2xl font-bold">USK Pharm & ICP IT Company</h1>
                    <p class="text-blue-200 text-sm mt-0.5">Interaktiv Moliyaviy va Strategik Hisob-Kitob Doskasi (Tiyinigacha aniqlikda)</p>
                </div>
            </div>
            
            <!-- ICP IT Company Logotipi -->
            <div class="flex items-center gap-3 bg-white/10 p-3 rounded-xl backdrop-blur-sm border border-white/15">
                <div class="w-12 h-12 rounded-lg overflow-hidden shadow-md flex-shrink-0">
                    <img src="12087.jpg" alt="ICP IT Company Logo" class="w-full h-full object-cover">
                </div>
                <div class="text-left text-xs">
                    <span class="font-semibold block text-white">Texnik Hamkor</span>
                    <span class="text-blue-200">Innovate • Create • Perform</span>
                </div>
            </div>
        </header>

        <!-- Asosiy sozlamalar bloki (Boshqaruv paneli) -->
        <div class="grid grid-cols-1 md:grid-cols-4 gap-6 mb-8">
            <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-200">
                <label class="block text-sm font-medium text-slate-600 mb-2">Kunlik Hamshiralik Chaqiruvlari</label>
                <input type="number" id="nurseCalls" value="25" class="w-full p-2 border border-slate-300 rounded-lg font-semibold text-blue-600 focus:ring-2 focus:ring-blue-500 outline-none" oninput="calculateFinance()">
                <span class="text-xs text-slate-400 mt-1 block">O‘rtacha narx: 60,000 so‘m</span>
            </div>

            <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-200">
                <label class="block text-sm font-medium text-slate-600 mb-2">Kunlik Dori Buyurtmalari</label>
                <input type="number" id="drugOrders" value="40" class="w-full p-2 border border-slate-300 rounded-lg font-semibold text-blue-600 focus:ring-2 focus:ring-blue-500 outline-none" oninput="calculateFinance()">
                <span class="text-xs text-slate-400 mt-1 block">O‘rtacha chek: 100,000 so‘m</span>
            </div>

            <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-200">
                <label class="block text-sm font-medium text-slate-600 mb-2">Valyuta Kursi (1 USD / UZS)</label>
                <input type="number" id="usdRate" value="12800" class="w-full p-2 border border-slate-300 rounded-lg font-semibold text-blue-600 focus:ring-2 focus:ring-blue-500 outline-none" oninput="calculateFinance()">
                <span class="text-xs text-slate-400 mt-1 block">1 million dollarga yetish uchun so'm ekvivalenti</span>
            </div>

            <div class="bg-white p-5 rounded-xl shadow-sm border border-slate-200 flex flex-col justify-between">
                <div>
                    <span class="text-sm font-medium text-slate-600">ICP IT Company Ulushi</span>
                    <h3 class="text-2xl font-bold text-emerald-600 mt-1">40%</h3>
                </div>
                <span class="text-xs text-slate-400">Sof foydadan kafolatlangan dividend</span>
            </div>
        </div>

        <!-- Natijalar paneli -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
            <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                <h4 class="text-sm font-medium text-slate-500 uppercase tracking-wider">Oylik Yalpi Tushum</h4>
                <div id="monthlyRevenue" class="text-2xl font-bold text-slate-900 mt-2">0 UZS</div>
                <div id="monthlyRevenueUsd" class="text-sm text-slate-500 mt-1">0 USD</div>
            </div>

            <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                <h4 class="text-sm font-medium text-slate-500 uppercase tracking-wider">Yillik Sof Foyda (Taxminiy 50%)</h4>
                <div id="annualNetProfit" class="text-2xl font-bold text-indigo-600 mt-2">0 UZS</div>
                <div id="annualNetProfitUsd" class="text-sm text-slate-500 mt-1">0 USD</div>
            </div>

            <div class="bg-indigo-900 text-white p-6 rounded-xl shadow-md">
                <h4 class="text-sm font-medium text-indigo-200 uppercase tracking-wider">ICP IT Company 40% Dividendi</h4>
                <div id="itAnnualDividend" class="text-2xl font-bold text-emerald-400 mt-2">0 UZS</div>
                <div id="itAnnualDividendUsd" class="text-sm text-indigo-200 mt-1">0 USD</div>
            </div>
        </div>

        <!-- Batafsil hisob-kitob jadvali -->
        <div class="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden mb-8">
            <div class="p-6 border-b border-slate-100">
                <h3 class="text-lg font-bold text-slate-800">Daromad Oqimlari Taqsimoti (Oylik Tiyinigacha)</h3>
            </div>
            <div class="overflow-x-auto">
                <table class="w-full text-left border-collapse">
                    <thead>
                        <tr class="bg-slate-100 text-slate-600 text-sm">
                            <th class="p-4">Daromad Manbasi</th>
                            <th class="p-4">Hisob-kitob Mantiqi</th>
                            <th class="p-4 text-right">Oylik Tushum (UZS)</th>
                        </tr>
                    </thead>
                    <tbody class="divide-y divide-slate-100 text-sm">
                        <tr>
                            <td class="p-4 font-medium">1. Hamshiralik Xizmatlari (Kompaniya ulushi)</td>
                            <td class="p-4 text-slate-500">Chaqiruv × 60,000 so‘m × 30 kun × 60%</td>
                            <td id="rowNurse" class="p-4 text-right font-semibold">0.00 UZS</td>
                        </tr>
                        <tr>
                            <td class="p-4 font-medium">2. Dori Dostavkasi Komissiyasi</td>
                            <td class="p-4 text-slate-500">Buyurtma × 100,000 so‘m × 30 kun × 10%</td>
                            <td id="rowDelivery" class="p-4 text-right font-semibold">0.00 UZS</td>
                        </tr>
                        <tr>
                            <td class="p-4 font-medium">3. Dorixona Hamkorlik Ulushi</td>
                            <td class="p-4 text-slate-500">Dori aylanmasidan 2% kafolatlangan ulush</td>
                            <td id="rowPharmacy" class="p-4 text-right font-semibold">0.00 UZS</td>
                        </tr>
                        <tr>
                            <td class="p-4 font-medium">4. B2B Reklama va Integratsiya</td>
                            <td class="p-4 text-slate-500">Tibbiy brendlar va klinikalar reklamasi</td>
                            <td id="rowAds" class="p-4 text-right font-semibold">4,500,000.00 UZS</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>

        <!-- 5 yillik maqsad progress bari -->
        <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
            <h3 class="text-lg font-bold text-slate-800 mb-2">5 Yillik $1,000,000 (1 Million Dollar) Marrasi Prognozi</h3>
            <p class="text-sm text-slate-500 mb-4">Ushbu oylik daromad sur'atida 5 yillik umumiy sof foyda va ICP IT jamoasining 40% ($400,000) ulushiga erishish ko‘rsatkichi.</p>
            <div class="w-full bg-slate-200 rounded-full h-4 mb-2 overflow-hidden">
                <div id="progressBar" class="bg-emerald-500 h-4 rounded-full transition-all duration-500" style="width: 0%;"></div>
            </div>
            <div class="flex justify-between text-sm text-slate-600 font-medium">
                <span id="progressText">Joriy yillik prognoz: 0 USD</span>
                <span>Maqsad: $1,000,000</span>
            </div>
        </div>
    </div>

    <script>
        function formatMoney(amount) {
            return new Intl.NumberFormat('uz-UZ', { minimumFractionDigits: 2, maximumFractionDigits: 2 }).format(amount);
        }

        function calculateFinance() {
            let nurseCalls = parseFloat(document.getElementById('nurseCalls').value) || 0;
            let drugOrders = parseFloat(document.getElementById('drugOrders').value) || 0;
            let usdRate = parseFloat(document.getElementById('usdRate').value) || 12800;

            let monthlyNurseGross = nurseCalls * 60000 * 30;
            let monthlyNurseCompany = monthlyNurseGross * 0.60;

            let monthlyDrugTurnover = drugOrders * 100000 * 30;
            let monthlyDeliveryCommission = monthlyDrugTurnover * 0.10;

            let monthlyPharmacyShare = monthlyDrugTurnover * 0.02;
            let monthlyAds = 4500000;

            let totalMonthlyRevenue = monthlyNurseCompany + monthlyDeliveryCommission + monthlyPharmacyShare + monthlyAds;
            let totalAnnualRevenue = totalMonthlyRevenue * 12;
            let annualNetProfit = totalAnnualRevenue * 0.50;
            let itAnnualDividend = annualNetProfit * 0.40;

            document.getElementById('rowNurse').innerText = formatMoney(monthlyNurseCompany) + " UZS";
            document.getElementById('rowDelivery').innerText = formatMoney(monthlyDeliveryCommission) + " UZS";
            document.getElementById('rowPharmacy').innerText = formatMoney(monthlyPharmacyShare) + " UZS";
            document.getElementById('rowAds').innerText = formatMoney(monthlyAds) + " UZS";

            document.getElementById('monthlyRevenue').innerText = formatMoney(totalMonthlyRevenue) + " UZS";
            document.getElementById('monthlyRevenueUsd').innerText = "$" + formatMoney(totalMonthlyRevenue / usdRate);

            document.getElementById('annualNetProfit').innerText = formatMoney(annualNetProfit) + " UZS";
            document.getElementById('annualNetProfitUsd').innerText = "$" + formatMoney(annualNetProfit / usdRate);

            document.getElementById('itAnnualDividend').innerText = formatMoney(itAnnualDividend) + " UZS";
            document.getElementById('itAnnualDividendUsd').innerText = "$" + formatMoney(itAnnualDividend / usdRate);

            let targetAnnualNetProfitUsd = 200000;
            let currentAnnualNetProfitUsd = annualNetProfit / usdRate;
            let progressPercent = Math.min((currentAnnualNetProfitUsd / targetAnnualNetProfitUsd) * 100, 100);

            document.getElementById('progressBar').style.width = progressPercent.toFixed(1) + "%";
            document.getElementById('progressText').innerText = "Joriy yillik sof foyda prognozi: $" + formatMoney(currentAnnualNetProfitUsd) + " (" + progressPercent.toFixed(1) + "%)";
        }

        calculateFinance();
    </script>
</body>
</html>
