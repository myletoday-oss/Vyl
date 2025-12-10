<!DOCTYPE html>
<html lang="vi" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cẩm Nang: Quy Trình Tạo Lập Nội Dung Số</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@500;700&display=swap" rel="stylesheet">
    <style>
        body { 
            font-family: 'Outfit', sans-serif; 
            background-color: #fff1f2; /* Rose-50 background */
            color: #4a044e; /* Dark Fuchsia text */
            overflow-x: hidden;
            font-size: 18px;
        }
        h1, h2, h3, h4, h5 { font-family: 'Space Grotesk', sans-serif; }
        
        /* Liquid Background Animation */
        .liquid-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
            background: linear-gradient(135deg, #fff1f2 0%, #fef2f2 100%);
        }
        .blob {
            position: absolute;
            filter: blur(90px);
            opacity: 0.6;
            animation: float 25s infinite alternate;
            z-index: -1;
        }
        .blob-1 { top: -10%; left: -10%; width: 50vw; height: 50vw; background: #f472b6; animation-delay: 0s; }
        .blob-2 { bottom: -10%; right: -10%; width: 60vw; height: 60vw; background: #fbbf24; animation-delay: -5s; }
        .blob-3 { top: 40%; left: 30%; width: 40vw; height: 40vw; background: #a78bfa; animation-delay: -10s; }

        @keyframes float {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(40px, 40px) scale(1.05); }
        }

        /* Glassmorphism Classes */
        .glass-panel {
            background: rgba(255, 255, 255, 0.6);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.9);
            box-shadow: 0 8px 32px 0 rgba(219, 39, 119, 0.1);
        }
        .glass-card {
            background: rgba(255, 255, 255, 0.5);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.7);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 4px 6px -1px rgba(219, 39, 119, 0.05);
        }
        .glass-card:hover {
            background: rgba(255, 255, 255, 0.9);
            border-color: #fce7f3;
            transform: translateY(-8px) scale(1.01);
            box-shadow: 0 20px 25px -5px rgba(219, 39, 119, 0.15);
        }

        /* Text Gradients */
        .text-gradient-main {
            background: linear-gradient(to right, #db2777, #7c3aed, #ea580c);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 10px; }
        ::-webkit-scrollbar-track { background: #fff1f2; }
        ::-webkit-scrollbar-thumb { background: #f472b6; border-radius: 5px; }
        ::-webkit-scrollbar-thumb:hover { background: #db2777; }

        /* Navigation Active State */
        .nav-link.active {
            background: rgba(255, 255, 255, 0.8);
            border-left: 4px solid #db2777;
            color: #831843;
            font-weight: 700;
            box-shadow: 0 4px 6px -1px rgba(219, 39, 119, 0.1);
        }
    </style>
</head>
<body class="text-slate-800">

    <!-- Liquid Background -->
    <div class="liquid-bg">
        <div class="blob blob-1 rounded-full mix-blend-multiply"></div>
        <div class="blob blob-2 rounded-full mix-blend-multiply"></div>
        <div class="blob blob-3 rounded-full mix-blend-multiply"></div>
    </div>

    <!-- Sidebar Navigation -->
    <aside class="fixed inset-y-0 left-0 w-80 glass-panel z-50 flex flex-col hidden lg:flex border-r-0 rounded-r-3xl my-4 ml-4 h-[calc(100vh-2rem)]">
        <div class="p-8 border-b border-pink-100/50">
            <h1 class="font-bold text-2xl flex items-center gap-3 tracking-wide text-fuchsia-900">
                <div class="bg-white p-2.5 rounded-xl shadow-md border border-pink-100">
                    <i data-lucide="layers" class="text-fuchsia-600 w-7 h-7"></i>
                </div>
                Cẩm Nang Số
            </h1>
            <p class="text-sm text-fuchsia-500 mt-2 font-medium tracking-widest uppercase pl-1">Powered by AI</p>
        </div>
        <nav class="flex-1 overflow-y-auto py-8 px-6 space-y-4">
            <a href="#hero" class="nav-link flex items-center gap-4 px-4 py-3.5 rounded-xl hover:bg-white/60 transition text-fuchsia-700 hover:text-fuchsia-900 group">
                <i data-lucide="home" class="w-6 h-6 group-hover:scale-110 transition-transform text-fuchsia-500"></i> Giới Thiệu
            </a>
            <div class="pt-4 pb-2 text-xs font-bold text-fuchsia-400 uppercase tracking-widest px-4">Lộ Trình Triển Khai</div>
            <a href="#phase1" class="nav-link flex items-center gap-4 px-4 py-3.5 rounded-xl hover:bg-white/60 transition text-fuchsia-700 hover:text-rose-700 group border border-transparent">
                <span class="bg-rose-100 text-rose-600 w-8 h-8 rounded-lg flex items-center justify-center text-sm font-bold group-hover:bg-rose-600 group-hover:text-white transition-all">1</span>
                Phân Tích
            </a>
            <a href="#phase2" class="nav-link flex items-center gap-4 px-4 py-3.5 rounded-xl hover:bg-white/60 transition text-fuchsia-700 hover:text-violet-700 group border border-transparent">
                <span class="bg-violet-100 text-violet-600 w-8 h-8 rounded-lg flex items-center justify-center text-sm font-bold group-hover:bg-violet-600 group-hover:text-white transition-all">2</span>
                Lập Kế Hoạch
            </a>
            <a href="#phase3" class="nav-link flex items-center gap-4 px-4 py-3.5 rounded-xl bg-white/40 border border-amber-200 text-amber-900 group relative overflow-hidden shadow-sm">
                <div class="absolute inset-0 bg-amber-50 blur-xl group-hover:bg-amber-100 transition-all opacity-50"></div>
                <span class="relative bg-amber-500 text-white w-8 h-8 rounded-lg flex items-center justify-center text-sm font-bold shadow-md">3</span>
                <span class="relative font-bold">Sản Xuất (AI)</span>
                <i data-lucide="sparkles" class="relative w-5 h-5 ml-auto text-amber-600 animate-pulse"></i>
            </a>
        </nav>
        <div class="p-6 border-t border-pink-100/50 text-xs text-fuchsia-400 text-center font-medium">
            &copy; 2025 EdTech Innovation
        </div>
    </aside>

    <!-- Main Content -->
    <main class="lg:ml-80 min-h-screen px-4 lg:px-8 py-8">
        
        <!-- Mobile Header -->
        <div class="lg:hidden glass-panel rounded-2xl p-4 sticky top-4 z-40 mb-8 flex justify-between items-center shadow-lg">
            <span class="font-bold text-xl text-fuchsia-900">Quy Trình Tạo Lập</span>
            <button onclick="document.querySelector('aside').classList.toggle('hidden'); document.querySelector('aside').classList.toggle('flex'); document.querySelector('aside').classList.toggle('fixed'); document.querySelector('aside').classList.toggle('inset-0'); document.querySelector('aside').classList.toggle('w-full'); document.querySelector('aside').classList.toggle('m-0'); document.querySelector('aside').classList.toggle('rounded-none');" class="p-2.5 bg-white rounded-xl text-fuchsia-700 shadow-sm border border-pink-100">
                <i data-lucide="menu"></i>
            </button>
        </div>

        <!-- Hero Section -->
        <section id="hero" class="relative py-24 px-6 lg:px-16 glass-panel rounded-[2.5rem] mb-16 overflow-hidden shadow-xl border-t border-white">
            <div class="absolute top-[-20%] right-[-10%] w-[30rem] h-[30rem] bg-gradient-to-br from-fuchsia-200 to-rose-200 rounded-full blur-[80px] -z-10 opacity-60"></div>
            
            <div class="max-w-5xl relative z-10">
                <div class="inline-flex items-center gap-3 py-2 px-5 rounded-full bg-white/60 border border-white/50 text-fuchsia-700 text-base font-bold mb-8 backdrop-blur-md shadow-sm">
                    <span class="relative flex h-3 w-3">
                      <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-fuchsia-400 opacity-75"></span>
                      <span class="relative inline-flex rounded-full h-3 w-3 bg-fuchsia-500"></span>
                    </span>
                    Quy Trình Chuẩn Hóa 2025
                </div>
                
                <h1 class="text-6xl lg:text-8xl font-extrabold text-slate-900 mb-8 leading-tight tracking-tight">
                    Quy Trình Tạo Lập <br> 
                    <span class="text-gradient-main">Nội Dung Số Trong Dạy Học</span>
                </h1>
                
                <p class="text-2xl lg:text-3xl text-slate-600 mb-12 leading-relaxed max-w-4xl font-light">
                    Hướng dẫn toàn diện từ việc phân tích mục tiêu sư phạm đến ứng dụng <strong class="text-fuchsia-700 font-bold bg-fuchsia-50 px-2 py-1 rounded-lg border border-fuchsia-100">Trí tuệ nhân tạo (AI)</strong> để tạo ra sản phẩm E-learning chất lượng cao.
                </p>
                
                <div class="flex flex-wrap gap-6">
                    <a href="#phase1" class="group relative px-10 py-5 bg-fuchsia-600 rounded-2xl text-white font-bold text-lg overflow-hidden shadow-lg shadow-fuchsia-500/30 transition-all hover:scale-105 hover:shadow-fuchsia-500/50 hover:bg-fuchsia-700">
                        <span class="flex items-center gap-3">Bắt đầu ngay <i data-lucide="arrow-right" class="w-6 h-6"></i></span>
                    </a>
                    <a href="#phase3" class="px-10 py-5 rounded-2xl bg-white border border-slate-200 hover:bg-slate-50 text-slate-700 font-bold text-lg transition-all flex items-center gap-3 shadow-sm hover:shadow-md hover:text-amber-600">
                        Xem phần AI <i data-lucide="sparkles" class="w-6 h-6 text-amber-500 fill-amber-500"></i>
                    </a>
                </div>
            </div>
        </section>

        <!-- Phase 1 -->
        <section id="phase1" class="mb-20">
            <div class="flex items-center gap-8 mb-12 pl-4">
                <div class="w-24 h-24 rounded-[2rem] bg-gradient-to-br from-rose-500 to-pink-600 text-white flex items-center justify-center text-5xl font-bold shadow-2xl shadow-rose-500/30 border-4 border-white/50">01</div>
                <div>
                    <h2 class="text-5xl font-bold text-slate-900 mb-2">Phân Tích</h2>
                    <p class="text-2xl text-rose-500 font-medium">Mục Tiêu & Đối Tượng</p>
                </div>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Step 1 Card -->
                <div class="glass-card p-10 rounded-[2rem]">
                    <div class="w-20 h-20 bg-rose-100 text-rose-600 rounded-3xl flex items-center justify-center mb-8 shadow-inner"><i data-lucide="crosshair" class="w-10 h-10"></i></div>
                    <h3 class="font-bold text-3xl mb-4 text-slate-800">Bước 1: Mục Tiêu SMART</h3>
                    <p class="text-lg text-slate-600 mb-8 leading-relaxed">Xác định mục tiêu nội dung số theo nguyên tắc SMART:</p>
                    <ul class="space-y-4 text-base text-slate-600 font-medium">
                        <li class="flex items-center gap-4"><span class="w-3 h-3 bg-rose-500 rounded-full shadow-lg shadow-rose-300"></span>Specific (Cụ thể)</li>
                        <li class="flex items-center gap-4"><span class="w-3 h-3 bg-rose-500 rounded-full shadow-lg shadow-rose-300"></span>Measurable (Đo lường được)</li>
                        <li class="flex items-center gap-4"><span class="w-3 h-3 bg-rose-500 rounded-full shadow-lg shadow-rose-300"></span>Achievable (Khả thi)</li>
                        <li class="flex items-center gap-4"><span class="w-3 h-3 bg-rose-500 rounded-full shadow-lg shadow-rose-300"></span>Relevant (Liên quan)</li>
                        <li class="flex items-center gap-4"><span class="w-3 h-3 bg-rose-500 rounded-full shadow-lg shadow-rose-300"></span>Time-bound (Có thời hạn)</li>
                    </ul>
                </div>

                <!-- Step 2 Card -->
                <div class="glass-card p-10 rounded-[2rem]">
                    <div class="w-20 h-20 bg-rose-100 text-rose-600 rounded-3xl flex items-center justify-center mb-8 shadow-inner"><i data-lucide="user-search" class="w-10 h-10"></i></div>
                    <h3 class="font-bold text-3xl mb-4 text-slate-800">Bước 2: Phân Tích Đối Tượng</h3>
                    <p class="text-lg text-slate-600 mb-6">Xây dựng chân dung người học qua 3 yếu tố:</p>
                    <div class="space-y-5">
                        <div class="bg-white/60 p-5 rounded-2xl border border-white shadow-sm">
                            <h4 class="text-base font-bold text-rose-800 uppercase tracking-wide">Nhân Khẩu Học</h4>
                        </div>
                        <div class="bg-white/60 p-5 rounded-2xl border border-white shadow-sm">
                            <h4 class="text-base font-bold text-rose-800 uppercase tracking-wide">Tâm Lý Học</h4>
                            <p class="text-sm text-slate-500 mt-1">Thói quen sử dụng công nghệ, nhu cầu/hứng thú môn học</p>
                        </div>
                        <div class="bg-white/60 p-5 rounded-2xl border border-white shadow-sm">
                            <h4 class="text-base font-bold text-rose-800 uppercase tracking-wide">Thói Quen Số</h4>
                            <p class="text-sm text-slate-500 mt-1">Thời gian sử dụng, thiết bị</p>
                        </div>
                    </div>
                </div>

                <!-- Step 3 Card -->
                <div class="glass-card p-10 rounded-[2rem]">
                    <div class="w-20 h-20 bg-rose-100 text-rose-600 rounded-3xl flex items-center justify-center mb-8 shadow-inner"><i data-lucide="link-2" class="w-10 h-10"></i></div>
                    <h3 class="font-bold text-3xl mb-4 text-slate-800">Bước 3: Liên Kết Sư Phạm</h3>
                    <p class="text-xl text-slate-600 leading-relaxed mb-8">
                        Liên kết giữa mục tiêu – đối tượng để đảm bảo sự phù hợp giữa <strong class="text-rose-600 bg-rose-50 px-1 rounded">cái cần dạy</strong> và <strong class="text-rose-600 bg-rose-50 px-1 rounded">cái người học tiếp nhận được</strong>.
                    </p>
                    <div class="p-6 bg-gradient-to-r from-rose-50 to-pink-50 rounded-2xl border border-rose-100 text-rose-800 shadow-sm">
                        <strong class="block mb-2 text-rose-600 uppercase text-xs tracking-widest font-bold">KẾT QUẢ ĐẦU RA:</strong> 
                        Lựa chọn loại nội dung, định dạng, phương pháp và công cụ số phù hợp.
                    </div>
                </div>
            </div>
        </section>

        <!-- Phase 2 -->
        <section id="phase2" class="mb-20">
            <div class="flex items-center gap-8 mb-12 pl-4">
                <div class="w-24 h-24 rounded-[2rem] bg-gradient-to-br from-violet-500 to-purple-600 text-white flex items-center justify-center text-5xl font-bold shadow-2xl shadow-violet-500/30 border-4 border-white/50">02</div>
                <div>
                    <h2 class="text-5xl font-bold text-slate-900 mb-2">Lập Kế Hoạch</h2>
                    <p class="text-2xl text-violet-500 font-medium">Nội Dung Số</p>
                </div>
            </div>

            <div class="grid lg:grid-cols-12 gap-8">
                <!-- Step 1 -->
                <div class="lg:col-span-5 h-full">
                    <div class="glass-card p-10 rounded-[2rem] h-full border border-violet-100">
                        <h3 class="font-bold text-3xl text-violet-800 mb-8 flex items-center gap-4">
                            <i data-lucide="check-circle-2" class="w-8 h-8 text-violet-500 fill-violet-100"></i> Bước 1: Chọn Loại Học Liệu
                        </h3>
                        
                        <div class="space-y-8">
                            <!-- Group 1 -->
                            <div class="bg-violet-50 p-8 rounded-3xl border border-violet-100">
                                <h4 class="font-bold text-lg text-violet-900 mb-6 border-b-2 border-violet-200 pb-3">1. Căn cứ vào Mục Tiêu (YCCĐ)</h4>
                                <ul class="text-slate-700 space-y-6">
                                    <li>
                                        <span class="font-bold text-slate-900 block mb-2 text-lg">Hoạt động trong bài dạy</span> 
                                        Video mô phỏng quy trình/cơ chế, Infographic tuyên truyền.
                                        <div class="text-base text-violet-600 bg-white inline-block px-3 py-1 rounded-lg mt-2 shadow-sm border border-violet-100">💡 VD: Video mô phỏng</div>
                                    </li>
                                </ul>
                            </div>

                            <!-- Group 2 -->
                            <div class="bg-fuchsia-50 p-8 rounded-3xl border border-fuchsia-100">
                                <h4 class="font-bold text-lg text-fuchsia-900 mb-6 border-b-2 border-fuchsia-200 pb-3">2. Căn cứ vào Phương Pháp Dạy Học</h4>
                                <div class="grid gap-4">
                                    <div class="p-4 bg-white rounded-2xl text-base text-slate-600 shadow-sm"><strong class="text-fuchsia-700">Dạy học khám phá:</strong> Video mô phỏng, thí nghiệm...</div>
                                    <div class="p-4 bg-white rounded-2xl text-base text-slate-600 shadow-sm"><strong class="text-fuchsia-700">Dạy học dự án:</strong> Bài giảng E-learning hướng dẫn học tập...</div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Step 2 Table -->
                <div class="lg:col-span-7 h-full">
                    <div class="glass-card rounded-[2rem] overflow-hidden h-full flex flex-col border border-white">
                         <div class="p-8 bg-violet-50 border-b border-violet-100">
                            <h3 class="font-bold text-3xl text-violet-800 flex items-center gap-4">
                                <i data-lucide="table" class="w-8 h-8 text-violet-500"></i> Bước 2: Bảng Kế Hoạch
                            </h3>
                        </div>
                        <div class="overflow-x-auto flex-1 p-6">
                            <table class="w-full text-lg text-left h-full border-collapse">
                                <thead class="text-sm font-extrabold text-slate-400 uppercase tracking-wider">
                                    <tr>
                                        <th class="px-6 py-6 border-b border-slate-200">Hoạt Động</th>
                                        <th class="px-6 py-6 border-b border-slate-200">Mô Tả Chi Tiết</th>
                                        <th class="px-6 py-6 border-b border-slate-200">Kết Quả Đầu Ra</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-slate-100 text-slate-600">
                                    <tr class="hover:bg-violet-50/50 transition-colors">
                                        <td class="px-6 py-8 font-bold text-slate-900 align-top">Phân tích cấu trúc KHDH</td>
                                        <td class="px-6 py-8 text-base align-top leading-relaxed">Xác định: mục tiêu bài học, nội dung trọng tâm, năng lực cần phát triển, hình thức tổ chức.</td>
                                        <td class="px-6 py-8 align-top"><span class="bg-violet-100 text-violet-700 px-3 py-1.5 rounded-lg text-sm font-bold">Kế hoạch bài dạy</span></td>
                                    </tr>
                                    <tr class="hover:bg-violet-50/50 transition-colors">
                                        <td class="px-6 py-8 font-bold text-slate-900 align-top">Xác định vai trò nội dung số</td>
                                        <td class="px-6 py-8 text-base align-top">
                                            <ul class="list-disc list-inside space-y-2 text-slate-500">
                                                <li>Khởi động: Video, hình ảnh, câu hỏi gợi mở.</li>
                                                <li>Hình thành kiến thức: Mô phỏng, infographic, bài giảng tương tác.</li>
                                                <li>Luyện tập/Đánh giá: Quiz, trò chơi, bài tập trực tuyến.</li>
                                            </ul>
                                        </td>
                                        <td class="px-6 py-8 align-top"><span class="bg-violet-100 text-violet-700 px-3 py-1.5 rounded-lg text-sm font-bold">Tích hợp trong KHBD</span></td>
                                    </tr>
                                    <tr class="hover:bg-violet-50/50 transition-colors">
                                        <td class="px-6 py-8 font-bold text-slate-900 align-top">Phân bổ thời gian – nguồn lực – công cụ</td>
                                        <td class="px-6 py-8 text-base align-top leading-relaxed">Lập kế hoạch chi tiết: thời lượng, công cụ (Gemini, Canva, H5P...), người phụ trách.</td>
                                        <td class="px-6 py-8 align-top"><span class="bg-violet-100 text-violet-700 px-3 py-1.5 rounded-lg text-sm font-bold">Bảng kế hoạch chi tiết</span></td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Phase 3 -->
        <section id="phase3" class="mb-12 relative">
            <div class="flex items-center gap-8 mb-12 pl-4 relative z-10">
                <div class="w-24 h-24 rounded-[2rem] bg-gradient-to-br from-amber-500 to-orange-600 text-white flex items-center justify-center text-5xl font-bold shadow-2xl shadow-amber-500/30 border-4 border-white/50">03</div>
                <div>
                    <h2 class="text-5xl font-bold text-slate-900 mb-2">Sản Xuất Nội Dung Số</h2>
                    <p class="text-2xl text-amber-600 font-bold bg-amber-50 inline-block px-2 rounded-lg">Cộng tác: Người Dạy & AI</p>
                </div>
            </div>
            
            <div class="p-8 mb-16 glass-panel rounded-3xl border-l-8 border-amber-500 bg-white/70">
                <p class="text-slate-600 text-xl leading-relaxed">
                    Sản xuất là giai đoạn biến kế hoạch thành sản phẩm thực tế — chất lượng của giai đoạn này quyết định thành công của nội dung. 
                    Mục tiêu: Giúp người học tạo ra nội dung số có giá trị thực tiễn (học liệu số) đảm bảo tính khoa học, sư phạm và sáng tạo.
                </p>
            </div>

            <div class="space-y-16 relative">
                <!-- Vertical Line -->
                <div class="absolute left-[3rem] top-12 bottom-12 w-1 bg-gradient-to-b from-amber-300 via-slate-300 to-transparent hidden lg:block rounded-full"></div>

                <!-- Step 1 -->
                <div class="relative lg:pl-32 group">
                    <div class="hidden lg:flex absolute left-0 top-0 w-24 h-24 bg-white border-4 border-amber-200 rounded-[2rem] items-center justify-center font-bold text-3xl text-amber-600 z-10 shadow-lg">01</div>
                    
                    <div class="glass-card p-10 rounded-[2.5rem] border border-amber-100 bg-white/60">
                        <div class="flex items-center gap-6 mb-8">
                            <div class="p-4 bg-amber-100 rounded-2xl text-amber-600"><i data-lucide="upload-cloud" class="w-10 h-10"></i></div>
                            <h3 class="text-3xl font-bold text-slate-800">Số Hóa Đầu Vào & Sử Dụng Gemini Canvas</h3>
                        </div>
                        
                        <!-- Gemini Instructions -->
                        <div class="bg-slate-50 p-8 rounded-3xl border border-slate-200 shadow-inner mb-8">
                            <h4 class="text-amber-700 font-bold text-xl mb-8 flex items-center gap-4 pb-4 border-b border-slate-200">
                                <i data-lucide="monitor" class="w-6 h-6"></i> Hướng Dẫn Kích Hoạt Canvas
                            </h4>
                            <div class="grid md:grid-cols-2 gap-10">
                                <div>
                                    <h5 class="text-sm font-extrabold text-slate-400 uppercase mb-4 tracking-widest">1. Chuẩn Bị File</h5>
                                    <p class="text-slate-600 leading-relaxed text-lg bg-white p-4 rounded-xl border border-slate-100 shadow-sm">
                                        Sử dụng file KHBD định dạng <code class="text-fuchsia-600 bg-fuchsia-50 px-2 py-1 rounded font-bold border border-fuchsia-100">.docx</code> hoặc <code class="text-fuchsia-600 bg-fuchsia-50 px-2 py-1 rounded font-bold border border-fuchsia-100">.pdf</code> đã thiết kế ở giai đoạn 2. <br>
                                        <span class="text-sm text-slate-400 mt-3 block italic">⚠️ Đảm bảo file có cấu trúc rõ ràng (Mục tiêu, Hoạt động).</span>
                                    </p>
                                </div>
                                <div>
                                    <h5 class="text-sm font-extrabold text-slate-400 uppercase mb-4 tracking-widest">2. Thao Tác Mở Canvas</h5>
                                    <ul class="text-slate-600 space-y-5 text-lg">
                                        <li class="flex items-start gap-4">
                                            <span class="bg-slate-200 text-slate-600 w-7 h-7 rounded-full flex items-center justify-center text-xs font-bold shrink-0 mt-1">1</span>
                                            <span>Bấm vào biểu tượng <strong>Dấu cộng (+)</strong> để tải file lên.</span>
                                        </li>
                                        <li class="flex items-start gap-4">
                                            <span class="bg-slate-200 text-slate-600 w-7 h-7 rounded-full flex items-center justify-center text-xs font-bold shrink-0 mt-1">2</span>
                                            <span>Tìm và nhấn vào biểu tượng <strong>Công cụ</strong>, chọn mục <strong class="text-amber-600 bg-amber-100 px-2 rounded">Canvas</strong> để mở giao diện làm việc chia đôi màn hình.</span>
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Step 2 -->
                <div class="relative lg:pl-32 group">
                    <div class="hidden lg:flex absolute left-0 top-0 w-24 h-24 bg-white border-4 border-amber-200 rounded-[2rem] items-center justify-center font-bold text-3xl text-slate-400 group-hover:text-amber-600 group-hover:border-amber-400 transition-all duration-300 z-10 shadow-lg">02</div>
                    
                    <div class="glass-card p-10 rounded-[2.5rem]">
                        <div class="flex items-center gap-6 mb-8">
                            <div class="p-4 bg-amber-100 rounded-2xl text-amber-600"><i data-lucide="message-square-code" class="w-10 h-10"></i></div>
                            <h3 class="text-3xl font-bold text-slate-800">Kỹ Thuật Ra Lệnh & Chuyển Đổi Logic</h3>
                        </div>
                        
                        <div class="grid md:grid-cols-2 gap-8">
                            <div class="bg-white/70 p-8 rounded-3xl border border-white shadow-sm hover:shadow-md transition-shadow">
                                <span class="text-sm font-extrabold text-amber-600 uppercase tracking-widest block mb-6">Cơ Chế Xử Lý Của AI (Logic Mapping)</span>
                                <ul class="text-slate-600 space-y-5 text-lg">
                                    <li class="flex items-center gap-4 bg-slate-50 p-4 rounded-xl border border-slate-100"><i data-lucide="arrow-right" class="w-5 h-5 text-amber-500"></i> Mapping: Thảo luận nhóm → <strong class="text-slate-900">Form nhập liệu</strong></li>
                                    <li class="flex items-center gap-4 bg-slate-50 p-4 rounded-xl border border-slate-100"><i data-lucide="arrow-right" class="w-5 h-5 text-amber-500"></i> Gamification: Kiểm tra kiến thức → <strong class="text-slate-900">Quiz trắc nghiệm</strong></li>
                                    <li class="flex items-center gap-4 bg-slate-50 p-4 rounded-xl border border-slate-100"><i data-lucide="arrow-right" class="w-5 h-5 text-amber-500"></i> Visualization: Nội dung văn bản → <strong class="text-slate-900">Biểu đồ tương tác</strong></li>
                                </ul>
                            </div>
                            <div class="bg-slate-800 p-8 rounded-3xl border border-slate-700 flex flex-col justify-center text-white shadow-2xl">
                                <div class="text-sm text-slate-400 italic mb-4 flex items-center gap-2 font-medium"><i data-lucide="terminal" class="w-5 h-5"></i> Thao tác ra lệnh (Prompt):</div>
                                <div class="font-mono text-xl text-amber-300 leading-relaxed bg-black/30 p-6 rounded-2xl border border-amber-500/30">
                                    "Thiết kế elearning theo KHBD sau..."
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Step 3 -->
                <div class="relative lg:pl-32 group">
                    <div class="hidden lg:flex absolute left-0 top-0 w-24 h-24 bg-white border-4 border-amber-200 rounded-[2rem] items-center justify-center font-bold text-3xl text-slate-400 group-hover:text-amber-600 group-hover:border-amber-400 transition-all duration-300 z-10 shadow-lg">03</div>
                    
                    <div class="glass-card p-10 rounded-[2.5rem]">
                        <div class="flex items-center gap-6 mb-8">
                            <div class="p-4 bg-amber-100 rounded-2xl text-amber-600"><i data-lucide="eye" class="w-10 h-10"></i></div>
                            <h3 class="text-3xl font-bold text-slate-800">Tạo Sinh & Kiểm Duyệt Mã Nguồn</h3>
                        </div>
                        
                        <div class="flex flex-col md:flex-row gap-10 mb-10">
                            <div class="flex-1 bg-white/80 p-8 rounded-3xl border border-white shadow-sm">
                                <h4 class="font-bold text-slate-900 text-xl mb-6 flex items-center gap-4"><i data-lucide="cpu" class="w-6 h-6 text-purple-500"></i> Vai Trò Của AI (Thực Thi)</h4>
                                <p class="text-slate-600 text-lg leading-relaxed">Tự động hóa viết mã nguồn (Source Code) cho sản phẩm (ví dụ: ReactJS, CSS). Xử lý các logic phức tạp như chấm điểm trắc nghiệm, hiệu ứng chuyển trang.</p>
                            </div>
                            <div class="flex-1 bg-white/80 p-8 rounded-3xl border border-white shadow-sm">
                                <h4 class="font-bold text-slate-900 text-xl mb-6 flex items-center gap-4"><i data-lucide="user-check" class="w-6 h-6 text-blue-500"></i> Vai Trò Của Bạn (Kiểm Duyệt)</h4>
                                <ul class="text-slate-600 space-y-3 text-lg">
                                    <li class="flex items-center gap-3"><span class="w-2 h-2 bg-blue-500 rounded-full"></span><strong>Logic:</strong> Đáp ứng mục tiêu dạy học?</li>
                                    <li class="flex items-center gap-3"><span class="w-2 h-2 bg-blue-500 rounded-full"></span><strong>Giao diện:</strong> Màu sắc, bố cục phù hợp?</li>
                                    <li class="flex items-center gap-3"><span class="w-2 h-2 bg-blue-500 rounded-full"></span><strong>Sửa lỗi:</strong> Ra lệnh AI sửa lỗi (Debugging).</li>
                                </ul>
                            </div>
                        </div>

                         <!-- Preview Guide -->
                         <div class="bg-gradient-to-r from-slate-900 to-slate-800 p-8 rounded-3xl border border-slate-700 shadow-2xl text-white">
                            <h4 class="text-amber-400 font-bold text-xl mb-8 flex items-center gap-4 pb-6 border-b border-slate-700">
                                <i data-lucide="play-circle" class="w-7 h-7"></i> Chế Độ Xem Trước (Preview HTML)
                            </h4>
                            <div class="grid md:grid-cols-2 gap-10">
                                <div>
                                    <h5 class="text-sm font-extrabold text-slate-400 uppercase mb-4 tracking-widest">Khi Nào Xuất Hiện?</h5>
                                    <p class="text-lg text-slate-300 bg-white/10 p-4 rounded-xl border border-white/10 leading-relaxed">Sau khi bạn ra lệnh tạo E-learning (ở Bước 2) và AI trả về mã nguồn (Code).</p>
                                </div>
                                <div>
                                    <h5 class="text-sm font-extrabold text-slate-400 uppercase mb-4 tracking-widest">Thao Tác</h5>
                                    <ul class="text-lg text-slate-300 space-y-4">
                                        <li class="flex items-start gap-4">
                                            <i data-lucide="check" class="w-5 h-5 text-amber-500 shrink-0 mt-1"></i>
                                            <span>AI hiển thị khối mã nguồn.</span>
                                        </li>
                                        <li class="flex items-start gap-4">
                                            <i data-lucide="check" class="w-5 h-5 text-amber-500 shrink-0 mt-1"></i>
                                            <span>Tìm nút <strong class="text-slate-900 bg-white px-2 py-0.5 rounded text-sm font-bold shadow-lg">Show Preview</strong> hoặc <strong class="text-slate-900 bg-white px-2 py-0.5 rounded text-sm font-bold shadow-lg">Xem trước</strong>.</span>
                                        </li>
                                        <li class="flex items-start gap-4">
                                            <i data-lucide="check" class="w-5 h-5 text-amber-500 shrink-0 mt-1"></i>
                                            <span>Bấm để xem giao diện web chạy thực tế ngay lập tức.</span>
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Step 4 -->
                <div class="relative lg:pl-32 group">
                    <div class="hidden lg:flex absolute left-0 top-0 w-24 h-24 bg-white border-4 border-amber-200 rounded-[2rem] items-center justify-center font-bold text-3xl text-slate-400 group-hover:text-amber-600 group-hover:border-amber-400 transition-all duration-300 z-10 shadow-lg">04</div>
                    
                    <div class="glass-card p-10 rounded-[2.5rem]">
                        <div class="flex items-center gap-6 mb-8">
                            <div class="p-4 bg-amber-100 rounded-2xl text-amber-600"><i data-lucide="package-check" class="w-10 h-10"></i></div>
                            <h3 class="text-3xl font-bold text-slate-800">Đóng Gói & Triển Khai</h3>
                        </div>
                        <p class="text-slate-600 text-xl mb-10">Biến mã lệnh thành giao diện trực quan để người học truy cập.</p>
                        <div class="flex flex-col md:flex-row gap-8">
                            <div class="flex-1 p-8 rounded-3xl bg-amber-50 border border-amber-100 hover:border-amber-300 transition-all cursor-pointer group/card shadow-sm">
                                <h5 class="font-bold text-amber-600 text-xl mb-3 flex items-center gap-3"><i data-lucide="zap" class="w-6 h-6"></i> Phương án 1: Cách Nhanh</h5>
                                <p class="text-base text-slate-500 mb-3">Kiểm thử nhanh (Rapid Prototyping).</p>
                                <div class="text-lg text-slate-800 font-medium">
                                    Sử dụng nút <strong>"Chia sẻ"</strong> trên Canvas: <br>
                                    <span class="text-sm font-normal text-slate-600 mt-1 block">Bấm <strong>Chia sẻ</strong> &rarr; Sao chép link &rarr; Dán vào thanh địa chỉ trình duyệt.</span>
                                </div>
                            </div>
                            <div class="flex-1 p-8 rounded-3xl bg-blue-50 border border-blue-100 hover:border-blue-300 transition-all cursor-pointer group/card shadow-sm">
                                <h5 class="font-bold text-blue-600 text-xl mb-3 flex items-center gap-3"><i data-lucide="hard-drive" class="w-6 h-6"></i> Phương án 2: Chuyên Nghiệp</h5>
                                <p class="text-base text-slate-500 mb-3">Triển khai diện rộng (Production).</p>
                                <div class="text-lg text-slate-800 font-medium">Lưu file <strong>.html</strong> chạy offline hoặc đưa lên Website trường (Vercel/Netlify).</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <script>
        lucide.createIcons();
        
        // Add scroll spy to update active link
        window.addEventListener('scroll', () => {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('.nav-link');
            
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                if (pageYOffset >= sectionTop - 150) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('bg-white/80', 'border-l-4', 'border-fuchsia-500', 'text-slate-900', 'shadow-md');
                link.classList.add('text-fuchsia-700');
                if (link.getAttribute('href').includes(current)) {
                    link.classList.add('bg-white/80', 'border-l-4', 'border-fuchsia-500', 'text-slate-900', 'shadow-md');
                    link.classList.remove('text-fuchsia-700');
                }
            });
        });
    </script>
</body>
</html>
