<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>คณิตศาสตร์การเงิน ป.5</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
      font-family: 'Kanit', sans-serif;
    }
    
    .coin-bounce {
      animation: bounce 2s ease-in-out infinite;
    }
    
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    
    .sparkle {
      animation: sparkle 1.5s ease-in-out infinite;
    }
    
    @keyframes sparkle {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.7; transform: scale(1.1); }
    }
    
    .slide-in {
      animation: slideIn 0.5s ease-out;
    }
    
    @keyframes slideIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    .correct-flash {
      animation: correctFlash 0.5s ease-out;
    }
    
    @keyframes correctFlash {
      0% { background-color: #10b981; }
      100% { background-color: transparent; }
    }
    
    .wrong-shake {
      animation: shake 0.5s ease-out;
    }
    
    @keyframes shake {
      0%, 100% { transform: translateX(0); }
      25% { transform: translateX(-10px); }
      75% { transform: translateX(10px); }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app" class="h-full overflow-auto" style="background: linear-gradient(135deg, #fef3c7 0%, #fde68a 50%, #fbbf24 100%);"><!-- Header -->
   <header class="text-center py-6 px-4" style="background: linear-gradient(180deg, #f59e0b 0%, #d97706 100%);">
    <div class="flex justify-center items-center gap-3 mb-2"><span class="text-4xl coin-bounce">🪙</span>
     <h1 id="main-title" class="text-3xl md:text-4xl font-bold text-white drop-shadow-lg">คณิตศาสตร์การเงิน ป.5</h1><span class="text-4xl coin-bounce" style="animation-delay: 0.5s;">💰</span>
    </div>
    <p id="welcome-text" class="text-amber-100 text-lg">เรียนรู้เรื่องเงินอย่างสนุก!</p>
   </header><!-- Score Bar -->
   <div class="bg-white/80 backdrop-blur mx-4 mt-4 rounded-2xl p-4 shadow-lg flex justify-between items-center">
    <div class="flex items-center gap-2"><span class="text-2xl">⭐</span> <span class="font-semibold text-amber-800">คะแนน: <span id="score" class="text-2xl text-amber-600">0</span></span>
    </div>
    <div class="flex items-center gap-2"><span class="text-2xl">🏆</span> <span class="font-semibold text-amber-800">ระดับ: <span id="level" class="text-amber-600">1</span></span>
    </div>
    <div class="flex items-center gap-2"><span class="text-2xl">❤️</span> <span id="lives" class="font-semibold text-red-500">3</span>
    </div>
   </div><!-- Navigation Tabs -->
   <nav class="flex justify-center gap-2 px-4 mt-4 flex-wrap"><button onclick="showSection('learn')" class="nav-btn px-4 py-2 rounded-full font-medium transition-all bg-amber-500 text-white shadow-lg hover:bg-amber-600" data-section="learn"> 📚 เรียนรู้ </button> <button onclick="showSection('practice')" class="nav-btn px-4 py-2 rounded-full font-medium transition-all bg-white/70 text-amber-800 hover:bg-amber-500 hover:text-white" data-section="practice"> ✏️ แบบฝึกหัด </button> <button onclick="showSection('game')" class="nav-btn px-4 py-2 rounded-full font-medium transition-all bg-white/70 text-amber-800 hover:bg-amber-500 hover:text-white" data-section="game"> 🎮 เกมจำลอง </button>
   </nav><!-- Main Content Area -->
   <main class="px-4 py-6 pb-32"><!-- Learn Section -->
    <section id="learn-section" class="slide-in">
     <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-3"><!-- Thai Currency Card -->
      <div class="bg-white rounded-2xl p-5 shadow-lg hover:shadow-xl transition-shadow">
       <h3 class="text-xl font-bold text-amber-700 mb-3 flex items-center gap-2"><span class="text-2xl">🇹🇭</span> เงินไทย</h3>
       <div class="space-y-2 text-gray-700">
        <div class="flex items-center gap-3 p-2 bg-amber-50 rounded-lg"><span class="text-3xl">🪙</span>
         <div>
          <p class="font-medium">เหรียญ</p>
          <p class="text-sm text-gray-500">25 สตางค์, 50 สตางค์, 1, 2, 5, 10 บาท</p>
         </div>
        </div>
        <div class="flex items-center gap-3 p-2 bg-green-50 rounded-lg"><span class="text-3xl">💵</span>
         <div>
          <p class="font-medium">ธนบัตร</p>
          <p class="text-sm text-gray-500">20, 50, 100, 500, 1000 บาท</p>
         </div>
        </div>
        <div class="mt-3 p-3 bg-blue-50 rounded-lg">
         <p class="text-sm font-medium text-blue-700">💡 ความรู้เพิ่มเติม</p>
         <p class="text-sm text-blue-600">100 สตางค์ = 1 บาท</p>
        </div>
       </div>
      </div><!-- Price Calculation Card -->
      <div class="bg-white rounded-2xl p-5 shadow-lg hover:shadow-xl transition-shadow">
       <h3 class="text-xl font-bold text-amber-700 mb-3 flex items-center gap-2"><span class="text-2xl">🧮</span> การคำนวณราคา</h3>
       <div class="space-y-3 text-gray-700">
        <div class="p-3 bg-purple-50 rounded-lg">
         <p class="font-medium text-purple-700">ราคารวม = ราคา × จำนวน</p>
         <p class="text-sm mt-1">ตัวอย่าง: ดินสอราคา 15 บาท ซื้อ 3 แท่ง</p>
         <p class="text-sm font-medium text-purple-600">= 15 × 3 = 45 บาท</p>
        </div>
        <div class="p-3 bg-pink-50 rounded-lg">
         <p class="font-medium text-pink-700">เงินทอน = เงินที่จ่าย - ราคาส���นค้า</p>
         <p class="text-sm mt-1">ตัวอย่าง: จ่าย 100 บาท ซื้อของ 65 บาท</p>
         <p class="text-sm font-medium text-pink-600">= 100 - 65 = 35 บาท</p>
        </div>
       </div>
      </div><!-- Discount Card -->
      <div class="bg-white rounded-2xl p-5 shadow-lg hover:shadow-xl transition-shadow">
       <h3 class="text-xl font-bold text-amber-700 mb-3 flex items-center gap-2"><span class="text-2xl">🏷️</span> ส่วนลด</h3>
       <div class="space-y-3 text-gray-700">
        <div class="p-3 bg-red-50 rounded-lg">
         <p class="font-medium text-red-700">ส่วนลด = ราคาเดิม × เปอร์เซ็นต์ลด ÷ 100</p>
         <p class="text-sm mt-1">ตัวอย่าง: กระเป๋า 200 บาท ลด 20%</p>
         <p class="text-sm font-medium text-red-600">= 200 × 20 ÷ 100 = 40 บาท</p>
         <p class="text-sm font-medium text-green-600">ราคาจ่ายจริง = 200 - 40 = 160 บาท</p>
        </div>
        <div class="p-3 bg-orange-50 rounded-lg">
         <p class="text-sm font-medium text-orange-700">🎯 ส่วนลดที่พบบ่อย</p>
         <p class="text-sm">10%, 20%, 25%, 30%, 50%</p>
        </div>
       </div>
      </div>
     </div>
    </section><!-- Practice Section -->
    <section id="practice-section" class="hidden slide-in">
     <div class="bg-white rounded-2xl p-6 shadow-lg max-w-2xl mx-auto">
      <div class="flex justify-between items-center mb-4">
       <h3 class="text-xl font-bold text-amber-700">แบบฝึกหัด</h3><span id="question-num" class="text-sm text-gray-500">ข้อ 1/10</span>
      </div><!-- Question Display -->
      <div id="question-area" class="mb-6">
       <div class="bg-gradient-to-r from-amber-100 to-yellow-100 rounded-xl p-5">
        <p id="question-type" class="text-sm text-amber-600 mb-2">📦 โจทย์ประเภท: การทอนเงิน</p>
        <p id="question-text" class="text-lg text-gray-800 font-medium">น้องซื้อขนมราคา 35 บาท จ่ายด้วยแบงก์ 100 บาท จะได้เงินทอนเท่าไหร่?</p>
       </div>
      </div><!-- Answer Options -->
      <div id="options-area" class="grid grid-cols-2 gap-3 mb-4"><button onclick="checkAnswer(0)" class="option-btn p-4 bg-blue-50 hover:bg-blue-100 rounded-xl text-blue-800 font-medium transition-all border-2 border-transparent hover:border-blue-300"> 55 บาท </button> <button onclick="checkAnswer(1)" class="option-btn p-4 bg-green-50 hover:bg-green-100 rounded-xl text-green-800 font-medium transition-all border-2 border-transparent hover:border-green-300"> 65 บาท </button> <button onclick="checkAnswer(2)" class="option-btn p-4 bg-purple-50 hover:bg-purple-100 rounded-xl text-purple-800 font-medium transition-all border-2 border-transparent hover:border-purple-300"> 75 บาท </button> <button onclick="checkAnswer(3)" class="option-btn p-4 bg-pink-50 hover:bg-pink-100 rounded-xl text-pink-800 font-medium transition-all border-2 border-transparent hover:border-pink-300"> 45 บาท </button>
      </div><!-- Feedback Area -->
      <div id="feedback-area" class="hidden p-4 rounded-xl mb-4">
       <p id="feedback-text" class="font-medium"></p>
       <p id="feedback-explain" class="text-sm mt-1"></p>
      </div><!-- Next Button --> <button id="next-btn" onclick="nextQuestion()" class="hidden w-full py-3 bg-amber-500 hover:bg-amber-600 text-white rounded-xl font-medium transition-all"> ข้อถัดไป ➜ </button>
     </div>
    </section><!-- Game Section - Shop Simulator -->
    <section id="game-section" class="hidden slide-in">
     <div class="bg-white rounded-2xl p-6 shadow-lg max-w-3xl mx-auto">
      <h3 class="text-xl font-bold text-amber-700 mb-4 flex items-center gap-2"><span class="text-2xl">🏪</span> ร้านค้าจำลอง</h3><!-- Shop Items -->
      <div class="grid grid-cols-2 md:grid-cols-4 gap-3 mb-6">
       <div class="shop-item bg-gradient-to-br from-red-50 to-red-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="addToCart('🍎', 'แอปเปิ้ล', 25)"><span class="text-4xl">🍎</span>
        <p class="font-medium text-gray-800 mt-1">แอปเปิ้ล</p>
        <p class="text-red-600 font-bold">25 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-yellow-50 to-yellow-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="addToCart('🍌', 'กล้วย', 15)"><span class="text-4xl">🍌</span>
        <p class="font-medium text-gray-800 mt-1">กล้วย</p>
        <p class="text-yellow-600 font-bold">15 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-blue-50 to-blue-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="addToCart('📓', 'สมุด', 35)"><span class="text-4xl">📓</span>
        <p class="font-medium text-gray-800 mt-1">สมุด</p>
        <p class="text-blue-600 font-bold">35 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-green-50 to-green-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="addToCart('✏️', 'ดินสอ', 10)"><span class="text-4xl">✏️</span>
        <p class="font-medium text-gray-800 mt-1">ดินสอ</p>
        <p class="text-green-600 font-bold">10 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-purple-50 to-purple-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="addToCart('🧴', 'ยางลบ', 8)"><span class="text-4xl">🧴</span>
        <p class="font-medium text-gray-800 mt-1">ยางลบ</p>
        <p class="text-purple-600 font-bold">8 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-pink-50 to-pink-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="addToCart('🥤', 'น้ำผลไม้', 20)"><span class="text-4xl">🥤</span>
        <p class="font-medium text-gray-800 mt-1">น้ำผลไม้</p>
        <p class="text-pink-600 font-bold">20 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-orange-50 to-orange-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="addToCart('🍪', 'คุกกี้', 12)"><span class="text-4xl">🍪</span>
        <p class="font-medium text-gray-800 mt-1">คุกกี้</p>
        <p class="text-orange-600 font-bold">12 บาท</p>
       </div>
       <div class="shop-item bg-gradient-to-br from-cyan-50 to-cyan-100 p-4 rounded-xl text-center cursor-pointer hover:scale-105 transition-transform" onclick="addToCart('📏', 'ไม้บรรทัด', 18)"><span class="text-4xl">📏</span>
        <p class="font-medium text-gray-800 mt-1">ไม้บรรทัด</p>
        <p class="text-cyan-600 font-bold">18 บาท</p>
       </div>
      </div><!-- Cart -->
      <div class="bg-amber-50 rounded-xl p-4 mb-4">
       <h4 class="font-bold text-amber-800 mb-2 flex items-center gap-2"><span>🛒</span> ตะกร้าสินค้า</h4>
       <div id="cart-items" class="min-h-[60px] text-gray-600">
        <p class="text-sm text-gray-400">ยังไม่มีสินค้าในตะกร้า</p>
       </div>
       <div class="flex justify-between items-center mt-3 pt-3 border-t border-amber-200"><span class="font-bold text-amber-800">รวมทั้งหมด:</span> <span id="cart-total" class="text-2xl font-bold text-amber-600">0 บาท</span>
       </div>
      </div><!-- Payment Section -->
      <div class="bg-green-50 rounded-xl p-4">
       <h4 class="font-bold text-green-800 mb-3">💳 ชำระเงิน</h4>
       <div class="flex flex-wrap gap-2 mb-4"><button onclick="addPayment(20)" class="px-4 py-2 bg-green-100 hover:bg-green-200 rounded-lg text-green-800 font-medium transition-all">💵 20</button> <button onclick="addPayment(50)" class="px-4 py-2 bg-green-100 hover:bg-green-200 rounded-lg text-green-800 font-medium transition-all">💵 50</button> <button onclick="addPayment(100)" class="px-4 py-2 bg-green-100 hover:bg-green-200 rounded-lg text-green-800 font-medium transition-all">💵 100</button> <button onclick="addPayment(500)" class="px-4 py-2 bg-green-100 hover:bg-green-200 rounded-lg text-green-800 font-medium transition-all">💵 500</button> <button onclick="addPayment(10)" class="px-4 py-2 bg-yellow-100 hover:bg-yellow-200 rounded-lg text-yellow-800 font-medium transition-all">🪙 10</button> <button onclick="addPayment(5)" class="px-4 py-2 bg-yellow-100 hover:bg-yellow-200 rounded-lg text-yellow-800 font-medium transition-all">🪙 5</button>
       </div>
       <div class="flex justify-between items-center mb-3"><span class="text-green-800">เงินที่จ่าย:</span> <span id="payment-amount" class="text-xl font-bold text-green-600">0 บาท</span>
       </div>
       <div class="flex gap-2"><button onclick="processPayment()" class="flex-1 py-3 bg-green-500 hover:bg-green-600 text-white rounded-xl font-medium transition-all">✅ จ่ายเงิน</button> <button onclick="resetShop()" class="px-4 py-3 bg-gray-200 hover:bg-gray-300 text-gray-700 rounded-xl font-medium transition-all">🔄</button>
       </div>
      </div><!-- Change Result -->
      <div id="change-result" class="hidden mt-4 p-4 bg-blue-50 rounded-xl text-center">
       <p id="change-text" class="text-lg font-medium text-blue-800"></p>
      </div>
     </div>
    </section>
   </main><!-- Creator Footer -->
   <footer class="fixed bottom-0 left-0 right-0 py-4 px-4" style="background: linear-gradient(180deg, rgba(245, 158, 11, 0.95) 0%, rgba(217, 119, 6, 0.95) 100%); backdrop-filter: blur(10px);">
    <div class="max-w-4xl mx-auto text-center">
     <div class="flex items-center justify-center gap-2 mb-1"><span class="text-2xl">👨‍💻</span>
      <p class="text-white font-medium text-sm md:text-base">ผู้สร้าง: <span class="font-bold">เด็กชายภัทรชนน พงษ์ญวนชั้น</span></p>
     </div>
     <p class="text-amber-100 text-xs md:text-sm">ชั้นประถมศึกษาปีที่ 5/5 สาย MEP 🎓</p>
    </div>
   </footer>
  </div>
  <script>
    // Configuration
    const defaultConfig = {
      app_title: 'คณิตศาสตร์การเงิน ป.5',
      welcome_message: 'เรียนรู้เรื่องเงินอย่างสนุก!',
      primary_color: '#f59e0b',
      secondary_color: '#fef3c7',
      text_color: '#78350f',
      button_color: '#d97706',
      accent_color: '#10b981'
    };

    let config = { ...defaultConfig };

    // Game State
    let score = 0;
    let level = 1;
    let lives = 3;
    let currentQuestion = 0;
    let correctAnswer = 1;
    let cart = [];
    let cartTotal = 0;
    let paymentAmount = 0;

    // Questions Bank
    const questions = [
      {
        type: 'การทอนเงิน',
        text: 'น้องซื้อขนมราคา 35 บาท จ่ายด้วยแบงก์ 100 บาท จะได้เงินทอนเท่าไหร่?',
        options: ['55 บาท', '65 บาท', '75 บาท', '45 บาท'],
        correct: 1,
        explain: '100 - 35 = 65 บาท'
      },
      {
        type: 'การคำนวณราคา',
        text: 'ปากการาคาด้ามละ 12 บาท ถ้าซื้อ 5 ด้าม จะต้องจ่ายเงินเท่าไหร่?',
        options: ['50 บาท', '55 บาท', '60 บาท', '65 บา��'],
        correct: 2,
        explain: '12 × 5 = 60 บาท'
      },
      {
        type: 'ส่วนลด',
        text: 'กระเป๋าราคา 200 บาท ลดราคา 10% ต้องจ่ายเท่าไหร่?',
        options: ['190 บาท', '180 บาท', '170 บาท', '160 บาท'],
        correct: 1,
        explain: 'ส่วนลด = 200 × 10 ÷ 100 = 20 บาท, จ่าย = 200 - 20 = 180 บาท'
      },
      {
        type: 'การทอนเงิน',
        text: 'แม่ให้เงิน 500 บาท ไปซื้อของ 387 บาท จะได้เงินทอนเท่าไหร่?',
        options: ['103 บาท', '113 บาท', '123 บาท', '133 บาท'],
        correct: 1,
        explain: '500 - 387 = 113 บาท'
      },
      {
        type: 'การคำนวณราคา',
        text: 'นมก���่องละ 8 บาท ถ้ามี��งิน 50 บาท ซื้อได้มากที่สุดกี่กล่อง?',
        options: ['5 กล่อง', '6 กล่อง', '7 กล่อง', '8 กล่อง'],
        correct: 1,
        explain: '50 ÷ 8 = 6 เศษ 2 ซื้อได้มากสุด 6 กล่อง'
      },
      {
        type: 'ส่วนลด',
        text: 'รองเท้าราคา 500 บาท ลด 20% ประหยัดเงินได้เท่าไหร่?',
        options: ['80 บาท', '90 บาท', '100 บาท', '110 บาท'],
        correct: 2,
        explain: 'ส่วนลด = 500 × 20 ÷ 100 = 100 บาท'
      },
      {
        type: 'การทอนเงิน',
        text: 'ซื้อไอศกรีม 3 แท่ง แท่งละ 15 บาท จ่าย 100 บาท ได้เงินทอนเท่าไหร่?',
        options: ['45 บาท', '50 บาท', '55 บาท', '60 บาท'],
        correct: 2,
        explain: 'ราคารวม = 15 × 3 = 45 บาท, เงินทอน = 100 - 45 = 55 บาท'
      },
      {
        type: 'การคำนวณราคา',
        text: 'สมุดราคา 25 บาท ดินสอราคา 8 บาท ซื้อสมุด 2 เล่ม และดินสอ 3 แท่ง รวมเท่าไหร่?',
        options: ['64 บาท', '74 บาท', '84 บาท', '94 บาท'],
        correct: 1,
        explain: 'สมุด = 25 × 2 = 50, ดินสอ = 8 × 3 = 24, รวม = 50 + 24 = 74 บาท'
      },
      {
        type: 'ส่วนลด',
        text: 'เสื้อราคา 350 บาท ลด 30% ต้องจ่ายเท่าไหร่?',
        options: ['235 บาท', '245 บาท', '255 บาท', '265 บาท'],
        correct: 1,
        explain: 'ส่วนลด = 350 × 30 ÷ 100 = 105 บาท, จ่าย = 350 - 105 = 245 บาท'
      },
      {
        type: 'การทอนเงิน',
        text: 'พ่อให้เงิน 1000 บาท ซื้อของขวัญ 756 บาท ได้เงินทอนเท่าไหร่?',
        options: ['234 บาท', '244 บาท', '254 บาท', '264 บาท'],
        correct: 1,
        explain: '1000 - 756 = 244 บาท'
      }
    ];

    // Initialize SDK
    async function initApp() {
      if (window.elementSdk) {
        await window.elementSdk.init({
          defaultConfig,
          onConfigChange: async (newConfig) => {
            config = { ...defaultConfig, ...newConfig };
            updateUI();
          },
          mapToCapabilities: (cfg) => ({
            recolorables: [
              {
                get: () => cfg.primary_color || defaultConfig.primary_color,
                set: (value) => { cfg.primary_color = value; window.elementSdk.setConfig({ primary_color: value }); }
              },
              {
                get: () => cfg.secondary_color || defaultConfig.secondary_color,
                set: (value) => { cfg.secondary_color = value; window.elementSdk.setConfig({ secondary_color: value }); }
              },
              {
                get: () => cfg.text_color || defaultConfig.text_color,
                set: (value) => { cfg.text_color = value; window.elementSdk.setConfig({ text_color: value }); }
              },
              {
                get: () => cfg.button_color || defaultConfig.button_color,
                set: (value) => { cfg.button_color = value; window.elementSdk.setConfig({ button_color: value }); }
              },
              {
                get: () => cfg.accent_color || defaultConfig.accent_color,
                set: (value) => { cfg.accent_color = value; window.elementSdk.setConfig({ accent_color: value }); }
              }
            ],
            borderables: [],
            fontEditable: undefined,
            fontSizeable: undefined
          }),
          mapToEditPanelValues: (cfg) => new Map([
            ['app_title', cfg.app_title || defaultConfig.app_title],
            ['welcome_message', cfg.welcome_message || defaultConfig.welcome_message]
          ])
        });
        config = { ...defaultConfig, ...window.elementSdk.config };
      }
      updateUI();
      loadQuestion();
    }

    function updateUI() {
      const title = document.getElementById('main-title');
      const welcome = document.getElementById('welcome-text');
      
      if (title) title.textContent = config.app_title || defaultConfig.app_title;
      if (welcome) welcome.textContent = config.welcome_message || defaultConfig.welcome_message;
      
      // Update colors
      const header = document.querySelector('header');
      if (header) {
        header.style.background = `linear-gradient(180deg, ${config.primary_color || defaultConfig.primary_color} 0%, ${config.button_color || defaultConfig.button_color} 100%)`;
      }
      
      const app = document.getElementById('app');
      if (app) {
        app.style.background = `linear-gradient(135deg, ${config.secondary_color || defaultConfig.secondary_color} 0%, #fde68a 50%, ${config.primary_color || defaultConfig.primary_color} 100%)`;
      }
    }

    // Navigation
    function showSection(section) {
      document.querySelectorAll('[id$="-section"]').forEach(el => el.classList.add('hidden'));
      document.getElementById(`${section}-section`).classList.remove('hidden');
      
      document.querySelectorAll('.nav-btn').forEach(btn => {
        btn.classList.remove('bg-amber-500', 'text-white', 'shadow-lg');
        btn.classList.add('bg-white/70', 'text-amber-800');
      });
      
      document.querySelector(`[data-section="${section}"]`).classList.remove('bg-white/70', 'text-amber-800');
      document.querySelector(`[data-section="${section}"]`).classList.add('bg-amber-500', 'text-white', 'shadow-lg');
    }

    // Practice Functions
    function loadQuestion() {
      if (currentQuestion >= questions.length) {
        currentQuestion = 0;
        shuffleQuestions();
      }
      
      const q = questions[currentQuestion];
      document.getElementById('question-num').textContent = `ข้อ ${currentQuestion + 1}/10`;
      document.getElementById('question-type').textContent = `📦 โจทย์ประเภท: ${q.type}`;
      document.getElementById('question-text').textContent = q.text;
      
      const optionBtns = document.querySelectorAll('.option-btn');
      optionBtns.forEach((btn, i) => {
        btn.textContent = q.options[i];
        btn.disabled = false;
        btn.classList.remove('opacity-50', 'ring-4', 'ring-green-500', 'ring-red-500');
      });
      
      correctAnswer = q.correct;
      
      document.getElementById('feedback-area').classList.add('hidden');
      document.getElementById('next-btn').classList.add('hidden');
    }

    function shuffleQuestions() {
      for (let i = questions.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [questions[i], questions[j]] = [questions[j], questions[i]];
      }
    }

    function checkAnswer(selected) {
      const optionBtns = document.querySelectorAll('.option-btn');
      optionBtns.forEach(btn => btn.disabled = true);
      
      const feedbackArea = document.getElementById('feedback-area');
      const feedbackText = document.getElementById('feedback-text');
      const feedbackExplain = document.getElementById('feedback-explain');
      
      if (selected === correctAnswer) {
        score += 10;
        document.getElementById('score').textContent = score;
        
        optionBtns[selected].classList.add('ring-4', 'ring-green-500');
        feedbackArea.classList.remove('hidden', 'bg-red-50');
        feedbackArea.classList.add('bg-green-50');
        feedbackText.textContent = '🎉 ถูกต้อง! เก่งมาก!';
        feedbackText.className = 'font-medium text-green-700';
        
        if (score % 50 === 0) {
          level++;
          document.getElementById('level').textContent = level;
        }
      } else {
        lives--;
        document.getElementById('lives').textContent = lives;
        
        optionBtns[selected].classList.add('ring-4', 'ring-red-500', 'wrong-shake');
        optionBtns[correctAnswer].classList.add('ring-4', 'ring-green-500');
        
        feedbackArea.classList.remove('hidden', 'bg-green-50');
        feedbackArea.classList.add('bg-red-50');
        feedbackText.textContent = '😅 ไม่ถูกต้อง ลองดูคำอธิบายนะ';
        feedbackText.className = 'font-medium text-red-700';
        
        if (lives <= 0) {
          feedbackText.textContent = '💔 หมดชีวิตแล้ว! เริ่มใหม่กันเถอะ';
          setTimeout(() => {
            lives = 3;
            score = 0;
            level = 1;
            document.getElementById('lives').textContent = lives;
            document.getElementById('score').textContent = score;
            document.getElementById('level').textContent = level;
          }, 2000);
        }
      }
      
      feedbackExplain.textContent = `💡 วิธีคิด: ${questions[currentQuestion].explain}`;
      feedbackExplain.className = 'text-sm mt-1 text-gray-600';
      
      document.getElementById('next-btn').classList.remove('hidden');
    }

    function nextQuestion() {
      currentQuestion++;
      loadQuestion();
    }

    // Shop Game Functions
    function addToCart(emoji, name, price) {
      cart.push({ emoji, name, price });
      cartTotal += price;
      updateCartDisplay();
    }

    function updateCartDisplay() {
      const cartItems = document.getElementById('cart-items');
      if (cart.length === 0) {
        cartItems.innerHTML = '<p class="text-sm text-gray-400">ยังไม่มีสินค้าในตะกร้า</p>';
      } else {
        const grouped = cart.reduce((acc, item) => {
          const key = item.name;
          if (!acc[key]) acc[key] = { ...item, count: 0 };
          acc[key].count++;
          return acc;
        }, {});
        
        cartItems.innerHTML = Object.values(grouped).map(item => 
          `<div class="flex justify-between items-center py-1">
            <span>${item.emoji} ${item.name} × ${item.count}</span>
            <span class="font-medium">${item.price * item.count} บาท</span>
          </div>`
        ).join('');
      }
      document.getElementById('cart-total').textContent = `${cartTotal} บาท`;
    }

    function addPayment(amount) {
      paymentAmount += amount;
      document.getElementById('payment-amount').textContent = `${paymentAmount} บาท`;
    }

    function processPayment() {
      const changeResult = document.getElementById('change-result');
      const changeText = document.getElementById('change-text');
      
      if (cart.length === 0) {
        changeResult.classList.remove('hidden', 'bg-blue-50');
        changeResult.classList.add('bg-yellow-50');
        changeText.textContent = '⚠️ กรุณาเลือกสินค้าก่อนนะ';
        changeText.className = 'text-lg font-medium text-yellow-800';
        return;
      }
      
      if (paymentAmount < cartTotal) {
        changeResult.classList.remove('hidden', 'bg-blue-50');
        changeResult.classList.add('bg-red-50');
        changeText.textContent = `❌ เงินไม่พอ! ต้องจ่ายอีก ${cartTotal - paymentAmount} บาท`;
        changeText.className = 'text-lg font-medium text-red-800';
        return;
      }
      
      const change = paymentAmount - cartTotal;
      changeResult.classList.remove('hidden', 'bg-yellow-50', 'bg-red-50');
      changeResult.classList.add('bg-green-50');
      
      if (change === 0) {
        changeText.textContent = '✅ จ่ายเงินพอดี! ไม่ต้องทอน 🎉';
      } else {
        changeText.textContent = `✅ จ่ายสำเร็จ! เงินทอน ${change} บาท 💰`;
      }
      changeText.className = 'text-lg font-medium text-green-800';
      
      score += 5;
      document.getElementById('score').textContent = score;
    }

    function resetShop() {
      cart = [];
      cartTotal = 0;
      paymentAmount = 0;
      updateCartDisplay();
      document.getElementById('payment-amount').textContent = '0 บาท';
      document.getElementById('change-result').classList.add('hidden');
    }

    // Initialize
    initApp();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c031eda70604f58',t:'MTc2ODc5MjAzMi4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
