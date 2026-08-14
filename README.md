<!DOCTYPE html>
<html lang="zh-CN" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>越夜越美丽 · 河内吃喝玩乐探索指南 | Hanoi Travel & Food Guide</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+SC:wght@400;600;700&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        hanoi: {
                            gold: '#D97706',       // 法式殖民建筑黄
                            ochre: '#B45309',      // 暖赭石
                            teal: '#0F5132',       // 印度支那复古绿
                            darkteal: '#064E3B',   // 深森林绿
                            cream: '#FDFBF7',      // 鸡蛋咖啡奶霜色
                            paper: '#F5ECE1',      // 怀旧纸张色
                            terracotta: '#C2410C', // 瓦片红
                            coffee: '#451A03'      // 滴漏咖啡棕
                        }
                    },
                    fontFamily: {
                        serif: ['"Noto Serif SC"', 'serif'],
                        sans: ['"Plus Jakarta Sans"', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #FDFBF7;
            color: #262626;
            font-family: 'Plus Jakarta Sans', sans-serif;
        }
        .font-serif-title {
            font-family: 'Noto Serif SC', serif;
        }
        .bg-pattern {
            background-color: #FDFBF7;
            background-image: radial-gradient(#d97706 0.5px, transparent 0.5px), radial-gradient(#0f5132 0.5px, #FDFBF7 0.5px);
            background-size: 20px 20px;
            background-position: 0 0, 10px 10px;
            background-opacity: 0.05;
        }
        .glass-card {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(8px);
            border: 1px solid rgba(217, 119, 6, 0.15);
        }
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
    </style>
</head>
<body class="bg-hanoi-cream text-stone-800 relative selection:bg-hanoi-gold selection:text-white">

    <!-- Navigation Bar -->
    <header class="sticky top-0 z-40 bg-hanoi-cream/90 backdrop-blur-md border-b border-hanoi-gold/20 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Logo -->
                <div class="flex items-center space-x-3">
                    <div class="w-10 h-10 rounded-full bg-hanoi-teal flex items-center justify-center text-hanoi-gold text-xl font-bold shadow-md">
                        <i class="fa-solid me-0.5 fa-mug-hot"></i>
                    </div>
                    <div>
                        <span class="text-xl font-bold font-serif-title text-hanoi-darkteal tracking-wide block leading-tight">Hanoi Explorer</span>
                        <span class="text-xs text-hanoi-gold tracking-widest uppercase font-semibold">河内吃喝玩乐攻略</span>
                    </div>
                </div>

                <!-- Desktop Nav -->
                <nav class="hidden md:flex items-center space-x-8 font-medium text-sm text-stone-700">
                    <a href="#discover" class="hover:text-hanoi-gold transition-colors"><i class="fa-solid fa-compass mr-1 text-hanoi-gold"></i>探索精选</a>
                    <a href="#itinerary" class="hover:text-hanoi-gold transition-colors"><i class="fa-solid fa-route mr-1 text-hanoi-gold"></i>推荐行程</a>
                    <a href="#toolkit" class="hover:text-hanoi-gold transition-colors"><i class="fa-solid fa-toolbox mr-1 text-hanoi-gold"></i>旅行实用箱</a>
                    <a href="#tips" class="hover:text-hanoi-gold transition-colors"><i class="fa-solid fa-lightbulb mr-1 text-hanoi-gold"></i>避坑指南</a>
                </nav>

                <!-- Actions -->
                <div class="flex items-center space-x-4">
                    <button id="openFavoritesBtn" class="relative bg-hanoi-paper hover:bg-hanoi-gold/20 text-hanoi-darkteal p-2.5 rounded-full transition-all flex items-center justify-center border border-hanoi-gold/30">
                        <i class="fa-solid fa-heart text-hanoi-terracotta text-lg"></i>
                        <span id="favCountBadge" class="absolute -top-1 -right-1 bg-hanoi-terracotta text-white text-xs font-bold w-5 h-5 rounded-full flex items-center justify-center shadow-sm">0</span>
                    </button>
                    <a href="#spinModal" onclick="openRandomizer()" class="hidden sm:inline-flex items-center space-x-2 bg-hanoi-teal hover:bg-hanoi-darkteal text-white px-4 py-2 rounded-full text-sm font-semibold shadow-md hover:shadow-lg transition-all">
                        <i class="fa-solid fa-dice text-hanoi-gold"></i>
                        <span>今天吃什么？</span>
                    </a>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Banner -->
    <section class="relative min-h-[580px] flex items-center justify-center overflow-hidden bg-hanoi-coffee text-white">
        <!-- Background Image with Blend -->
        <div class="absolute inset-0 z-0">
            <img src="https://images.unsplash.com/photo-1555921015-5532091f6026?auto=format&fit=crop&w=1920&q=80" 
                 alt="Hanoi Old Quarter Street" 
                 class="w-full h-full object-cover object-center opacity-40 mix-blend-overlay"
                 onerror="this.src='https://placehold.co/1920x1080/451A03/FFF?text=Hanoi+Street'">
            <div class="absolute inset-0 bg-gradient-to-t from-hanoi-coffee via-hanoi-coffee/50 to-transparent"></div>
        </div>

        <div class="relative z-10 max-w-5xl mx-auto px-4 text-center py-16">
            <div class="inline-flex items-center space-x-2 bg-hanoi-gold/20 border border-hanoi-gold/40 backdrop-blur-md px-4 py-1.5 rounded-full mb-6">
                <span class="w-2 h-2 rounded-full bg-hanoi-gold animate-pulse"></span>
                <span class="text-xs sm:text-sm font-medium tracking-wide text-hanoi-cream">千年古都 · 浪漫法式风情 · 街头美食天堂</span>
            </div>
            
            <h1 class="text-4xl sm:text-6xl lg:text-7xl font-bold font-serif-title leading-tight mb-6 tracking-wide">
                越夜越美丽 <span class="text-hanoi-gold italic font-normal">·</span> 漫步河内
            </h1>
            
            <p class="text-stone-300 text-base sm:text-xl max-w-2xl mx-auto mb-10 font-light leading-relaxed">
                在三十六行街的迷宫中品尝一碗浓郁牛肉粉，于还剑湖畔抿一口鸡蛋咖啡，感受古老越南与法式浪漫交织的市井烟火。
            </p>

            <!-- Search and Quick Filter Bar -->
            <div class="max-w-2xl mx-auto relative glass-card p-2 rounded-2xl shadow-2xl border border-white/20">
                <div class="flex items-center bg-white rounded-xl px-4 py-3 shadow-inner">
                    <i class="fa-solid fa-magnifying-glass text-hanoi-gold text-lg mr-3"></i>
                    <input type="text" id="searchInput" placeholder="搜索景点、美食 (例：鸡蛋咖啡, 还剑湖, Banh Mi)..." 
                           class="w-full bg-transparent text-stone-800 placeholder-stone-400 focus:outline-none text-sm sm:text-base">
                    <button onclick="applySearch()" class="bg-hanoi-gold hover:bg-hanoi-ochre text-white px-5 py-2.5 rounded-lg text-sm font-semibold transition-all shadow shrink-0">
                        搜索
                    </button>
                </div>
            </div>

            <!-- Quick Stats -->
            <div class="grid grid-cols-2 sm:grid-cols-4 gap-4 max-w-3xl mx-auto mt-12 text-center border-t border-white/10 pt-8">
                <div>
                    <div class="text-2xl sm:text-3xl font-bold font-serif-title text-hanoi-gold">36 +</div>
                    <div class="text-xs text-stone-300 mt-1">古街行当巷弄</div>
                </div>
                <div>
                    <div class="text-2xl sm:text-3xl font-bold font-serif-title text-hanoi-gold">50,000₫</div>
                    <div class="text-xs text-stone-300 mt-1">地道河粉均价 (~15元)</div>
                </div>
                <div>
                    <div class="text-2xl sm:text-3xl font-bold font-serif-title text-hanoi-gold">100 Years</div>
                    <div class="text-xs text-stone-300 mt-1">鸡蛋咖啡历史</div>
                </div>
                <div>
                    <div class="text-2xl sm:text-3xl font-bold font-serif-title text-hanoi-gold">Top 1</div>
                    <div class="text-xs text-stone-300 mt-1">东南亚慢节奏之都</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Main Content Section -->
    <main id="discover" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        
        <!-- Category Filter Header -->
        <div class="flex flex-col md:flex-row md:items-end justify-between mb-10 gap-6">
            <div>
                <div class="flex items-center space-x-2 text-hanoi-gold font-semibold text-sm tracking-wider uppercase mb-2">
                    <i class="fa-solid fa-fire"></i>
                    <span>Curated Selection</span>
                </div>
                <h2 class="text-3xl sm:text-4xl font-bold font-serif-title text-hanoi-darkteal">河内精选吃喝玩乐地图</h2>
            </div>

            <!-- Filter Pills -->
            <div class="flex items-center space-x-2 overflow-x-auto no-scrollbar pb-2 md:pb-0">
                <button onclick="filterCategory('all')" class="filter-btn active bg-hanoi-teal text-white px-4 py-2 rounded-full text-sm font-medium whitespace-nowrap transition-all shadow-sm">
                    ✨ 全部精选
                </button>
                <button onclick="filterCategory('food')" class="filter-btn bg-white hover:bg-hanoi-paper text-stone-600 px-4 py-2 rounded-full text-sm font-medium whitespace-nowrap transition-all border border-stone-200">
                    🍜 地道美食
                </button>
                <button onclick="filterCategory('coffee')" class="filter-btn bg-white hover:bg-hanoi-paper text-stone-600 px-4 py-2 rounded-full text-sm font-medium whitespace-nowrap transition-all border border-stone-200">
                    ☕ 咖啡与甜品
                </button>
                <button onclick="filterCategory('sight')" class="filter-btn bg-white hover:bg-hanoi-paper text-stone-600 px-4 py-2 rounded-full text-sm font-medium whitespace-nowrap transition-all border border-stone-200">
                    🏛️ 经典打卡
                </button>
                <button onclick="filterCategory('night')" class="filter-btn bg-white hover:bg-hanoi-paper text-stone-600 px-4 py-2 rounded-full text-sm font-medium whitespace-nowrap transition-all border border-stone-200">
                    🍺 嗨晚夜生活
                </button>
            </div>
        </div>

        <!-- Cards Grid -->
        <div id="spotsGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Cards will be populated by JavaScript dynamically -->
        </div>
    </main>

    <!-- 3-Day Itinerary Section -->
    <section id="itinerary" class="bg-hanoi-paper/60 py-20 border-y border-hanoi-gold/20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-14">
                <span class="text-hanoi-gold font-semibold text-sm tracking-widest uppercase">Plan Your Trip</span>
                <h2 class="text-3xl sm:text-4xl font-bold font-serif-title text-hanoi-darkteal mt-2">河内 3 天 2 夜经典行程路线</h2>
                <p class="text-stone-600 mt-3 text-base">精心打磨的最佳游览顺序，高效穿梭古街巷弄与法式建筑之间，不走回头路。</p>
            </div>

            <!-- Itinerary Tabs -->
            <div class="flex justify-center mb-10">
                <div class="inline-flex p-1.5 bg-white rounded-2xl border border-hanoi-gold/20 shadow-sm space-x-2">
                    <button onclick="switchDay(1)" id="dayBtn1" class="day-tab bg-hanoi-teal text-white px-6 py-2.5 rounded-xl font-semibold text-sm transition-all shadow-sm">
                        DAY 1 · 古街人文与美食探索
                    </button>
                    <button onclick="switchDay(2)" id="dayBtn2" class="day-tab text-stone-600 hover:text-hanoi-teal px-6 py-2.5 rounded-xl font-semibold text-sm transition-all">
                        DAY 2 · 法式优雅与西湖漫步
                    </button>
                    <button onclick="switchDay(3)" id="dayBtn3" class="day-tab text-stone-600 hover:text-hanoi-teal px-6 py-2.5 rounded-xl font-semibold text-sm transition-all">
                        DAY 3 · 隐秘巷弄与夜生活
                    </button>
                </div>
            </div>

            <!-- Itinerary Content Container -->
            <div id="itineraryContent" class="max-w-4xl mx-auto bg-white rounded-3xl p-6 sm:p-10 shadow-xl border border-hanoi-gold/10">
                <!-- Injected via JS -->
            </div>
        </div>
    </section>

    <!-- Interactive Travel Toolkit -->
    <section id="toolkit" class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-3xl mx-auto mb-14">
            <span class="text-hanoi-gold font-semibold text-sm tracking-widest uppercase">Interactive Tools</span>
            <h2 class="text-3xl sm:text-4xl font-bold font-serif-title text-hanoi-darkteal mt-2">河内随身助手工具箱</h2>
            <p class="text-stone-600 mt-3">方便即时换算消费、快速用越南语交流与解决选择困难症。</p>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
            
            <!-- Tool 1: Currency Converter -->
            <div class="bg-white p-8 rounded-3xl border border-hanoi-gold/20 shadow-lg flex flex-col justify-between">
                <div>
                    <div class="flex items-center space-x-3 mb-6">
                        <div class="w-12 h-12 rounded-2xl bg-hanoi-gold/10 text-hanoi-gold flex items-center justify-center text-xl">
                            <i class="fa-solid fa-calculator"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-lg text-stone-800">越南盾即时换算</h3>
                            <p class="text-xs text-stone-500">实时计算，去掉3个零再除以3.5</p>
                        </div>
                    </div>

                    <div class="space-y-4">
                        <div>
                            <label class="block text-xs font-semibold text-stone-500 mb-1">越南盾金额 (VND ₫)</label>
                            <div class="relative">
                                <input type="number" id="vndInput" value="100000" step="10000" oninput="convertCurrency()" 
                                       class="w-full bg-stone-50 border border-stone-200 rounded-xl px-4 py-3 text-lg font-bold text-hanoi-darkteal focus:outline-none focus:border-hanoi-gold">
                                <span class="absolute right-4 top-3.5 text-xs text-stone-400 font-semibold">₫</span>
                            </div>
                        </div>

                        <div class="flex justify-center my-2 text-hanoi-gold">
                            <i class="fa-solid fa-arrow-down-up-across-line text-lg"></i>
                        </div>

                        <div class="grid grid-cols-2 gap-3">
                            <div class="bg-hanoi-paper/50 p-3 rounded-xl border border-hanoi-gold/10">
                                <span class="text-xs text-stone-500 block">约合人民币 (CNY)</span>
                                <span id="cnyOutput" class="text-xl font-bold text-hanoi-terracotta">¥ 28.5</span>
                            </div>
                            <div class="bg-hanoi-paper/50 p-3 rounded-xl border border-hanoi-gold/10">
                                <span class="text-xs text-stone-500 block">约合美元 (USD)</span>
                                <span id="usdOutput" class="text-xl font-bold text-hanoi-darkteal">$ 3.9</span>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="mt-6 pt-4 border-t border-stone-100 text-xs text-stone-400 flex items-center justify-between">
                    <span>💡 快捷口诀：去掉末尾3个0，再除以3.5</span>
                </div>
            </div>

            <!-- Tool 2: Survival Phrases with Audio simulation -->
            <div class="bg-white p-8 rounded-3xl border border-hanoi-gold/20 shadow-lg flex flex-col justify-between">
                <div>
                    <div class="flex items-center space-x-3 mb-6">
                        <div class="w-12 h-12 rounded-2xl bg-hanoi-teal/10 text-hanoi-teal flex items-center justify-center text-xl">
                            <i class="fa-solid fa-comments"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-lg text-stone-800">地道越南语生存卡</h3>
                            <p class="text-xs text-stone-500">点击播放发音 / 出示给司机会话</p>
                        </div>
                    </div>

                    <div class="space-y-3 max-h-[220px] overflow-y-auto pr-1 no-scrollbar" id="phrasesList">
                        <!-- Phrases populated via JS -->
                    </div>
                </div>

                <div class="mt-6 pt-4 border-t border-stone-100 text-xs text-stone-400">
                    <span>📢 支持浏览器TTS朗读发音，也可以直接给店家看字</span>
                </div>
            </div>

            <!-- Tool 3: Random Food Spinner Widget -->
            <div class="bg-gradient-to-br from-hanoi-teal to-hanoi-darkteal text-white p-8 rounded-3xl shadow-lg flex flex-col justify-between relative overflow-hidden">
                <div class="relative z-10">
                    <div class="flex items-center space-x-3 mb-6">
                        <div class="w-12 h-12 rounded-2xl bg-white/10 text-hanoi-gold flex items-center justify-center text-xl backdrop-blur-md">
                            <i class="fa-solid fa-arrows-spin"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-lg text-white">今天河内吃什么？</h3>
                            <p class="text-xs text-stone-300">选择困难症救星随机抽取</p>
                        </div>
                    </div>

                    <div class="bg-white/10 backdrop-blur-md rounded-2xl p-6 text-center border border-white/10 my-4 min-h-[140px] flex flex-col items-center justify-center">
                        <div id="randomResultTitle" class="text-2xl font-bold font-serif-title text-hanoi-gold mb-1">点击按钮开始</div>
                        <div id="randomResultSub" class="text-xs text-stone-200">抽取你的下一餐美食路线</div>
                    </div>
                </div>

                <button onclick="spinRandomFood()" class="relative z-10 w-full bg-hanoi-gold hover:bg-hanoi-ochre text-white font-bold py-3.5 rounded-xl transition-all shadow-md active:scale-95 flex items-center justify-center space-x-2">
                    <i class="fa-solid fa-dice"></i>
                    <span>随机决定吃啥</span>
                </button>
            </div>
        </div>
    </section>

    <!-- Hanoi Travel Tips & Traps Avoidance -->
    <section id="tips" class="bg-hanoi-coffee text-white py-20 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <span class="text-hanoi-gold font-semibold text-sm tracking-widest uppercase">Local Insider Guide</span>
                <h2 class="text-3xl sm:text-4xl font-bold font-serif-title text-white mt-2">河内旅行避坑与地道指南</h2>
                <p class="text-stone-300 mt-3">第一次来河内必看的交通、过马路、打车与防坑秘籍。</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                
                <div class="bg-white/5 border border-white/10 p-6 rounded-2xl hover:bg-white/10 transition-all">
                    <div class="w-10 h-10 rounded-xl bg-hanoi-gold/20 text-hanoi-gold flex items-center justify-center text-lg mb-4">
                        <i class="fa-solid fa-motorcycle"></i>
                    </div>
                    <h3 class="font-bold text-lg text-hanoi-gold mb-2">过马路的艺术</h3>
                    <p class="text-stone-300 text-sm leading-relaxed">
                        河内摩托车如潮水！切记：<strong>匀速向前走，千万不要突然停下或后退</strong>。骑士会根据你的移动轨迹自行避开你。
                    </p>
                </div>

                <div class="bg-white/5 border border-white/10 p-6 rounded-2xl hover:bg-white/10 transition-all">
                    <div class="w-10 h-10 rounded-xl bg-hanoi-gold/20 text-hanoi-gold flex items-center justify-center text-lg mb-4">
                        <i class="fa-solid fa-taxi"></i>
                    </div>
                    <h3 class="font-bold text-lg text-hanoi-gold mb-2">交通打车软件</h3>
                    <p class="text-stone-300 text-sm leading-relaxed">
                        强烈推荐下载 <strong>Grab</strong> 或 <strong>Xanh SM</strong>（绿色电动出租车）。明码标价，避免黑出租绕路或乱要价。
                    </p>
                </div>

                <div class="bg-white/5 border border-white/10 p-6 rounded-2xl hover:bg-white/10 transition-all">
                    <div class="w-10 h-10 rounded-xl bg-hanoi-gold/20 text-hanoi-gold flex items-center justify-center text-lg mb-4">
                        <i class="fa-solid fa-shoe-prints"></i>
                    </div>
                    <h3 class="font-bold text-lg text-hanoi-gold mb-2">街头擦鞋与椰子摊陷阱</h3>
                    <p class="text-stone-300 text-sm leading-relaxed">
                        古街若有人热情强行帮你擦鞋或把椰子担子搭在你肩上拍照，事后会索要高价。礼貌摇手说“No”即可。
                    </p>
                </div>

                <div class="bg-white/5 border border-white/10 p-6 rounded-2xl hover:bg-white/10 transition-all">
                    <div class="w-10 h-10 rounded-xl bg-hanoi-gold/20 text-hanoi-gold flex items-center justify-center text-lg mb-4">
                        <i class="fa-solid fa-sim-card"></i>
                    </div>
                    <h3 class="font-bold text-lg text-hanoi-gold mb-2">网络与小费文化</h3>
                    <p class="text-stone-300 text-sm leading-relaxed">
                        机场可直接办 Viettel 4G卡。越南并非严格小费国，但满意服务可留 20,000₫ (~6元) 零钱作为谢意。
                    </p>
                </div>

            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-stone-900 text-stone-400 py-12 border-t border-stone-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center sm:flex sm:justify-between sm:items-center">
            <div class="mb-4 sm:mb-0">
                <p class="text-sm">© 2026 Hanoi Travel Guide · 越夜越美丽 河内指南</p>
                <p class="text-xs text-stone-500 mt-1">愿你在古街的咖啡香与河粉汤气中，遇见最惬意的东南亚慢时光。</p>
            </div>
            <div class="flex justify-center space-x-6 text-lg">
                <a href="#" class="hover:text-hanoi-gold transition-colors"><i class="fa-brands fa-instagram"></i></a>
                <a href="#" class="hover:text-hanoi-gold transition-colors"><i class="fa-brands fa-xiaohongshu"></i></a>
                <a href="#" class="hover:text-hanoi-gold transition-colors"><i class="fa-solid fa-envelope"></i></a>
            </div>
        </div>
    </footer>

    <!-- Spot Detail Modal -->
    <div id="spotModal" class="fixed inset-0 z-50 flex items-center justify-center bg-black/60 backdrop-blur-sm hidden p-4 opacity-0 transition-opacity duration-300">
        <div class="bg-white w-full max-w-2xl rounded-3xl overflow-hidden shadow-2xl border border-hanoi-gold/20 transform scale-95 transition-transform duration-300" id="spotModalContent">
            <!-- Modal Body Injected Dynamically -->
        </div>
    </div>

    <!-- Favorites Drawer -->
    <div id="favDrawer" class="fixed inset-y-0 right-0 z-50 w-full max-w-md bg-white shadow-2xl transform translate-x-full transition-transform duration-300 flex flex-col">
        <div class="p-6 bg-hanoi-paper border-b border-hanoi-gold/20 flex items-center justify-between">
            <div class="flex items-center space-x-2">
                <i class="fa-solid fa-heart text-hanoi-terracotta text-xl"></i>
                <h3 class="font-bold text-lg text-stone-800 font-serif-title">我的河内收藏夹</h3>
            </div>
            <button onclick="toggleFavDrawer(false)" class="text-stone-400 hover:text-stone-700 text-xl">
                <i class="fa-solid fa-xmark"></i>
            </button>
        </div>

        <div id="favListContainer" class="p-6 flex-1 overflow-y-auto space-y-4">
            <!-- Saved items will appear here -->
        </div>

        <div class="p-6 border-t border-stone-100 bg-stone-50">
            <button onclick="clearAllFavorites()" class="w-full bg-stone-200 hover:bg-stone-300 text-stone-700 font-semibold py-2.5 rounded-xl text-sm transition-all">
                清空收藏
            </button>
        </div>
    </div>

    <!-- Custom Toast Notification -->
    <div id="toast" class="fixed bottom-6 right-6 z-50 bg-stone-900 text-white px-5 py-3 rounded-2xl shadow-xl border border-hanoi-gold/30 flex items-center space-x-3 translate-y-20 opacity-0 transition-all duration-300">
        <i class="fa-solid fa-circle-check text-hanoi-gold text-lg" id="toastIcon"></i>
        <span id="toastMessage" class="text-sm font-medium">收藏成功！</span>
    </div>

    <script>
        // Data Store
        const spotsData = [
            {
                id: 'pho-1',
                category: 'food',
                title: 'Phở Gia Truyền Bát Đàn',
                cnTitle: '百年百年老店 · 传统牛肉河粉',
                image: 'https://images.unsplash.com/photo-1582878826629-29b7ad1cdc43?auto=format&fit=crop&w=800&q=80',
                fallbackImage: 'https://placehold.co/800x600/451A03/FFF?text=Vietnamese+Pho',
                rating: 4.8,
                reviews: 3200,
                price: '55,000₫ - 85,000₫ (~¥16-25)',
                address: '49P. Bát Đàn, Cửa Đông, Hoàn Kiếm, Hà Nội',
                time: '06:00 - 10:00, 18:00 - 20:30',
                desc: '河内知名度最高的高汤牛肉粉之一！每天早晨排长龙。老式铜锅慢炖十余小时的牛骨清汤，牛肉鲜嫩，配上生姜与新鲜九层塔，地道老河内风味。',
                tags: ['米其林必比登推荐', '必吃早餐', '古街百年'],
                tips: '排队需要先付款再自助端粉，建议加一份油条 (Quẩy) 蘸汤吃！'
            },
            {
                id: 'egg-coffee-1',
                category: 'coffee',
                title: 'Giảng Cà Phê',
                cnTitle: '创始店 · 经典蛋黄咖啡',
                image: 'https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?auto=format&fit=crop&w=800&q=80',
                fallbackImage: 'https://placehold.co/800x600/D97706/FFF?text=Egg+Coffee',
                rating: 4.9,
                reviews: 4500,
                price: '35,000₫ (~¥10)',
                address: '39 Nguyễn Hữu Huân, Lý Thái Tổ, Hoàn Kiếm, Hà Nội',
                time: '07:00 - 22:30',
                desc: '1946年创办的蛋黄咖啡发源地。将打发的蛋黄奶霜与浓烈越南罗布斯塔咖啡结合，口感顺滑如提拉米苏，甜而不腻，香浓丝滑。',
                tags: ['1946创始', '地道老字号', '特色饮品'],
                tips: '入口隐藏在窄巷中，顺着楼梯上二楼别有洞天。热蛋咖啡最经典！'
            },
            {
                id: 'buncha-1',
                category: 'food',
                title: 'Bún Chả Hương Liên',
                cnTitle: '奥巴马同款 · 炭烤猪肉米粉',
                image: 'https://images.unsplash.com/photo-1569718212165-3a8278d5f624?auto=format&fit=crop&w=800&q=80',
                fallbackImage: 'https://placehold.co/800x600/C2410C/FFF?text=Bun+Cha',
                rating: 4.7,
                reviews: 2800,
                price: '60,000₫ - 90,000₫ (~¥18-27)',
                address: '24 Lê Văn Hưu, Phan Chu Trinh, Hai Bà Trưng, Hà Nội',
                time: '08:00 - 20:30',
                desc: '美国前总统奥巴马与厨神安东尼·波登曾亲临的烤肉米粉店！炭火烤制的猪肉饼浸在酸甜适口的鱼露高汤中，配上冷米粉与新鲜香菜。',
                tags: ['名人打卡', '炭烤香气', '传统名吃'],
                tips: '直接点一份 "Combo Obama"（烤肉米粉+炸海鲜春卷+越南啤酒）。'
            },
            {
                id: 'sight-1',
                category: 'sight',
                title: 'Hoàn Kiếm Lake & Ngọc Sơn Temple',
                cnTitle: '还剑湖 & 玉山祠',
                image: 'https://images.unsplash.com/photo-1555921015-5532091f6026?auto=format&fit=crop&w=800&q=80',
                fallbackImage: 'https://placehold.co/800x600/0F5132/FFF?text=Hoan+Kiem+Lake',
                rating: 4.8,
                reviews: 6200,
                price: '门票 30,000₫ (~¥9)',
                address: 'Hoàn Kiếm, Hà Nội',
                time: '全天开放 (玉山祠 08:00-18:00)',
                desc: '河内的心脏与灵魂。清晨有当地人在此晨练太极，夜晚红色的栖旭桥点亮湖面，浪漫至极。湖中心还有传奇的神龟塔。',
                tags: ['地标景观', '湖畔漫步', '市中心'],
                tips: '每逢周末晚上，还剑湖四周会划为步行街，有街头音乐与传统民间游戏。'
            },
            {
                id: 'sight-2',
                category: 'sight',
                title: 'St. Joseph Cathedral',
                cnTitle: '圣若瑟大教堂 · 小巴黎风情',
                image: 'https://images.unsplash.com/photo-1509042239860-f550ce710b93?auto=format&fit=crop&w=800&q=80',
                fallbackImage: 'https://placehold.co/800x600/451A03/FFF?text=St+Joseph+Cathedral',
                rating: 4.7,
                reviews: 3900,
                price: '免费参观',
                address: '40 Nhà Chung, Hàng Trống, Hoàn Kiếm, Hà Nội',
                time: '08:00 - 11:00, 14:00 - 17:00',
                desc: '建于1886年的新哥特式建筑，模仿巴黎圣母院风格。复古斑驳的灰黑墙面充满岁月感，是河内拍照最抢眼的地标之一。',
                tags: ['法式建筑', '摄影圣地', '古街地标'],
                tips: '教堂正对面的柠檬茶摊 (Trà Chanh) 是河内年轻人最爱的街头聚会点。'
            },
            {
                id: 'night-1',
                category: 'night',
                title: 'Tạ Hiện Beer Street',
                cnTitle: '谢现啤酒街 · 不夜城狂欢',
                image: 'https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=800&q=80',
                fallbackImage: 'https://placehold.co/800x600/C2410C/FFF?text=Ta+Hien+Beer+Street',
                rating: 4.6,
                reviews: 5100,
                price: '生啤酒 15,000₫/杯 (~¥4 rounded)',
                address: 'Tạ Hiện, Hàng Buồm, Hoàn Kiếm, Hà Nội',
                time: '18:00 - 深夜 02:00',
                desc: '河内最火爆的夜生活集聚地！整条街坐满了坐在矮塑料凳上喝着鲜啤酒 (Bia Hơi)、吃着烤黄鱼和下酒菜的各国游客与青年。',
                tags: ['夜生活', '街头鲜啤酒', '氛围感爆棚'],
                tips: '尝尝本地廉价鲜啤酒 Bia Hơi，爽口解腻，顺便感受超嗨氛围。'
            },
            {
                id: 'food-2',
                category: 'food',
                title: 'Bánh Mì 25',
                cnTitle: 'Bánh Mì 25 · 网红脆皮法包',
                image: 'https://images.unsplash.com/photo-1626804475297-4160820cc6e5?auto=format&fit=crop&w=800&q=80',
                fallbackImage: 'https://placehold.co/800x600/D97706/FFF?text=Banh+Mi',
                rating: 4.8,
                reviews: 4100,
                price: '30,000₫ - 50,000₫ (~¥9-15)',
                address: '25 Hàng Cá, Hàng Bồ, Hoàn Kiếm, Hà Nội',
                time: '07:00 - 21:00',
                desc: '外皮酥脆到掉渣的法式面包，夹入秘制猪肉酱、叉烧、酸黄瓜、香菜与辣椒酱。咬下去层次极丰富！',
                tags: ['快速简餐', '酥脆法包', '人气极高'],
                tips: '提供素食与牛肉/鸡肉多种选择，搭配一杯新鲜现榨芒果汁超赞！'
            },
            {
                id: 'sight-3',
                category: 'sight',
                title: 'Hanoi Train Street Coffee',
                cnTitle: '河内火车街咖啡馆',
                image: 'https://images.unsplash.com/photo-1528127269322-539801943592?auto=format&fit=crop&w=800&q=80',
                fallbackImage: 'https://placehold.co/800x600/0F5132/FFF?text=Hanoi+Train+Street',
                rating: 4.7,
                reviews: 3100,
                price: '饮品 40,000₫ (~¥12)',
                address: 'Phố Đường Tàu, Hàng Bông, Hoàn Kiếm, Hà Nội',
                time: '咖啡馆全天开放 (火车班次依时刻表)',
                desc: '火车从紧挨着咖啡馆桌椅仅几十厘米的窄巷中呼啸而过！绝无仅有的奇幻体验，喝咖啡的同时感受轰鸣声。',
                tags: ['奇观体验', '网红打卡', '拍照绝佳'],
                tips: '由于安全管制，入口常有警察，需要由铁道旁咖啡馆老板带入才能进入。'
            },
            {
                id: 'coffee-2',
                category: 'coffee',
                title: 'Loading T Café',
                cnTitle: '百年法式老宅 · 肉桂咖啡',
                image: 'https://images.unsplash.com/photo-1501339847302-ac426a4a7cbb?auto=format&fit=crop&w=800&q=80',
                fallbackImage: 'https://placehold.co/800x600/451A03/FFF?text=Loading+T+Cafe',
                rating: 4.9,
                reviews: 1200,
                price: '45,000₫ - 65,000₫ (~¥13-19)',
                address: '8 Chân Cầm, Hàng Trống, Hoàn Kiếm, Hà Nội',
                time: '08:00 - 18:00',
                desc: '隐匿在古老法式建筑二楼的复古咖啡馆，拥有原汁原味的彩色花砖与木质百叶窗。招牌肉桂咖啡香气馥郁，极其优雅。',
                tags: ['法式复古', '肉桂咖啡', '安静角落'],
                tips: '拍照氛围极佳，非常适合午后避暑与享受慢时光。'
            }
        ];

        const phrases = [
            { vi: 'Xin chào', cn: '你好', phonetic: '心 潮' },
            { vi: 'Cảm ơn', cn: '谢谢', phonetic: '感 恩' },
            { vi: 'Bao nhiêu tiền?', cn: '多少钱？', phonetic: '包 纽 甜' },
            { vi: 'Tính tiền', cn: '买单结账', phonetic: '顶 甜' },
            { vi: 'Không cay', cn: '不要辣', phonetic: '空 该' },
            { vi: 'Một, Hai, Ba', cn: '1, 2, 3', phonetic: '莫、海、巴' }
        ];

        const itineraryData = {
            1: [
                { time: '08:00', title: '地道晨光 · 享用 Phở Gia Truyền 牛肉粉', desc: '在古街八旦街享用热气腾腾的古法高汤牛肉河粉，搭配酥脆油条。' },
                { time: '09:30', title: '漫步还剑湖 & 参观玉山祠', desc: '沿着湖畔散步，穿过朱红色的栖旭桥，感受河内市中心的宁静与神话故事。' },
                { time: '11:30', title: '午餐 · Bún Chả 香气扑鼻炭烤肉米粉', desc: '前往奥巴马同款或古街老店，品尝酸甜高汤里的炭烤猪肉饼与鲜米粉。' },
                { time: '14:00', title: '探秘 1946 创始店 Giảng Cà Phê', desc: '在穿过狭窄巷弄后，品尝一杯热气腾腾、口感如提拉米苏般绵密的鸡蛋咖啡。' },
                { time: '16:30', title: '圣若瑟大教堂 & 36行街漫游', desc: '在大教堂前合影，随后打卡鞋巷、银巷、草席巷等充满历史烟火气的古街。' },
                { time: '19:30', title: '夜生活 · Tạ Hiện 啤酒街欢聚', desc: '坐在矮脚塑料凳上，喝着15,000盾一杯的本地鲜啤酒，感受全球旅人的狂欢。' }
            ],
            2: [
                { time: '08:30', title: '法式清晨 · Bánh Mì 25 脆皮法包', desc: '以一份刚出炉的丰富馅料越南法包和现榨芒果汁开启美好的一天。' },
                { time: '10:00', title: '参观越南妇女博物馆或总督府外围', desc: '了解越南丰富人文历史，欣赏保留完好的法式殖民建筑群。' },
                { time: '12:30', title: '午餐 · Chả Cá Lăng 鱧鱼锅', desc: '品尝河内独有的传统名菜：用姜黄与莳萝煎炸的鲜鱼块，配米粉与花生。' },
                { time: '15:00', title: '前往西湖 (Tây Hồ) & 镇国寺', desc: '河内最大的湖泊，租一辆自行车环湖，参观屹立湖畔千年历史的古老佛塔。' },
                { time: '18:00', title: '西湖日落与高级法餐/湖畔咖啡', desc: '在西湖畔找一家露台餐厅，欣赏金黄色的湖面日落，享受悠闲晚餐。' }
            ],
            3: [
                { time: '09:00', title: 'Loading T 咖啡馆复古迟到早餐', desc: '在百年来留存的花砖法式建筑里，喝一杯带着肉桂香气的特调咖啡。' },
                { time: '11:00', title: '河内火车街 (Train Street) 惊险体验', desc: '紧靠着铁轨喝一杯椰子咖啡，近距离感受火车贴身驶过的震撼。' },
                { time: '13:00', title: '同春市场 (Đồng Xuân) 伴手礼采买', desc: '选购越南腰果、咖啡豆、腰果、干果与传统手工丝绸。' },
                { time: '16:00', title: '升龙水上木偶戏 (Water Puppet)', desc: '在还剑湖畔剧场欣赏越南独特的世界非物质文化遗产艺术表演。' }
            ]
        };

        // Favorites state stored in LocalStorage
        let favorites = JSON.parse(localStorage.getItem('hanoi_favs')) || [];

        document.addEventListener('DOMContentLoaded', () => {
            renderSpots(spotsData);
            renderPhrases();
            switchDay(1);
            updateFavBadge();
            convertCurrency();
        });

        // Render Spots Grid
        function renderSpots(items) {
            const grid = document.getElementById('spotsGrid');
            grid.innerHTML = '';

            if (items.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full text-center py-12 text-stone-400">
                        <i class="fa-solid fa-compass-slash text-4xl mb-3"></i>
                        <p>未找到符合条件的地点，尝试换个关键词搜索吧！</p>
                    </div>
                `;
                return;
            }

            items.forEach(spot => {
                const isFav = favorites.includes(spot.id);
                const card = document.createElement('div');
                card.className = 'bg-white rounded-3xl overflow-hidden border border-hanoi-gold/15 shadow-md hover:shadow-xl transition-all duration-300 flex flex-col group';
                card.innerHTML = `
                    <div class="relative h-52 overflow-hidden bg-stone-100">
                        <img src="${spot.image}" alt="${spot.title}" 
                             onerror="this.onerror=null; this.src='${spot.fallbackImage}';"
                             class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute top-3 right-3 flex space-x-2">
                            <button onclick="toggleFavorite('${spot.id}', event)" class="w-10 h-10 rounded-full bg-white/80 backdrop-blur-md text-stone-700 hover:text-hanoi-terracotta flex items-center justify-center shadow-md transition-all">
                                <i class="${isFav ? 'fa-solid text-hanoi-terracotta' : 'fa-regular'} fa-heart text-lg"></i>
                            </button>
                        </div>
                        <div class="absolute bottom-3 left-3 bg-stone-900/70 backdrop-blur-md text-white text-xs px-3 py-1 rounded-full flex items-center space-x-1">
                            <i class="fa-solid fa-star text-hanoi-gold"></i>
                            <span class="font-bold">${spot.rating}</span>
                            <span class="text-stone-300">(${spot.reviews})</span>
                        </div>
                    </div>

                    <div class="p-6 flex-1 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center space-x-2 mb-2">
                                ${spot.tags.map(t => `<span class="bg-hanoi-paper text-hanoi-ochre text-[11px] font-semibold px-2.5 py-0.5 rounded-md">${t}</span>`).join('')}
                            </div>
                            <h3 class="font-bold text-xl text-stone-900 font-serif-title group-hover:text-hanoi-gold transition-colors">${spot.title}</h3>
                            <p class="text-xs text-hanoi-gold font-medium mb-3">${spot.cnTitle}</p>
                            <p class="text-stone-600 text-sm line-clamp-2 mb-4 leading-relaxed">${spot.desc}</p>
                        </div>

                        <div>
                            <div class="flex items-center text-xs text-stone-500 mb-4 font-medium">
                                <i class="fa-solid fa-tag text-hanoi-terracotta mr-1.5"></i>
                                <span>${spot.price}</span>
                            </div>
                            <button onclick="openSpotModal('${spot.id}')" class="w-full bg-hanoi-cream hover:bg-hanoi-gold hover:text-white text-hanoi-darkteal border border-hanoi-gold/30 font-semibold py-2.5 rounded-xl text-sm transition-all flex items-center justify-center space-x-2">
                                <span>查看地道攻略</span>
                                <i class="fa-solid fa-arrow-right text-xs"></i>
                            </button>
                        </div>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        // Filter Category
        function filterCategory(cat) {
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('bg-hanoi-teal', 'text-white');
                btn.classList.add('bg-white', 'text-stone-600');
            });
            event.currentTarget.classList.remove('bg-white', 'text-stone-600');
            event.currentTarget.classList.add('bg-hanoi-teal', 'text-white');

            if (cat === 'all') {
                renderSpots(spotsData);
            } else {
                renderSpots(spotsData.filter(s => s.category === cat));
            }
        }

        // Search Spot
        function applySearch() {
            const query = document.getElementById('searchInput').value.toLowerCase().trim();
            if (!query) {
                renderSpots(spotsData);
                return;
            }
            const filtered = spotsData.filter(s => 
                s.title.toLowerCase().includes(query) ||
                s.cnTitle.toLowerCase().includes(query) ||
                s.desc.toLowerCase().includes(query) ||
                s.tags.some(t => t.toLowerCase().includes(query))
            );
            renderSpots(filtered);
        }

        // Modal Handler
        function openSpotModal(id) {
            const spot = spotsData.find(s => s.id === id);
            if (!spot) return;

            const modal = document.getElementById('spotModal');
            const content = document.getElementById('spotModalContent');
            const isFav = favorites.includes(spot.id);

            content.innerHTML = `
                <div class="relative h-64 sm:h-72 bg-stone-900">
                    <img src="${spot.image}" alt="${spot.title}" 
                         onerror="this.onerror=null; this.src='${spot.fallbackImage}';"
                         class="w-full h-full object-cover opacity-90">
                    <button onclick="closeSpotModal()" class="absolute top-4 right-4 w-9 h-9 bg-black/50 hover:bg-black text-white rounded-full flex items-center justify-center text-lg transition-all">
                        <i class="fa-solid fa-xmark"></i>
                    </button>
                    <div class="absolute bottom-4 left-4 right-4 text-white">
                        <span class="bg-hanoi-gold text-white text-xs font-bold px-3 py-1 rounded-full uppercase tracking-wider mb-2 inline-block">Hanoi Essential</span>
                        <h2 class="text-2xl sm:text-3xl font-bold font-serif-title">${spot.title}</h2>
                        <p class="text-stone-200 text-sm font-medium">${spot.cnTitle}</p>
                    </div>
                </div>

                <div class="p-6 sm:p-8 max-h-[60vh] overflow-y-auto space-y-6">
                    <div>
                        <h4 class="text-xs font-bold text-stone-400 uppercase tracking-wider mb-1">特色简介</h4>
                        <p class="text-stone-700 leading-relaxed text-sm sm:text-base">${spot.desc}</p>
                    </div>

                    <div class="bg-hanoi-paper/60 p-4 rounded-2xl border border-hanoi-gold/20 space-y-3 text-sm">
                        <div class="flex items-start space-x-3">
                            <i class="fa-solid fa-location-dot text-hanoi-terracotta mt-1"></i>
                            <div>
                                <span class="font-bold text-stone-800 block">地址 (出示给Grab司机会话):</span>
                                <span class="text-stone-600 select-all font-mono text-xs bg-white px-2 py-1 rounded border border-stone-200 inline-block mt-1">${spot.address}</span>
                            </div>
                        </div>

                        <div class="flex items-center space-x-3">
                            <i class="fa-solid fa-clock text-hanoi-gold"></i>
                            <div>
                                <span class="font-bold text-stone-800">营业时间: </span>
                                <span class="text-stone-600">${spot.time}</span>
                            </div>
                        </div>

                        <div class="flex items-center space-x-3">
                            <i class="fa-solid fa-wallet text-hanoi-darkteal"></i>
                            <div>
                                <span class="font-bold text-stone-800">参考消费: </span>
                                <span class="text-stone-600 font-semibold text-hanoi-ochre">${spot.price}</span>
                            </div>
                        </div>
                    </div>

                    <div class="bg-amber-50 p-4 rounded-2xl border border-amber-200 text-sm">
                        <div class="flex items-center space-x-2 text-hanoi-ochre font-bold mb-1">
                            <i class="fa-solid fa-lightbulb"></i>
                            <span>老客避坑/地道 Tip:</span>
                        </div>
                        <p class="text-amber-900 text-xs sm:text-sm">${spot.tips}</p>
                    </div>
                </div>

                <div class="p-4 sm:p-6 bg-stone-50 border-t border-stone-100 flex items-center justify-between">
                    <button onclick="toggleFavorite('${spot.id}', event); closeSpotModal();" class="flex items-center space-x-2 text-stone-700 hover:text-hanoi-terracotta font-semibold text-sm">
                        <i class="${isFav ? 'fa-solid text-hanoi-terracotta' : 'fa-regular'} fa-heart text-lg"></i>
                        <span>${isFav ? '已在收藏夹' : '加入我的收藏'}</span>
                    </button>
                    <button onclick="closeSpotModal()" class="bg-hanoi-teal hover:bg-hanoi-darkteal text-white px-6 py-2.5 rounded-xl font-bold text-sm shadow transition-all">
                        关 闭
                    </button>
                </div>
            `;

            modal.classList.remove('hidden');
            setTimeout(() => {
                modal.classList.remove('opacity-0');
                document.getElementById('spotModalContent').classList.remove('scale-95');
            }, 10);
        }

        function closeSpotModal() {
            const modal = document.getElementById('spotModal');
            modal.classList.add('opacity-0');
            document.getElementById('spotModalContent').classList.add('scale-95');
            setTimeout(() => modal.classList.add('hidden'), 300);
        }

        // Days Switcher
        function switchDay(dayNum) {
            document.querySelectorAll('.day-tab').forEach(btn => {
                btn.classList.remove('bg-hanoi-teal', 'text-white', 'shadow-sm');
                btn.classList.add('text-stone-600');
            });
            const activeBtn = document.getElementById(`dayBtn${dayNum}`);
            activeBtn.classList.remove('text-stone-600');
            activeBtn.classList.add('bg-hanoi-teal', 'text-white', 'shadow-sm');

            const container = document.getElementById('itineraryContent');
            const list = itineraryData[dayNum];

            container.innerHTML = `
                <div class="relative border-l-2 border-hanoi-gold/30 ml-4 sm:ml-6 space-y-8">
                    ${list.map(item => `
                        <div class="relative pl-6 sm:pl-8 group">
                            <div class="absolute -left-[9px] top-1.5 w-4 h-4 rounded-full bg-hanoi-gold border-4 border-white shadow"></div>
                            <span class="inline-block text-xs font-bold text-hanoi-gold uppercase tracking-wider bg-hanoi-paper px-2.5 py-0.5 rounded-full mb-1">${item.time}</span>
                            <h3 class="text-lg sm:text-xl font-bold text-stone-800 font-serif-title mt-1">${item.title}</h3>
                            <p class="text-stone-600 text-sm mt-2 leading-relaxed">${item.desc}</p>
                        </div>
                    `).join('')}
                </div>
            `;
        }

        // Currency Converter
        function convertCurrency() {
            const vnd = parseFloat(document.getElementById('vndInput').value) || 0;
            // Approximate rates: 1 CNY = 3500 VND; 1 USD = 25500 VND
            const cny = (vnd / 3500).toFixed(1);
            const usd = (vnd / 25500).toFixed(1);

            document.getElementById('cnyOutput').innerText = `¥ ${cny}`;
            document.getElementById('usdOutput').innerText = `$ ${usd}`;
        }

        // Phrases Render & Audio Pronounce
        function renderPhrases() {
            const container = document.getElementById('phrasesList');
            container.innerHTML = phrases.map(p => `
                <div class="p-3 bg-stone-50 hover:bg-hanoi-paper/60 rounded-xl border border-stone-200/60 flex items-center justify-between transition-colors">
                    <div>
                        <div class="font-bold text-stone-800 text-sm font-mono">${p.vi}</div>
                        <div class="text-xs text-stone-500">${p.cn} <span class="text-hanoi-gold ml-1">(${p.phonetic})</span></div>
                    </div>
                    <button onclick="speakVietnamese('${p.vi}')" class="w-8 h-8 rounded-full bg-white border border-stone-200 text-hanoi-teal hover:bg-hanoi-teal hover:text-white transition-all flex items-center justify-center shadow-sm">
                        <i class="fa-solid fa-volume-high text-xs"></i>
                    </button>
                </div>
            `).join('');
        }

        function speakVietnamese(text) {
            if ('speechSynthesis' in window) {
                const utterance = new SpeechSynthesisUtterance(text);
                utterance.lang = 'vi-VN';
                window.speechSynthesis.speak(utterance);
                showToast(`正在朗读: "${text}"`);
            } else {
                showToast(`发音: ${text}`);
            }
        }

        // Random Food Spinner
        function spinRandomFood() {
            const resultTitle = document.getElementById('randomResultTitle');
            const resultSub = document.getElementById('randomResultSub');
            
            resultTitle.innerText = "抽取中...";
            resultSub.innerText = "转盘旋转中，请稍候...";

            let count = 0;
            const interval = setInterval(() => {
                const rand = spotsData[Math.floor(Math.random() * spotsData.length)];
                resultTitle.innerText = rand.cnTitle.split('·')[1] || rand.cnTitle;
                count++;
                if (count > 10) {
                    clearInterval(interval);
                    const finalPick = spotsData[Math.floor(Math.random() * spotsData.length)];
                    resultTitle.innerText = finalPick.title;
                    resultSub.innerText = `推荐打卡: ${finalPick.cnTitle}`;
                    showToast(`为你抽到了: ${finalPick.title}！`);
                }
            }, 100);
        }

        // Favorite Toggle & Drawer
        function toggleFavorite(id, event) {
            if(event) event.stopPropagation();
            
            const index = favorites.indexOf(id);
            if (index > -1) {
                favorites.splice(index, 1);
                showToast('已从收藏夹移除');
            } else {
                favorites.push(id);
                showToast('已保存至我的河内行程！');
            }
            
            localStorage.setItem('hanoi_favs', JSON.stringify(favorites));
            updateFavBadge();
            renderSpots(spotsData);
            renderFavList();
        }

        function updateFavBadge() {
            document.getElementById('favCountBadge').innerText = favorites.length;
        }

        function toggleFavDrawer(open) {
            const drawer = document.getElementById('favDrawer');
            if (open) {
                renderFavList();
                drawer.classList.remove('translate-x-full');
            } else {
                drawer.classList.add('translate-x-full');
            }
        }

        document.getElementById('openFavoritesBtn').addEventListener('click', () => toggleFavDrawer(true));

        function renderFavList() {
            const container = document.getElementById('favListContainer');
            if (favorites.length === 0) {
                container.innerHTML = `
                    <div class="text-center py-12 text-stone-400">
                        <i class="fa-regular fa-heart text-4xl mb-3 text-stone-300"></i>
                        <p class="text-sm">暂无收藏地点，快去探索心仪吃喝玩乐吧！</p>
                    </div>
                `;
                return;
            }

            const favSpots = spotsData.filter(s => favorites.includes(s.id));
            container.innerHTML = favSpots.map(s => `
                <div class="p-3 bg-stone-50 rounded-2xl border border-stone-200 flex items-center justify-between">
                    <div class="flex items-center space-x-3">
                        <img src="${s.image}" class="w-12 h-12 rounded-xl object-cover" onerror="this.src='${s.fallbackImage}'">
                        <div>
                            <h4 class="font-bold text-stone-800 text-sm font-serif-title">${s.title}</h4>
                            <span class="text-xs text-hanoi-gold">${s.cnTitle}</span>
                        </div>
                    </div>
                    <button onclick="toggleFavorite('${s.id}')" class="text-stone-400 hover:text-hanoi-terracotta p-2">
                        <i class="fa-solid fa-trash-can text-sm"></i>
                    </button>
                </div>
            `).join('');
        }

        function clearAllFavorites() {
            favorites = [];
            localStorage.setItem('hanoi_favs', JSON.stringify(favorites));
            updateFavBadge();
            renderFavList();
            renderSpots(spotsData);
            showToast('已清空所有收藏');
        }

        // Toast Helper
        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toastMessage').innerText = msg;
            toast.classList.remove('translate-y-20', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 2500);
        }
    </script>
</body>
</html>
