<!DOCTYPE html>
<html lang="vi" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>K37B - Lớp 7B | Cuốn Nhật Ký Thanh Xuân</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Nunito:wght@400;500;600;700&family=Playfair+Display:ital,wght@0,400;0,600;0,700;0,900;1,400;1,600&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Nunito', 'sans-serif'],
                        serif: ['Playfair Display', 'serif'],
                        handwriting: ['Dancing Script', 'cursive'],
                    },
                    colors: {
                        paper: '#fdfbf7', // Màu giấy trắng kem
                        paperDark: '#f4ece6', // Giấy sẫm màu
                        ink: '#2c2925', // Màu mực đen
                        inkLight: '#57534e', // Mực nhạt
                        gold: '#b68d40', // Màu vàng đồng (Bookmark/Accent)
                        goldLight: '#dfc282',
                    }
                }
            }
        }
    </script>

    <style>
        /* Nền giấy tinh tế hiện đại */
        body {
            background-color: #fdfbf7;
            background-image: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.8' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100' height='100' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
            color: #2c2925;
            overflow-x: hidden;
        }

        /* Khung viền tạp chí cho màn hình chính */
        .magazine-frame {
            position: absolute;
            top: 24px;
            left: 24px;
            right: 24px;
            bottom: 24px;
            border: 1px solid rgba(255,255,255,0.3);
            pointer-events: none;
            z-index: 15;
            border-radius: 4px;
        }
        .magazine-frame::before, .magazine-frame::after {
            content: '';
            position: absolute;
            width: 1px;
            height: 40px;
            background: #dfc282;
            left: 50%;
            transform: translateX(-50%);
        }
        .magazine-frame::before { top: 0; }
        .magazine-frame::after { bottom: 0; }

        /* Chữ mờ nghệ thuật (Watermark) */
        .watermark {
            position: absolute;
            font-family: 'Playfair Display', serif;
            font-weight: 900;
            color: rgba(44, 41, 37, 0.03);
            user-select: none;
            pointer-events: none;
            line-height: 1;
            white-space: nowrap;
            z-index: 0;
        }

        /* Hiệu ứng Highlight đoạn văn */
        .text-highlight {
            background: linear-gradient(to right, rgba(182, 141, 64, 0.3) 50%, transparent 50%);
            background-size: 200% 100%;
            background-position: 100% 0;
            transition: background-position 0.5s ease;
        }
        .text-highlight:hover {
            background-position: 0 0;
        }

        /* Khung thẻ hiện đại pha nét tạp chí */
        .editorial-card {
            background: #ffffff;
            border: 1px solid rgba(44, 41, 37, 0.08);
            box-shadow: 0 4px 15px rgba(0,0,0,0.02);
            transition: all 0.4s ease;
            position: relative;
        }
        /* Viền vàng nổi lên khi hover */
        .editorial-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: #b68d40;
            transform: scaleX(0);
            transition: transform 0.4s ease;
            transform-origin: left;
        }
        .editorial-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.06);
            border-color: rgba(182, 141, 64, 0.3);
        }
        .editorial-card:hover::before {
            transform: scaleX(1);
        }

        /* Hiệu ứng khung ảnh Polaroid sạch sẽ */
        .modern-polaroid {
            background: #ffffff;
            padding: 12px 12px 45px 12px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.04);
            border: 1px solid rgba(0,0,0,0.05);
            transition: all 0.5s ease;
            break-inside: avoid;
            position: relative;
        }
        /* Đinh ghim ảo (Trang trí) */
        .modern-polaroid::before {
            content: '';
            position: absolute;
            top: 6px;
            left: 50%;
            transform: translateX(-50%);
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background: #b68d40;
            box-shadow: 0 2px 4px rgba(0,0,0,0.2), inset 1px 1px 2px rgba(255,255,255,0.5);
            opacity: 0.8;
            z-index: 10;
        }
        .modern-polaroid:hover {
            transform: translateY(-8px) scale(1.01);
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            border-color: rgba(182, 141, 64, 0.2);
        }

        /* Drop Cap hiện đại */
        .drop-cap::first-letter {
            float: left;
            font-family: 'Playfair Display', serif;
            font-size: 4.5rem;
            line-height: 0.8;
            padding-right: 0.6rem;
            padding-top: 0.2rem;
            color: #b68d40;
            font-weight: 900;
        }

        /* Dấu gạch phân cách nghệ thuật */
        .ornament-divider {
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 2rem 0;
            opacity: 0.6;
        }
        .ornament-divider::before, .ornament-divider::after {
            content: '';
            height: 1px;
            width: 50px;
            background-color: #b68d40;
        }
        .ornament-divider i {
            margin: 0 1rem;
            color: #b68d40;
            font-size: 0.6rem;
            transform: rotate(45deg);
        }

        /* Hiệu ứng xuất hiện mượt mà */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 1s cubic-bezier(0.25, 0.8, 0.25, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Slideshow mượt mà */
        .slide {
            position: absolute;
            inset: 0;
            opacity: 0;
            transition: opacity 2s ease-in-out, transform 8s linear;
            background-size: cover;
            background-position: center;
            transform: scale(1.1);
        }
        .slide.active {
            opacity: 1;
            transform: scale(1);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: #f4ece6; }
        ::-webkit-scrollbar-thumb { background: #b68d40; border-radius: 10px; }
    </style>
</head>
<body class="font-sans antialiased relative selection:bg-gold selection:text-white">

    <!-- THANH ĐIỀU HƯỚNG HIỆN ĐẠI -->
    <nav class="fixed w-full z-[100] transition-all duration-500 py-6" id="navbar">
        <div class="max-w-7xl mx-auto px-6 lg:px-12">
            <div class="flex justify-between items-center pb-4 transition-all duration-300" id="nav-border">
                <div class="flex items-center gap-4 cursor-pointer group" onclick="window.scrollTo(0,0)">
                    
                    <!-- LOGO MỚI THIẾT KẾ CHO 7B -->
                    <div class="relative w-11 h-11 flex items-center justify-center">
                        <!-- Hình thoi xoay -->
                        <div id="nav-logo-diamond" class="absolute inset-0 border-[1.5px] border-white rotate-45 group-hover:rotate-90 transition-all duration-700 ease-in-out"></div>
                        <!-- Vòng tròn bao ngoài -->
                        <div id="nav-logo-circle" class="absolute inset-[-4px] border border-white/50 rounded-full scale-90 group-hover:scale-105 transition-all duration-700 ease-in-out"></div>
                        <!-- Chữ 7B -->
                        <span id="nav-logo-text" class="font-serif font-bold text-lg text-white z-10 transition-colors duration-500">7B</span>
                    </div>

                    <div class="flex flex-col ml-1">
                        <!-- Bỏ chữ "Anh Sơn" -->
                        <span class="font-serif font-bold text-2xl text-white tracking-widest leading-none uppercase transition-colors" id="nav-brand">K37B</span>
                        <span class="text-[10px] text-goldLight font-bold uppercase tracking-[0.2em] mt-1.5 transition-colors" id="nav-sub">Chương Nhạc Thanh Xuân</span>
                    </div>
                </div>
                
                <div class="hidden md:flex items-center space-x-12">
                    <a href="#home" class="nav-link text-white/90 text-sm uppercase tracking-widest font-semibold hover:text-gold transition-colors relative">Trang Bìa</a>
                    <a href="#about" class="nav-link text-white/90 text-sm uppercase tracking-widest font-semibold hover:text-gold transition-colors relative">Lời Tựa</a>
                    <a href="#members" class="nav-link text-white/90 text-sm uppercase tracking-widest font-semibold hover:text-gold transition-colors relative">Nhân Vật</a>
                    <a href="#timeline" class="nav-link text-white/90 text-sm uppercase tracking-widest font-semibold hover:text-gold transition-colors relative">Hành Trình</a>
                    <a href="#gallery" class="nav-link text-white/90 text-sm uppercase tracking-widest font-semibold hover:text-gold transition-colors relative">Ký Ức</a>
                </div>

                <button id="mobile-menu-btn" class="md:hidden text-white text-2xl focus:outline-none transition-colors">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>
        
        <div id="mobile-overlay" class="hidden fixed inset-0 bg-ink/80 z-[-1] backdrop-blur-sm" onclick="toggleMobileMenu()"></div>
        <div id="mobile-menu" class="hidden md:hidden bg-paper absolute top-full left-0 w-full shadow-2xl py-8 flex flex-col items-center space-y-6 text-ink font-serif text-lg border-b-4 border-gold">
            <a href="#home" onclick="toggleMobileMenu()">Trang Bìa</a>
            <a href="#about" onclick="toggleMobileMenu()">Lời Tựa</a>
            <a href="#members" onclick="toggleMobileMenu()">Nhân Vật</a>
            <a href="#timeline" onclick="toggleMobileMenu()">Hành Trình</a>
            <a href="#gallery" onclick="toggleMobileMenu()">Ký Ức</a>
        </div>
    </nav>

    <!-- TRANG CHỦ (SLIDESHOW HIỆN ĐẠI) -->
    <section id="home" class="relative h-screen flex items-center justify-center overflow-hidden">
        <!-- Khung trang trí giả lập bìa tạp chí -->
        <div class="magazine-frame"></div>

        <div class="slideshow-container absolute inset-0 z-0">
            <div class="slide active" style="background-image: url('image_27c6e5.jpg');"></div>
            <div class="slide" style="background-image: url('https://images.unsplash.com/photo-1525921429624-479b6a26d84d?auto=format&fit=crop&w=1920&q=80');"></div>
            <div class="slide" style="background-image: url('https://images.unsplash.com/photo-1497633762265-9d179a990aa6?auto=format&fit=crop&w=1920&q=80');"></div>
        </div>

        <!-- Lớp phủ tối mờ để chữ trắng nổi bật -->
        <div class="absolute inset-0 z-10 bg-gradient-to-b from-ink/70 via-ink/40 to-ink/90"></div>

        <div class="relative z-20 text-center px-4 max-w-4xl mt-16">
            <span class="font-handwriting text-3xl md:text-5xl text-gold mb-4 block opacity-90">Chương một...</span>
            <h1 class="text-6xl md:text-8xl font-serif font-black text-white mb-6 leading-[0.9] tracking-tighter uppercase drop-shadow-2xl">
                Tập Thể <br><span class="italic text-transparent bg-clip-text bg-gradient-to-r from-goldLight to-gold">Lớp 7B</span>
            </h1>
            
            <p class="text-xs md:text-sm font-bold uppercase tracking-[0.4em] text-white/70 mb-10 border-y border-white/20 py-3 inline-block">Trường THCS Anh Sơn • Niên khóa K37B</p>
            
            <div class="h-10 mb-8">
                <p class="text-lg md:text-2xl text-white/90 font-medium italic drop-shadow-md" id="typewriter"></p>
            </div>
            
            <div class="flex flex-wrap justify-center gap-6 mt-12">
                <a href="#about" class="px-10 py-4 bg-gold text-white font-bold uppercase tracking-widest text-xs hover:bg-white hover:text-ink transition-all duration-300 shadow-[0_0_20px_rgba(182,141,64,0.4)]">
                    Đọc Tiếp Hành Trình
                </a>
            </div>
        </div>

        <div class="absolute bottom-10 z-20 animate-bounce cursor-pointer" onclick="document.getElementById('about').scrollIntoView({behavior: 'smooth'})">
            <i class="fas fa-chevron-down text-white/40 text-2xl hover:text-gold transition-colors"></i>
        </div>
    </section>

    <!-- LỜI TỰA (GIỚI THIỆU & THỐNG KÊ GRID) -->
    <section id="about" class="py-32 relative overflow-hidden">
        <!-- Chữ chìm trang trí -->
        <div class="watermark top-10 -left-10 text-[12rem] md:text-[20rem]">7B</div>
        <div class="watermark bottom-10 -right-10 text-[10rem] md:text-[15rem] text-gold/5">K37B</div>

        <div class="max-w-7xl mx-auto px-6 lg:px-12 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
                <!-- Bên trái: Text Editorial -->
                <div class="reveal">
                    <p class="font-bold uppercase tracking-[0.3em] text-gold text-xs mb-4 flex items-center gap-2">
                        <span class="w-8 h-px bg-gold"></span> Lời Tựa
                    </p>
                    <h2 class="text-4xl md:text-5xl font-serif font-bold text-ink mb-8 leading-tight">Mảnh Ghép Vô Giá <br><span class="italic text-inkLight font-light">của thanh xuân</span></h2>
                    
                    <p class="text-lg text-inkLight leading-relaxed font-serif text-justify drop-cap mb-6">
                        Hơn cả một danh xưng của một lớp học, 7B là một <span class="text-highlight font-bold text-ink cursor-default">hệ sinh thái của tình bạn</span>, nơi 41 cá nhân kiệt xuất cùng nhau thêu dệt nên những trang hồi ký vô giá. Dưới vòm trời THCS Anh Sơn, chúng tôi không chỉ học cách tiếp nhận tri thức, mà còn học cách yêu thương và bảo bọc lẫn nhau qua những thăng trầm của tuổi học trò.
                    </p>
                    
                    <div class="ornament-divider">
                        <i class="fas fa-square"></i>
                    </div>

                    <div class="pl-6 border-l-[3px] border-gold italic text-ink font-medium text-lg md:text-xl font-serif">
                        "Mỗi ngày đến trường là một chương sách mới được viết lên bởi những tiếng cười giòn giã."
                    </div>
                </div>

                <!-- Bên phải: Grid Thống Kê -->
                <div class="grid grid-cols-2 gap-6 reveal relative">
                    <!-- Khung viền mờ chìm phía sau grid -->
                    <div class="absolute inset-0 border border-ink/5 translate-x-4 translate-y-4 -z-10 rounded-sm"></div>

                    <div class="editorial-card p-10 text-center rounded-sm">
                        <span class="block text-5xl font-serif font-black text-ink mb-2">41</span>
                        <span class="uppercase tracking-[0.2em] text-[10px] font-bold text-gold">Thành viên</span>
                    </div>
                    <div class="editorial-card p-10 text-center rounded-sm">
                        <span class="block text-5xl font-serif font-black text-ink mb-2">23</span>
                        <span class="uppercase tracking-[0.2em] text-[10px] font-bold text-gold">Nữ sinh</span>
                    </div>
                    <div class="editorial-card p-10 text-center rounded-sm">
                        <span class="block text-5xl font-serif font-black text-ink mb-2">18</span>
                        <span class="uppercase tracking-[0.2em] text-[10px] font-bold text-gold">Nam sinh</span>
                    </div>
                    <div class="editorial-card p-10 text-center rounded-sm flex items-center justify-center bg-ink text-paper hover:bg-gold transition-colors duration-500">
                        <div class="flex flex-col items-center">
                            <i class="fas fa-infinity text-4xl text-paper mb-2"></i>
                            <span class="uppercase tracking-[0.2em] text-[10px] font-bold text-paper/80">Tình Bạn</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- NHÂN VẬT (BAN CÁN SỰ GRID) -->
    <section id="members" class="py-32 bg-paperDark relative border-y border-ink/5">
        <!-- Text chìm -->
        <div class="watermark top-20 right-10 text-[8rem] text-ink/5">Lãnh Đạo</div>

        <div class="max-w-7xl mx-auto px-6 lg:px-12 relative z-10">
            <div class="text-center mb-20 reveal">
                <p class="font-bold uppercase tracking-[0.3em] text-gold text-xs mb-3 flex justify-center items-center gap-2">
                    <span class="w-6 h-px bg-gold"></span> Chương 2 <span class="w-6 h-px bg-gold"></span>
                </p>
                <h2 class="text-4xl md:text-5xl font-serif font-bold text-ink">Những Người Dẫn Đường</h2>
                <div class="ornament-divider">
                    <i class="fas fa-gem"></i>
                </div>
            </div>

            <!-- Lưới Ban cán sự (Cập nhật Tên đầy đủ) -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- Card 1 -->
                <div class="editorial-card p-8 flex flex-col items-center text-center reveal rounded-sm group">
                    <div class="w-16 h-16 border border-ink/10 rounded-full flex items-center justify-center text-gold text-xl mb-6 bg-paperDark group-hover:bg-gold group-hover:text-white group-hover:border-gold transition-all duration-500">
                        <i class="fas fa-crown"></i>
                    </div>
                    <p class="font-bold uppercase tracking-[0.2em] text-[10px] text-gold mb-2">Lớp Trưởng</p>
                    <h3 class="text-lg md:text-xl font-serif font-bold text-ink mb-4 leading-tight">Nguyễn Hà My</h3>
                    <p class="text-inkLight text-sm">Thủ lĩnh tài ba, ngọn hải đăng công tâm dẫn dắt 7B vững bước.</p>
                </div>

                <!-- Card 2 -->
                <div class="editorial-card p-8 flex flex-col items-center text-center reveal rounded-sm group" style="transition-delay: 100ms;">
                    <div class="w-16 h-16 border border-ink/10 rounded-full flex items-center justify-center text-gold text-xl mb-6 bg-paperDark group-hover:bg-gold group-hover:text-white group-hover:border-gold transition-all duration-500">
                        <i class="fas fa-star"></i>
                    </div>
                    <p class="font-bold uppercase tracking-[0.2em] text-[10px] text-gold mb-2">Đại Sứ Tín Nhiệm</p>
                    <h3 class="text-lg md:text-xl font-serif font-bold text-ink mb-4 leading-tight">Đặng Thị Linh Hương</h3>
                    <p class="text-inkLight text-sm">Cánh tay đắc lực, gánh vác trọng trách bằng sự tận tâm, chu đáo.</p>
                </div>

                <!-- Card 3 -->
                <div class="editorial-card p-8 flex flex-col items-center text-center reveal rounded-sm group" style="transition-delay: 200ms;">
                    <div class="w-16 h-16 border border-ink/10 rounded-full flex items-center justify-center text-gold text-xl mb-6 bg-paperDark group-hover:bg-gold group-hover:text-white group-hover:border-gold transition-all duration-500">
                        <i class="fas fa-book-open"></i>
                    </div>
                    <p class="font-bold uppercase tracking-[0.2em] text-[10px] text-gold mb-2">Học Tập</p>
                    <h3 class="text-lg md:text-xl font-serif font-bold text-ink mb-4 leading-tight">Nguyễn Văn Duy An</h3>
                    <p class="text-inkLight text-sm">Nhà thông thái, tấm gương sáng trong hành trình chinh phục tri thức.</p>
                </div>

                <!-- Card 4 -->
                <div class="editorial-card p-8 flex flex-col items-center text-center reveal rounded-sm group" style="transition-delay: 300ms;">
                    <div class="w-16 h-16 border border-ink/10 rounded-full flex items-center justify-center text-gold text-xl mb-6 bg-paperDark group-hover:bg-gold group-hover:text-white group-hover:border-gold transition-all duration-500">
                        <i class="fas fa-leaf"></i>
                    </div>
                    <p class="font-bold uppercase tracking-[0.2em] text-[10px] text-gold mb-2">Lao Động</p>
                    <h3 class="text-lg md:text-xl font-serif font-bold text-ink mb-4 leading-tight">Nguyễn Ngọc Huyền</h3>
                    <p class="text-inkLight text-sm">Sứ giả tận tâm, chăm lo cho không gian lớp luôn sạch đẹp, rạng rỡ.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- DÒNG THỜI GIAN (TIMELINE - BỔ SUNG MỚI) -->
    <section id="timeline" class="py-32 bg-paper relative border-b border-ink/5">
        <div class="max-w-4xl mx-auto px-6 lg:px-12 relative z-10">
            <div class="text-center mb-20 reveal">
                <p class="font-bold uppercase tracking-[0.3em] text-gold text-xs mb-3 flex items-center justify-center gap-2">
                    <span class="w-6 h-px bg-gold"></span> Chương 3 <span class="w-6 h-px bg-gold"></span>
                </p>
                <h2 class="text-4xl md:text-5xl font-serif font-bold text-ink">Dòng Thời Gian</h2>
                <div class="w-16 h-px bg-ink/20 mx-auto mt-6"></div>
            </div>

            <!-- Bố cục Dòng Thời Gian Dọc -->
            <div class="relative border-l border-ink/20 ml-3 md:ml-6 pl-8 md:pl-12 space-y-16">
                
                <!-- Cột mốc 1 -->
                <div class="relative reveal">
                    <!-- Nút ghim trên timeline -->
                    <div class="absolute -left-[41px] md:-left-[57px] top-1 w-5 h-5 bg-paper rounded-full border-4 border-gold"></div>
                    <p class="text-gold font-bold text-xs uppercase tracking-[0.2em] mb-2">Tháng 9/2023</p>
                    <h4 class="font-serif font-bold text-2xl text-ink mb-3">Tiếng Trống Khai Trường</h4>
                    <div class="editorial-card p-6 rounded-sm">
                        <p class="text-inkLight text-sm leading-relaxed">
                            Những bước chân bỡ ngỡ bước vào cánh cổng trường THCS Anh Sơn. 41 ánh mắt lạ lẫm nhưng tràn đầy tò mò và háo hức. Đó là khởi đầu cho một tình bạn tuyệt đẹp mang tên 7B.
                        </p>
                    </div>
                </div>

                <!-- Cột mốc 2 -->
                <div class="relative reveal">
                    <div class="absolute -left-[41px] md:-left-[57px] top-1 w-5 h-5 bg-paper rounded-full border-4 border-gold"></div>
                    <p class="text-gold font-bold text-xs uppercase tracking-[0.2em] mb-2">Tháng 11/2023</p>
                    <h4 class="font-serif font-bold text-2xl text-ink mb-3">Tri Ân Người Lái Đò</h4>
                    <div class="editorial-card p-6 rounded-sm">
                        <p class="text-inkLight text-sm leading-relaxed">
                            Cả lớp đã cùng nhau tập luyện chăm chỉ cho hội diễn văn nghệ. Những điệu múa có thể còn vụng về nhưng đong đầy tình cảm chân thành gửi gắm đến các thầy cô giáo nhân ngày 20/11.
                        </p>
                    </div>
                </div>

                <!-- Cột mốc 3 -->
                <div class="relative reveal">
                    <div class="absolute -left-[41px] md:-left-[57px] top-1 w-5 h-5 bg-paper rounded-full border-4 border-gold"></div>
                    <p class="text-gold font-bold text-xs uppercase tracking-[0.2em] mb-2">Tháng 3/2024</p>
                    <h4 class="font-serif font-bold text-2xl text-ink mb-3">Hội Trại Thanh Xuân</h4>
                    <div class="editorial-card p-6 rounded-sm">
                        <p class="text-inkLight text-sm leading-relaxed">
                            Một kỷ niệm rực rỡ bên ánh lửa trại mùa xuân. Những trò chơi tập thể, những tràng cười sảng khoái đã giúp tinh thần đoàn kết của đại gia đình 7B được thắt chặt hơn bao giờ hết.
                        </p>
                    </div>
                </div>

            </div>
            
            <div class="text-center mt-16 reveal">
                <p class="font-handwriting text-2xl text-gold italic">... và câu chuyện vẫn đang được viết tiếp!</p>
            </div>
        </div>
    </section>

    <!-- KÝ ỨC (MASONRY GALLERY HIỆN ĐẠI) -->
    <section id="gallery" class="py-32 bg-paperDark relative">
        <div class="watermark bottom-20 left-10 text-[6rem] text-gold/5">Kỷ Niệm</div>

        <div class="max-w-7xl mx-auto px-6 lg:px-12 relative z-10">
            <div class="flex flex-col md:flex-row justify-between items-end mb-16 reveal border-b border-ink/10 pb-6">
                <div>
                    <h4 class="font-bold tracking-[0.3em] uppercase text-gold text-xs mb-3 flex items-center gap-2">
                        <span class="w-8 h-px bg-gold"></span> Chương Cuối
                    </h4>
                    <h2 class="text-4xl md:text-5xl font-serif font-bold text-ink">Tập Ảnh Thanh Xuân</h2>
                </div>
                <p class="text-inkLight font-handwriting text-2xl mt-4 md:mt-0 opacity-80">Lưu giữ nụ cười vĩnh cửu...</p>
            </div>

            <!-- Bố cục dạng Lưới (Masonry) ngay ngắn -->
            <div class="columns-1 sm:columns-2 lg:columns-3 gap-8 space-y-8 reveal">
                
                <!-- Khung ảnh 1 (Ảnh upload của người dùng) -->
                <div class="modern-polaroid group">
                    <div class="overflow-hidden relative">
                        <img src="image_27c6e5.jpg" class="w-full object-cover transition-transform duration-700 group-hover:scale-105" alt="Tập thể lớp">
                        <div class="absolute inset-0 bg-ink/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
                    </div>
                    <p class="font-handwriting text-3xl text-center mt-6 text-ink font-bold group-hover:text-gold transition-colors">Đại gia đình 7B</p>
                    <p class="font-sans text-[10px] tracking-widest uppercase text-center mt-2 text-inkLight/60">Khoảnh khắc đáng nhớ</p>
                </div>

                <!-- Khung ảnh 2 -->
                <div class="modern-polaroid group">
                    <div class="overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1511629091441-ee46146481b6?auto=format&fit=crop&w=600&q=80" class="w-full object-cover transition-transform duration-700 group-hover:scale-105" alt="Góc học tập">
                    </div>
                    <p class="font-sans text-sm font-bold tracking-[0.2em] uppercase text-center mt-6 text-ink">Góc tri thức</p>
                </div>

                <!-- Khung ảnh 3 -->
                <div class="modern-polaroid group">
                    <div class="overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1523240795612-9a054b0db644?auto=format&fit=crop&w=600&q=80" class="w-full object-cover transition-transform duration-700 group-hover:scale-105" alt="Nụ cười">
                    </div>
                    <p class="font-sans text-sm font-bold tracking-[0.2em] uppercase text-center mt-6 text-ink">Niềm vui</p>
                </div>

                <!-- Khung ảnh 4 -->
                <div class="modern-polaroid group">
                    <div class="overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1588072432836-e10032774350?auto=format&fit=crop&w=600&q=80" class="w-full object-cover transition-transform duration-700 group-hover:scale-105" alt="Lớp học">
                    </div>
                    <p class="font-sans text-sm font-bold tracking-[0.2em] uppercase text-center mt-6 text-ink">Phòng học</p>
                </div>

            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer class="bg-ink text-paper py-24 relative border-t border-gold/30">
        <div class="max-w-7xl mx-auto px-6 lg:px-12 grid grid-cols-1 md:grid-cols-3 gap-12 text-center md:text-left relative z-10 items-center">
            <div>
                <div class="w-12 h-12 border border-gold/50 mx-auto md:mx-0 flex items-center justify-center text-gold font-serif font-bold text-2xl mb-6 bg-gold/5">
                    7B
                </div>
                <h3 class="font-serif font-bold text-3xl mb-2 text-gold tracking-widest uppercase">K37B - Tập thể 7B</h3>
                <p class="text-paper/50 font-serif italic text-sm">"Cuốn sách thanh xuân không có hồi kết."</p>
            </div>
            
            <div class="flex justify-center space-x-4">
                <a href="#" class="w-10 h-10 border border-paper/20 flex items-center justify-center hover:bg-gold hover:border-gold hover:text-ink transition-all rounded-full"><i class="fab fa-facebook-f"></i></a>
                <a href="#" class="w-10 h-10 border border-paper/20 flex items-center justify-center hover:bg-gold hover:border-gold hover:text-ink transition-all rounded-full"><i class="fab fa-instagram"></i></a>
                <a href="#" class="w-10 h-10 border border-paper/20 flex items-center justify-center hover:bg-gold hover:border-gold hover:text-ink transition-all rounded-full"><i class="fab fa-youtube"></i></a>
            </div>

            <div class="md:text-right uppercase tracking-[0.2em] text-[10px] text-paper/40">
                <p class="mb-2 font-bold text-gold/60">Xuất bản bởi Tập thể 7B</p>
                <p>© 2024 THCS Anh Sơn.</p>
            </div>
        </div>
    </footer>

    <!-- SCRIPTS -->
    <script>
        // Hiệu ứng Typewriter trên nền Slider
        const textArray = [
            "Viết tiếp những trang sử rạng rỡ...", 
            "Nơi mỗi cá tính là một vì tinh tú...", 
            "K37B Anh Sơn - Tự hào và Kiêu hãnh!"
        ];
        let textIndex = 0, charIndex = 0, isDeleting = false;
        const typewriterSpan = document.getElementById("typewriter");

        function typeWriter() {
            const currentText = textArray[textIndex];
            typewriterSpan.innerHTML = isDeleting ? currentText.substring(0, charIndex - 1) : currentText.substring(0, charIndex + 1);
            charIndex = isDeleting ? charIndex - 1 : charIndex + 1;
            
            let typeSpeed = isDeleting ? 30 : 60;
            
            if (!isDeleting && charIndex === currentText.length) { 
                isDeleting = true; 
                typeSpeed = 2500; 
            } else if (isDeleting && charIndex === 0) { 
                isDeleting = false; 
                textIndex = (textIndex + 1) % textArray.length; 
                typeSpeed = 500; 
            }
            setTimeout(typeWriter, typeSpeed);
        }
        setTimeout(typeWriter, 1000);

        // Chuyển slide
        let currentSlide = 0;
        const slides = document.querySelectorAll('.slide');
        function nextSlide() {
            slides[currentSlide].classList.remove('active');
            currentSlide = (currentSlide + 1) % slides.length;
            slides[currentSlide].classList.add('active');
        }
        setInterval(nextSlide, 7000);

        // Đổi màu Navbar thông minh khi cuộn (Từ nền tối sang sáng)
        window.addEventListener('scroll', () => {
            const nav = document.getElementById('navbar');
            const border = document.getElementById('nav-border');
            const brand = document.getElementById('nav-brand');
            const sub = document.getElementById('nav-sub');
            const links = document.querySelectorAll('.nav-link');
            const btn = document.getElementById('mobile-menu-btn');
            
            // Xử lý logo
            const diamond = document.getElementById('nav-logo-diamond');
            const circle = document.getElementById('nav-logo-circle');
            const logoText = document.getElementById('nav-logo-text');

            if (window.scrollY > 80) {
                nav.classList.add('bg-paper/95', 'backdrop-blur-md', 'shadow-sm', 'py-3');
                nav.classList.remove('py-6');
                border.classList.add('border-ink/10');
                
                // Đổi chữ sang đen
                brand.classList.replace('text-white', 'text-ink');
                sub.classList.replace('text-goldLight', 'text-gold');
                btn.classList.replace('text-white', 'text-ink');
                links.forEach(l => l.classList.replace('text-white/90', 'text-inkLight'));
                
                // Đổi logo sang đen/vàng
                diamond.classList.replace('border-white', 'border-gold');
                circle.classList.replace('border-white/50', 'border-ink/20');
                logoText.classList.replace('text-white', 'text-ink');

            } else {
                nav.classList.remove('bg-paper/95', 'shadow-sm', 'py-3', 'backdrop-blur-md');
                nav.classList.add('py-6');
                border.classList.remove('border-ink/10');
                
                // Trả chữ về trắng (để nổi trên ảnh Slider)
                brand.classList.replace('text-ink', 'text-white');
                sub.classList.replace('text-gold', 'text-goldLight');
                btn.classList.replace('text-ink', 'text-white');
                links.forEach(l => l.classList.replace('text-inkLight', 'text-white/90'));

                // Trả logo về trắng
                diamond.classList.replace('border-gold', 'border-white');
                circle.classList.replace('border-ink/20', 'border-white/50');
                logoText.classList.replace('text-ink', 'text-white');
            }
        });

        // Hưởng ứng cuộn (Reveal)
        function reveal() {
            document.querySelectorAll('.reveal').forEach(el => {
                if (el.getBoundingClientRect().top < window.innerHeight - 80) el.classList.add('active');
            });
        }
        window.addEventListener('scroll', reveal);
        reveal(); 

        // Mobile Menu
        function toggleMobileMenu() {
            document.getElementById('mobile-menu').classList.toggle('hidden');
            document.getElementById('mobile-overlay').classList.toggle('hidden');
        }
        document.getElementById('mobile-menu-btn').addEventListener('click', toggleMobileMenu);
    </script>
</body>
</html>
