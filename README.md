[Uploading index.html.html…]()
# my-website<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jelajah Benua Dunia - IPAS Kelas 6 MI/SD</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Fredoka & Lexend (Ramah Anak & Mudah Dibaca) -->
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;600;700&family=Lexend:wght@400;500;600;700&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        skyLight: '#E0F2FE',
                        skyPastel: '#38BDF8',
                        greenPastel: '#4ADE80',
                        yellowPastel: '#FACC15',
                        orangePastel: '#FB923C',
                        pinkPastel: '#F472B6',
                        purplePastel: '#C084FC',
                        cardBg: '#FFFFFF',
                    },
                    fontFamily: {
                        heading: ['Fredoka', 'sans-serif'],
                        body: ['Lexend', 'sans-serif'],
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Lexend', sans-serif;
            background-color: #F0F9FF;
            background-image: radial-gradient(#BAE6FD 1.5px, transparent 1.5px);
            background-size: 24px 24px;
        }
        h1, h2, h3, h4, .font-heading {
            font-family: 'Fredoka', cursive, sans-serif;
        }
        .custom-shadow {
            box-shadow: 0 10px 25px -5px rgba(14, 165, 233, 0.15), 0 8px 10px -6px rgba(14, 165, 233, 0.1);
        }
        .card-bounce:hover {
            transform: translateY(-6px) scale(1.02);
            transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
        }
        .gradient-banner {
            background: linear-gradient(135deg, #38BDF8 0%, #818CF8 100%);
        }
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #E0F2FE;
        }
        ::-webkit-scrollbar-thumb {
            background: #38BDF8;
            border-radius: 10px;
        }
    </style>
</head>
<body class="text-slate-800 min-h-screen flex flex-col">

    <!-- Header & Navigation Bar -->
    <header class="sticky top-0 z-40 bg-white/90 backdrop-blur-md border-b-4 border-skyPastel shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Logo & Title -->
                <div class="flex items-center space-x-3 cursor-pointer" onclick="switchTab('beranda')">
                    <div class="w-12 h-12 bg-yellowPastel rounded-2xl flex items-center justify-center text-2xl text-slate-800 shadow-md transform rotate-3 hover:rotate-0 transition-transform">
                        🌍
                    </div>
                    <div>
                        <h1 class="text-xl sm:text-2xl font-bold text-sky-600 leading-none">Jelajah Dunia</h1>
                        <span class="text-xs font-semibold text-orange-500 bg-orange-100 px-2 py-0.5 rounded-full inline-block mt-1">IPAS Kelas 6 MI/SD</span>
                    </div>
                </div>

                <!-- Navigation Tabs (Desktop) -->
                <nav class="hidden md:flex space-x-2">
                    <button onclick="switchTab('beranda')" id="nav-beranda" class="nav-btn px-4 py-2.5 rounded-2xl font-heading font-semibold text-sm transition-all flex items-center space-x-2 bg-sky-500 text-white shadow-md">
                        <i class="fa-solid fa-house"></i>
                        <span>Beranda</span>
                    </button>
                    <button onclick="switchTab('materi')" id="nav-materi" class="nav-btn px-4 py-2.5 rounded-2xl font-heading font-semibold text-sm transition-all flex items-center space-x-2 text-slate-600 hover:bg-sky-100">
                        <i class="fa-solid fa-book-open"></i>
                        <span>Materi Benua</span>
                    </button>
                    <button onclick="switchTab('peta')" id="nav-peta" class="nav-btn px-4 py-2.5 rounded-2xl font-heading font-semibold text-sm transition-all flex items-center space-x-2 text-slate-600 hover:bg-sky-100">
                        <i class="fa-solid fa-map-location-dot"></i>
                        <span>Peta Interaktif</span>
                    </button>
                    <button onclick="switchTab('kuis')" id="nav-kuis" class="nav-btn px-4 py-2.5 rounded-2xl font-heading font-semibold text-sm transition-all flex items-center space-x-2 text-slate-600 hover:bg-sky-100">
                        <i class="fa-solid fa-gamepad"></i>
                        <span>Kuis Interaktif</span>
                    </button>
                </nav>

                <!-- Mobile Menu Button -->
                <div class="md:hidden">
                    <button id="mobile-menu-btn" onclick="toggleMobileMenu()" class="p-2.5 rounded-xl bg-sky-100 text-sky-600 focus:outline-none">
                        <i class="fa-solid fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Navigation Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-white border-b border-sky-100 px-4 pt-2 pb-4 space-y-2">
            <button onclick="switchTab('beranda'); toggleMobileMenu()" class="w-full text-left px-4 py-3 rounded-xl font-heading font-semibold text-slate-700 hover:bg-sky-50 flex items-center space-x-3">
                <i class="fa-solid fa-house text-sky-500"></i><span>Beranda</span>
            </button>
            <button onclick="switchTab('materi'); toggleMobileMenu()" class="w-full text-left px-4 py-3 rounded-xl font-heading font-semibold text-slate-700 hover:bg-sky-50 flex items-center space-x-3">
                <i class="fa-solid fa-book-open text-emerald-500"></i><span>Materi Benua</span>
            </button>
            <button onclick="switchTab('peta'); toggleMobileMenu()" class="w-full text-left px-4 py-3 rounded-xl font-heading font-semibold text-slate-700 hover:bg-sky-50 flex items-center space-x-3">
                <i class="fa-solid fa-map-location-dot text-amber-500"></i><span>Peta Interaktif</span>
            </button>
            <button onclick="switchTab('kuis'); toggleMobileMenu()" class="w-full text-left px-4 py-3 rounded-xl font-heading font-semibold text-slate-700 hover:bg-sky-50 flex items-center space-x-3">
                <i class="fa-solid fa-gamepad text-purple-500"></i><span>Kuis Interaktif</span>
            </button>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-8">

        <!-- ================= BERANDA SECTION ================= -->
        <section id="tab-beranda" class="space-y-8 animate-fade-in">
            <!-- Hero Banner -->
            <div class="gradient-banner rounded-3xl p-6 sm:p-10 text-white shadow-xl relative overflow-hidden flex flex-col md:flex-row items-center justify-between">
                <div class="z-10 max-w-xl text-center md:text-left space-y-4">
                    <span class="bg-white/20 text-white font-heading px-3 py-1 rounded-full text-xs sm:text-sm tracking-wide font-semibold border border-white/30">
                        🚀 Petualangan Edukasi IPAS
                    </span>
                    <h2 class="text-3xl sm:text-5xl font-extrabold leading-tight">
                        Halo Penjelajah Cilik! 👋
                    </h2>
                    <p class="text-sky-50 text-base sm:text-lg leading-relaxed">
                        Mari keliling bumi dan temukan keunikan 7 benua luar biasa di dunia! Siapkan rasa ingin tahumu dan jadilah ahli geografi hebat!
                    </p>
                    <div class="pt-2 flex flex-wrap gap-3 justify-center md:justify-start">
                        <button onclick="switchTab('materi')" class="bg-yellowPastel text-slate-900 font-heading font-bold px-6 py-3 rounded-2xl shadow-lg hover:bg-yellow-300 transition-all transform hover:scale-105 active:scale-95 flex items-center space-x-2">
                            <span>Mulai Belajar</span>
                            <i class="fa-solid fa-arrow-right"></i>
                        </button>
                        <button onclick="switchTab('kuis')" class="bg-white/20 backdrop-blur-md text-white border border-white/40 font-heading font-bold px-6 py-3 rounded-2xl hover:bg-white/30 transition-all flex items-center space-x-2">
                            <i class="fa-solid fa-trophy"></i>
                            <span>Uji Kemampuan</span>
                        </button>
                    </div>
                </div>

                <!-- Mascot / Mascot Graphic -->
                <div class="mt-8 md:mt-0 relative flex justify-center">
                    <div class="w-48 h-48 sm:w-64 sm:h-64 bg-white/10 rounded-full flex items-center justify-center border-4 border-white/20 animate-pulse">
                        <span class="text-8xl sm:text-9xl filter drop-shadow-lg">🧭</span>
                    </div>
                </div>
            </div>

            <!-- Pengenalan Singkat: Apa itu Benua & Samudra? -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <!-- Kartu Benua -->
                <div class="bg-white p-6 sm:p-8 rounded-3xl border-2 border-sky-100 custom-shadow flex items-start space-x-5">
                    <div class="w-16 h-16 rounded-2xl bg-sky-100 text-sky-600 flex items-center justify-center text-3xl shrink-0">
                        🏔️
                    </div>
                    <div class="space-y-2">
                        <h3 class="text-2xl font-bold text-slate-800">Apa itu Benua?</h3>
                        <p class="text-slate-600 text-sm leading-relaxed">
                            <strong>Benua</strong> adalah hamparan daratan yang sangat luas di permukaan bumi. Di dalam benua terdapat berbagai negara, pegunungan, sungai, serta beragam flora dan fauna yang unik!
                        </p>
                    </div>
                </div>

                <!-- Kartu Samudra -->
                <div class="bg-white p-6 sm:p-8 rounded-3xl border-2 border-emerald-100 custom-shadow flex items-start space-x-5">
                    <div class="w-16 h-16 rounded-2xl bg-emerald-100 text-emerald-600 flex items-center justify-center text-3xl shrink-0">
                        🌊
                    </div>
                    <div class="space-y-2">
                        <h3 class="text-2xl font-bold text-slate-800">Apa itu Samudra?</h3>
                        <p class="text-slate-600 text-sm leading-relaxed">
                            <strong>Samudra</strong> adalah lautan garam yang sangat luas yang mengelilingi dan memisahkan benua-benua di bumi. Contohnya: Samudra Pasifik, Hindia, dan Atlantik.
                        </p>
                    </div>
                </div>
            </div>

            <!-- Ringkasan 7 Benua Quick Access -->
            <div>
                <div class="flex items-center justify-between mb-6">
                    <h3 class="text-2xl font-bold text-slate-800 flex items-center space-x-2">
                        <span>7 Benua Mengagumkan</span>
                        <span class="text-xs bg-sky-100 text-sky-600 px-3 py-1 rounded-full">Klik untuk detail</span>
                    </h3>
                </div>

                <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-7 gap-4" id="beranda-benua-grid">
                    <!-- Dynamic rendering via JS -->
                </div>
            </div>
        </section>

        <!-- ================= MATERI BENUA SECTION ================= -->
        <section id="tab-materi" class="hidden space-y-8">
            <div class="text-center max-w-2xl mx-auto space-y-2">
                <span class="text-sky-600 font-heading font-bold text-sm bg-sky-100 px-4 py-1.5 rounded-full">Buku Ensiklopedia Mini</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-800">Materi 7 Benua di Dunia</h2>
                <p class="text-slate-600 text-sm">Pelajari ciri khas, keunikan, serta ikon terkenal dari setiap benua dengan mudah!</p>
            </div>

            <!-- List Materi Benua -->
            <div class="space-y-8" id="materi-container">
                <!-- Populated via JavaScript -->
            </div>
        </section>

        <!-- ================= PETA INTERAKTIF SECTION ================= -->
        <section id="tab-peta" class="hidden space-y-6">
            <div class="text-center max-w-2xl mx-auto space-y-2">
                <span class="text-amber-600 font-heading font-bold text-sm bg-amber-100 px-4 py-1.5 rounded-full">Peta Dunia Ceria</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-800">Peta Benua Interaktif</h2>
                <p class="text-slate-600 text-sm">Klik pada kartu atau wilayah benua di bawah untuk membuka informasi cepat!</p>
            </div>

            <!-- Interactive Map Simulator Box -->
            <div class="bg-white p-6 sm:p-8 rounded-3xl border-2 border-sky-200 custom-shadow space-y-6">
                <!-- SVG World Map Graphic with Clickable Interactive Zones -->
                <div class="relative w-full bg-sky-100 rounded-2xl overflow-hidden p-4 border border-sky-200 flex flex-col items-center justify-center min-h-[320px] sm:min-h-[420px]">
                    <div class="absolute inset-0 opacity-10 pointer-events-none flex items-center justify-center text-9xl">
                        🌐
                    </div>
                    <p class="text-xs sm:text-sm font-semibold text-sky-700 bg-white/80 backdrop-blur-sm px-4 py-1.5 rounded-full mb-4 shadow-sm">
                        📍 Klik nama benua di bawah untuk melihat lokasinya pada peta!
                    </p>

                    <!-- Interactive Map Overlay Grid -->
                    <div class="w-full max-w-4xl grid grid-cols-2 sm:grid-cols-4 gap-3 z-10">
                        <button onclick="openContinentModal('asia')" class="p-3 bg-white hover:bg-amber-100 text-slate-800 font-heading font-bold rounded-2xl shadow-sm border border-amber-200 transition-all flex flex-col items-center hover:scale-105 text-xs sm:text-sm">
                            <span class="text-2xl mb-1">🌏</span>
                            <span>Benua Asia</span>
                        </button>
                        <button onclick="openContinentModal('amerika_utara')" class="p-3 bg-white hover:bg-rose-100 text-slate-800 font-heading font-bold rounded-2xl shadow-sm border border-rose-200 transition-all flex flex-col items-center hover:scale-105 text-xs sm:text-sm">
                            <span class="text-2xl mb-1">🗽</span>
                            <span>Amerika Utara</span>
                        </button>
                        <button onclick="openContinentModal('amerika_selatan')" class="p-3 bg-white hover:bg-emerald-100 text-slate-800 font-heading font-bold rounded-2xl shadow-sm border border-emerald-200 transition-all flex flex-col items-center hover:scale-105 text-xs sm:text-sm">
                            <span class="text-2xl mb-1">🦜</span>
                            <span>Amerika Selatan</span>
                        </button>
                        <button onclick="openContinentModal('eropa')" class="p-3 bg-white hover:bg-sky-100 text-slate-800 font-heading font-bold rounded-2xl shadow-sm border border-sky-200 transition-all flex flex-col items-center hover:scale-105 text-xs sm:text-sm">
                            <span class="text-2xl mb-1">🏰</span>
                            <span>Benua Eropa</span>
                        </button>
                        <button onclick="openContinentModal('afrika')" class="p-3 bg-white hover:bg-orange-100 text-slate-800 font-heading font-bold rounded-2xl shadow-sm border border-orange-200 transition-all flex flex-col items-center hover:scale-105 text-xs sm:text-sm">
                            <span class="text-2xl mb-1">🦁</span>
                            <span>Benua Afrika</span>
                        </button>
                        <button onclick="openContinentModal('australia')" class="p-3 bg-white hover:bg-purple-100 text-slate-800 font-heading font-bold rounded-2xl shadow-sm border border-purple-200 transition-all flex flex-col items-center hover:scale-105 text-xs sm:text-sm">
                            <span class="text-2xl mb-1">🦘</span>
                            <span>Benua Australia</span>
                        </button>
                        <button onclick="openContinentModal('antartika')" class="p-3 bg-white hover:bg-cyan-100 text-slate-800 font-heading font-bold rounded-2xl shadow-sm border border-cyan-200 transition-all flex flex-col items-center hover:scale-105 text-xs sm:text-sm col-span-2 sm:col-span-2">
                            <span class="text-2xl mb-1">🐧</span>
                            <span>Benua Antartika</span>
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- ================= KUIS INTERAKTIF SECTION ================= -->
        <section id="tab-kuis" class="hidden max-w-3xl mx-auto space-y-6">
            <!-- Header Kuis -->
            <div class="text-center space-y-2">
                <span class="text-purple-600 font-heading font-bold text-sm bg-purple-100 px-4 py-1.5 rounded-full">Uji Pemahaman</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-800">Kuis Penjelajah Dunia</h2>
                <p class="text-slate-600 text-sm">Jawab 10 pertanyaan seru dan dapatkan bintang penghargaan tertinggi!</p>
            </div>

            <!-- Quiz Main Card -->
            <div id="quiz-card" class="bg-white p-6 sm:p-10 rounded-3xl border-2 border-purple-100 custom-shadow relative">
                <!-- Progress & Score Header -->
                <div class="flex items-center justify-between border-b border-slate-100 pb-4 mb-6">
                    <div>
                        <span class="text-xs font-semibold text-purple-600 bg-purple-50 px-3 py-1 rounded-full uppercase tracking-wider">Pertanyaan</span>
                        <h4 id="quiz-progress-text" class="text-lg font-extrabold text-slate-800 mt-1">Soal 1 dari 10</h4>
                    </div>
                    <div class="text-right">
                        <span class="text-xs text-slate-400 font-semibold block">Skor Sementara</span>
                        <span id="quiz-score-badge" class="text-xl font-extrabold text-emerald-500">0 Poin</span>
                    </div>
                </div>

                <!-- Progress Bar -->
                <div class="w-full bg-slate-100 h-3 rounded-full overflow-hidden mb-6">
                    <div id="quiz-progress-bar" class="bg-purple-500 h-full w-10 transition-all duration-300"></div>
                </div>

                <!-- Question Text -->
                <div class="mb-6">
                    <h3 id="quiz-question" class="text-xl sm:text-2xl font-bold text-slate-800 leading-snug">
                        Memuat pertanyaan...
                    </h3>
                </div>

                <!-- Answer Options Grid -->
                <div id="quiz-options" class="grid grid-cols-1 gap-3">
                    <!-- Options populated via JS -->
                </div>

                <!-- Feedback Box (Shown after selecting an answer) -->
                <div id="quiz-feedback" class="hidden mt-6 p-4 rounded-2xl border text-sm space-y-1">
                    <div id="feedback-status" class="font-bold flex items-center space-x-2 text-base"></div>
                    <div id="feedback-explain" class="text-slate-600"></div>
                </div>

                <!-- Action Button -->
                <div class="mt-8 flex justify-end">
                    <button id="btn-next-question" onclick="nextQuestion()" class="hidden bg-purple-600 text-white font-heading font-bold px-6 py-3 rounded-2xl shadow-md hover:bg-purple-700 transition-all flex items-center space-x-2">
                        <span>Lanjut Soal Berikutnya</span>
                        <i class="fa-solid fa-arrow-right"></i>
                    </button>
                </div>
            </div>

            <!-- Quiz Result View (Hidden by default) -->
            <div id="quiz-result-card" class="hidden bg-white p-8 sm:p-12 rounded-3xl border-2 border-yellow-200 custom-shadow text-center space-y-6">
                <div class="w-24 h-24 bg-yellow-100 text-yellow-500 rounded-full flex items-center justify-center text-5xl mx-auto border-4 border-yellow-300 animate-bounce">
                    🏆
                </div>
                <div>
                    <h3 class="text-3xl font-extrabold text-slate-800">Kuis Selesai!</h3>
                    <p class="text-slate-500 text-sm mt-1">Luar biasa! Kamu telah menyelesaikan petualangan kuis.</p>
                </div>

                <!-- Stars Badge -->
                <div class="flex justify-center space-x-2 text-4xl" id="result-stars">
                    <span>⭐</span><span>⭐</span><span>⭐</span>
                </div>

                <!-- Final Score Box -->
                <div class="bg-slate-50 p-6 rounded-2xl border border-slate-200 max-w-sm mx-auto space-y-2">
                    <span class="text-xs font-semibold text-slate-400 uppercase">Total Skor Kamu</span>
                    <div id="final-score" class="text-5xl font-extrabold text-purple-600">100</div>
                    <p id="final-message" class="text-xs font-medium text-emerald-600 pt-2"></p>
                </div>

                <!-- Action Buttons -->
                <div class="flex flex-wrap justify-center gap-4 pt-4">
                    <button onclick="restartQuiz()" class="bg-purple-600 text-white font-heading font-bold px-6 py-3 rounded-2xl shadow-md hover:bg-purple-700 transition-all flex items-center space-x-2">
                        <i class="fa-solid fa-rotate-right"></i>
                        <span>Ulangi Kuis</span>
                    </button>
                    <button onclick="switchTab('materi')" class="bg-sky-500 text-white font-heading font-bold px-6 py-3 rounded-2xl shadow-md hover:bg-sky-600 transition-all flex items-center space-x-2">
                        <i class="fa-solid fa-book-open"></i>
                        <span>Baca Materi Lagi</span>
                    </button>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-white border-t border-sky-100 py-6 mt-12 text-center text-xs text-slate-500">
        <div class="max-w-7xl mx-auto px-4 space-y-2">
            <p class="font-semibold text-slate-600">Media Pembelajaran Interaktif IPAS Kelas 6 MI/SD &copy; Materi Benua-Benua di Dunia</p>
            <p class="text-slate-400">Didesain khusus untuk pembelajaran siswa sekolah dasar yang menyenangkan & interaktif 🎈</p>
        </div>
    </footer>

    <!-- POP-UP MODAL UNTUK DETAIL BENUA -->
    <div id="continent-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white w-full max-w-2xl rounded-3xl shadow-2xl overflow-hidden border-4 border-sky-200 animate-fade-in max-h-[90vh] flex flex-col">
            <!-- Modal Header -->
            <div id="modal-header-bg" class="p-6 text-white flex justify-between items-start relative">
                <div class="space-y-1 z-10">
                    <span id="modal-badge" class="bg-white/20 text-white px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wider border border-white/30">
                        Detail Benua
                    </span>
                    <h3 id="modal-title" class="text-2xl sm:text-3xl font-extrabold">Nama Benua</h3>
                </div>
                <button onclick="closeContinentModal()" class="w-10 h-10 bg-white/20 hover:bg-white/40 rounded-full flex items-center justify-center text-white text-lg transition-colors z-10">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <!-- Modal Body Scrollable -->
            <div class="p-6 overflow-y-auto space-y-6 text-slate-700 text-sm">
                <!-- Image Banner -->
                <div class="w-full h-48 rounded-2xl overflow-hidden shadow-inner bg-slate-100 relative">
                    <img id="modal-image" src="" alt="Gambar Benua" class="w-full h-full object-cover">
                </div>

                <!-- Deskripsi Utama -->
                <div>
                    <h4 class="font-heading font-bold text-slate-800 text-base mb-1">📌 Deskripsi & Keunikan</h4>
                    <p id="modal-description" class="leading-relaxed text-slate-600"></p>
                </div>

                <!-- Info Grid: Ikon, Flora/Fauna, Negara Populer -->
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <div class="bg-sky-50 p-4 rounded-2xl border border-sky-100">
                        <h5 class="font-bold text-sky-800 text-xs uppercase mb-2 flex items-center space-x-1">
                            <span>🏛️ Ikon & Landmark</span>
                        </h5>
                        <p id="modal-icons" class="text-slate-700 font-medium"></p>
                    </div>

                    <div class="bg-emerald-50 p-4 rounded-2xl border border-emerald-100">
                        <h5 class="font-bold text-emerald-800 text-xs uppercase mb-2 flex items-center space-x-1">
                            <span>🌿 Flora & Fauna Khas</span>
                        </h5>
                        <p id="modal-nature" class="text-slate-700 font-medium"></p>
                    </div>
                </div>

                <!-- Tahukah Kamu Box -->
                <div class="bg-amber-50 p-4 rounded-2xl border border-amber-200 flex items-start space-x-3">
                    <span class="text-2xl">💡</span>
                    <div>
                        <h5 class="font-heading font-bold text-amber-900 text-sm">Tahukah Kamu?</h5>
                        <p id="modal-fact" class="text-amber-800 text-xs leading-relaxed mt-0.5"></p>
                    </div>
                </div>
            </div>

            <!-- Modal Footer -->
            <div class="p-4 bg-slate-50 border-t border-slate-100 text-right">
                <button onclick="closeContinentModal()" class="bg-sky-500 text-white font-heading font-bold px-6 py-2.5 rounded-xl hover:bg-sky-600 transition-colors">
                    Tutup
                </button>
            </div>
        </div>
    </div>


    <!-- ================= JAVASCRIPT LOGIC ================= -->
    <script>
        // DATA BENUA LENGKAP
        const continentsData = {
            asia: {
                id: 'asia',
                name: 'Benua Asia',
                color: 'from-amber-400 to-orange-500',
                btnColor: 'bg-amber-500 hover:bg-amber-600',
                badgeBg: 'bg-amber-100 text-amber-800',
                tag: 'Benua Terbesar',
                emoji: '🌏',
                image: 'https://images.unsplash.com/photo-1540959733332-eab4deabeeaf?auto=format&fit=crop&w=800&q=80', // Gambar Borobudur/Asia
                shortDesc: 'Benua terbesar di dunia dan tempat tinggal kita (Indonesia)!',
                fullDesc: 'Benua Asia adalah benua terbesar dan paling padat penduduknya di bumi. Benua ini memiliki wilayah yang sangat luas dengan keberagaman budaya, suku, dan alam yang luar biasa.',
                icons: 'Candi Borobudur (Indonesia), Tembok Besar Cina, Gunung Everest (puncak tertinggi di dunia), Taj Mahal (India).',
                nature: 'Panda khas Cina, Komodo khas Indonesia, Harimau Benggala, Bunga Rafflesia Arnoldii.',
                countries: 'Indonesia, Jepang, Arab Saudi, Cina, India, Korea Selatan.',
                fact: 'Gunung terhitung paling tinggi di dunia, yaitu Gunung Everest, terletak di Benua Asia (perbatasan Nepal dan Tiongkok)!'
            },
            afrika: {
                id: 'afrika',
                name: 'Benua Afrika',
                color: 'from-orange-400 to-rose-500',
                btnColor: 'bg-orange-500 hover:bg-orange-600',
                badgeBg: 'bg-orange-100 text-orange-800',
                tag: 'Benua Hitam & Eksotis',
                emoji: '🦁',
                image: 'https://images.unsplash.com/photo-1516426122078-c23e76319801?auto=format&fit=crop&w=800&q=80', // Gambar Safari/Piramida
                shortDesc: 'Terkenal dengan gurun pasir Sahara yang sangat luas dan hewan safari!',
                fullDesc: 'Benua Afrika adalah benua terbesar kedua di dunia. Afrika terkenal dengan pemandangan alamnya yang eksotis, gurun pasir terluas, serta keanekaragaman hewan liar di padang rumput (savana).',
                icons: 'Piramida Mesir, Patung Sphinx, Gurun Sahara, Sungai Nil (sungai terpanjang).',
                nature: 'Singa, Jerapah, Gajah Afrika, Zebra, Pohon Baobab.',
                countries: 'Mesir, Afrika Selatan, Nigeria, Maroko, Kenya.',
                fact: 'Gurun Sahara di Afrika adalah gurun panas terbesar di bumi, luasnya hampir sama dengan seluruh wilayah Amerika Serikat!'
            },
            amerika_utara: {
                id: 'amerika_utara',
                name: 'Amerika Utara',
                color: 'from-rose-400 to-pink-500',
                btnColor: 'bg-rose-500 hover:bg-rose-600',
                badgeBg: 'bg-rose-100 text-rose-800',
                tag: 'Benua Modern',
                emoji: '🗽',
                image: 'https://images.unsplash.com/photo-1485738422979-f5c462d49f74?auto=format&fit=crop&w=800&q=80', // Gambar Liberty
                shortDesc: 'Rumah bagi Patung Liberty dan pemandangan megah Grand Canyon.',
                fullDesc: 'Benua Amerika Utara terletak di belahan bumi bagian barat. Benua ini memiliki negara-negara maju serta keajaiban alam berupa tebing raksasa dan air terjun terkenal.',
                icons: 'Patung Liberty (AS), Grand Canyon, Air Terjun Niagara, CN Tower (Kanada).',
                nature: 'Beruang Grizzly, Bison, Burung Elang Kepala Botak, Pohon Sequoia Raksasa.',
                countries: 'Amerika Serikat, Kanada, Meksiko.',
                fact: 'Air Terjun Niagara yang terkenal sangat menakjubkan berada di perbatasan antara negara Kanada dan Amerika Serikat!'
            },
            amerika_selatan: {
                id: 'amerika_selatan',
                name: 'Amerika Selatan',
                color: 'from-emerald-400 to-teal-500',
                btnColor: 'bg-emerald-500 hover:bg-emerald-600',
                badgeBg: 'bg-emerald-100 text-emerald-800',
                tag: 'Paru-paru Dunia',
                emoji: '🦜',
                image: 'https://images.unsplash.com/photo-1518638150340-f706e86654de?auto=format&fit=crop&w=800&q=80', // Gambar Amazon/Machu Picchu
                shortDesc: 'Memiliki Hutan Hujan Amazon yang lebat dan Sungai Amazon yang sangat panjang!',
                fullDesc: 'Amerika Selatan adalah benua yang kaya akan keanekaragaman hayati. Sebagian besar wilayah benua ini ditutupi oleh Hutan Hujan Amazon yang menghasilkan oksigen bagi bumi.',
                icons: 'Situs Bersejarah Machu Picchu (Peru), Patung Kristus Penebus (Brasil), Sungai Amazon.',
                nature: 'Burung Macaw, Ular Anaconda, Llama, Ikan Piranha, Katak Beracun Warna-warni.',
                countries: 'Brasil, Argentina, Peru, Kolombia, Chili.',
                fact: 'Hutan Hujan Amazon adalah hutan tropis terbesar di dunia yang sering dijuluki sebagai "Paru-paru Dunia"!'
            },
            eropa: {
                id: 'eropa',
                name: 'Benua Eropa',
                color: 'from-sky-400 to-blue-600',
                btnColor: 'bg-sky-500 hover:bg-sky-600',
                badgeBg: 'bg-sky-100 text-sky-800',
                tag: 'Benua Biru',
                emoji: '🏰',
                image: 'https://images.unsplash.com/photo-1502602898657-3e91760cbb34?auto=format&fit=crop&w=800&q=80', // Gambar Menara Eiffel
                shortDesc: 'Terkenal dengan kastil kerajaan, empat musim, dan Menara Eiffel!',
                fullDesc: 'Benua Eropa sering dijuluki "Benua Biru" karena sebagian besar penduduknya bermata biru dan banyaknya kerajaan terkenal. Eropa memiliki banyak bangunan bersejarah yang indah.',
                icons: 'Menara Eiffel (Prancis), Colosseum (Italia), Menara Pisa, Big Ben (Inggris).',
                nature: 'Serigala Eropa, Rusa Merah, Bunga Tulip, Pohon Ek (Oak).',
                countries: 'Prancis, Inggris, Jerman, Italia, Belanda, Spanyol.',
                fact: 'Di Eropa terdapat negara terkecil di dunia bernama Vatikan yang letaknya ada di dalam Kota Roma, Italia!'
            },
            australia: {
                id: 'australia',
                name: 'Benua Australia',
                color: 'from-purple-400 to-indigo-500',
                btnColor: 'bg-purple-500 hover:bg-purple-600',
                badgeBg: 'bg-purple-100 text-purple-800',
                tag: 'Benua Terkecil',
                emoji: '🦘',
                image: 'https://images.unsplash.com/photo-1523482580672-f109ba8cb9be?auto=format&fit=crop&w=800&q=80', // Gambar Sydney Opera House
                shortDesc: 'Benua paling kecil yang juga merupakan satu negara unik!',
                fullDesc: 'Benua Australia adalah benua terkecil di dunia. Uniknya, seluruh daratan benua ini hanya terdiri dari satu negara saja, yaitu negara Australia. Australia berada di sebelah selatan Indonesia.',
                icons: 'Sydney Opera House, Jembatan Harbor Sydney, Terumbu Karang Great Barrier Reef.',
                nature: 'Kanguru (hewan berkantung), Koala, Platipus, Burung Kookaburra, Pohon Eukaliptus.',
                countries: 'Australia (Negara sekaligus Benua).',
                fact: 'Kanguru ibu memiliki kantung di perutnya yang berguna sebagai tempat membawa dan melindungi bayinya!'
            },
            antartika: {
                id: 'antartika',
                name: 'Benua Antartika',
                color: 'from-cyan-400 to-blue-400',
                btnColor: 'bg-cyan-500 hover:bg-cyan-600',
                badgeBg: 'bg-cyan-100 text-cyan-800',
                tag: 'Benua Es Paling Dingin',
                emoji: '🐧',
                image: 'https://images.unsplash.com/photo-1517783999520-f068d7431a60?auto=format&fit=crop&w=800&q=80', // Gambar Penguin Antartika
                shortDesc: 'Seluruh wilayahnya tertutup es tebal dan menjadi rumah bagi para Penguin!',
                fullDesc: 'Antartika berada di Kutub Selatan bumi. Ini adalah benua paling dingin, paling berangin, dan paling kering. Karena sangat dingin, tidak ada warga yang tinggal tetap di sini kecuali para ilmuwan penjelajah.',
                icons: 'Stasiun Penelitian Ilmiah, Lapisan Es Abadi, Gunung Iceberg.',
                nature: 'Penguin Kaisar, Anjing Laut Weddell, Paus Orca, Krill (udang kecil).',
                countries: 'Tidak ada negara (wilayah netral untuk penelitian dunia).',
                fact: 'Sekitar 90% es yang ada di seluruh bumi berada di Benua Antartika!'
            }
        };

        // BANK SOAL KUIS (10 Soal IPAS Kelas 6)
        const quizData = [
            {
                question: "Benua apakah yang paling besar/luas di dunia dan menjadi tempat tinggal bagi negara Indonesia?",
                options: ["Benua Afrika", "Benua Asia", "Benua Eropa", "Benua Australia"],
                answer: 1,
                explanation: "Benua Asia adalah benua terbesar di dunia dan Indonesia terletak di kawasan Asia Tenggara."
            },
            {
                question: "Benua terkecil di dunia yang hanya terdiri dari satu wilayah negara adalah...",
                options: ["Benua Amerika", "Benua Antartika", "Benua Australia", "Benua Eropa"],
                answer: 2,
                explanation: "Benua Australia adalah benua terkecil di dunia sekaligus merupakan sebuah negara."
            },
            {
                question: "Hewan Khas berupa Kanguru dan Koala dapat kita temukan di Benua...",
                options: ["Australia", "Asia", "Afrika", "Amerika Selatan"],
                answer: 0,
                explanation: "Kanguru dan Koala adalah satwa mamalia berkantung khas asal Benua Australia."
            },
            {
                question: "Benua yang sebagian besar wilayahnya tertutup es tebal dan merupakan tempat tinggal penguin adalah...",
                options: ["Benua Eropa", "Benua Antartika", "Benua Afrika", "Benua Asia"],
                answer: 1,
                explanation: "Benua Antartika terletak di Kutub Selatan dan merupakan tempat paling dingin di bumi yang dihuni oleh penguin."
            },
            {
                question: "Bangunan bersejarah berupa Piramida dan Gurun Sahara yang sangat luas berada di Benua...",
                options: ["Benua Afrika", "Benua Amerika Utara", "Benua Eropa", "Benua Asia"],
                answer: 0,
                explanation: "Piramida Mesir dan Gurun Sahara terletak di Benua Afrika."
            },
            {
                question: "Hutan hujan tropis terbesar di dunia yang dijuluki 'Paru-Paru Dunia' adalah Hutan Amazon yang berada di...",
                options: ["Amerika Utara", "Eropa", "Amerika Selatan", "Asia"],
                answer: 2,
                explanation: "Hutan Hujan Amazon terletak di Benua Amerika Selatan (sebagian besar di negara Brasil)."
            },
            {
                question: "Ikon terkenal berupa Menara Eiffel yang berada di negara Prancis terletak di Benua...",
                options: ["Benua Asia", "Benua Eropa", "Benua Afrika", "Benua Australia"],
                answer: 1,
                explanation: "Menara Eiffel berada di Kota Paris, negara Prancis, yang termasuk dalam wilayah Benua Eropa."
            },
            {
                question: "Gunung tertinggi di dunia yang bernama Gunung Everest terletak di Benua...",
                options: ["Benua Asia", "Benua Amerika Utara", "Benua Antartika", "Benua Eropa"],
                answer: 0,
                explanation: "Gunung Everest berada di Pegunungan Himalaya yang terletak di Benua Asia."
            },
            {
                question: "Apa yang dimaksud dengan Samudra?",
                options: [
                    "Hamparan daratan yang sangat luas",
                    "Lautan garam yang sangat luas mengelilingi benua",
                    "Danau air tawar kecil di atas gunung",
                    "Sungai buatan manusia di perkotaan"
                ],
                answer: 1,
                explanation: "Samudra adalah lautan garam yang sangat luas yang memisahkan benua-benua di bumi."
            },
            {
                question: "Patung Liberty yang sangat terkenal terletak di negara Amerika Serikat di Benua...",
                options: ["Amerika Selatan", "Amerika Utara", "Eropa", "Asia"],
                answer: 1,
                explanation: "Patung Liberty berada di Kota New York, Amerika Serikat, yang masuk dalam Benua Amerika Utara."
            }
        ];

        // STATE APLIKASI
        let currentQuizIndex = 0;
        let score = 0;
        let userAnswers = [];

        // INITIALIZATION
        window.addEventListener('DOMContentLoaded', () => {
            renderBerandaGrid();
            renderMateriList();
            initQuiz();
        });

        // SWITCH TAB NAVIGATION LOGIC
        function switchTab(tabName) {
            // Hide all tabs
            const tabs = ['beranda', 'materi', 'peta', 'kuis'];
            tabs.forEach(t => {
                const el = document.getElementById(`tab-${t}`);
                if (el) el.classList.add('hidden');

                const navBtn = document.getElementById(`nav-${t}`);
                if (navBtn) {
                    navBtn.classList.remove('bg-sky-500', 'text-white', 'shadow-md');
                    navBtn.classList.add('text-slate-600', 'hover:bg-sky-100');
                }
            });

            // Show active tab
            const activeTab = document.getElementById(`tab-${tabName}`);
            if (activeTab) activeTab.classList.remove('hidden');

            // Highlight nav button
            const activeNavBtn = document.getElementById(`nav-${tabName}`);
            if (activeNavBtn) {
                activeNavBtn.classList.remove('text-slate-600', 'hover:bg-sky-100');
                activeNavBtn.classList.add('bg-sky-500', 'text-white', 'shadow-md');
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // TOGGLE MOBILE MENU
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // RENDER GRID BENUA DI BERANDA
        function renderBerandaGrid() {
            const grid = document.getElementById('beranda-benua-grid');
            grid.innerHTML = '';

            Object.values(continentsData).forEach(c => {
                const card = document.createElement('div');
                card.className = `bg-white p-4 rounded-2xl border border-sky-100 custom-shadow card-bounce cursor-pointer flex flex-col items-center text-center space-y-2`;
                card.onclick = () => openContinentModal(c.id);

                card.innerHTML = `
                    <div class="w-12 h-12 rounded-xl flex items-center justify-center text-2xl bg-sky-50">
                        ${c.emoji}
                    </div>
                    <h4 class="font-heading font-bold text-slate-800 text-sm">${c.name}</h4>
                    <span class="text-[10px] font-semibold px-2 py-0.5 rounded-full ${c.badgeBg}">${c.tag}</span>
                `;
                grid.appendChild(card);
            });
        }

        // RENDER LIST MATERI BENUA
        function renderMateriList() {
            const container = document.getElementById('materi-container');
            container.innerHTML = '';

            Object.values(continentsData).forEach((c, idx) => {
                const isEven = idx % 2 === 0;
                const item = document.createElement('div');
                item.className = `bg-white rounded-3xl p-6 sm:p-8 border-2 border-slate-100 custom-shadow flex flex-col ${isEven ? 'lg:flex-row' : 'lg:flex-row-reverse'} gap-6 items-center`;

                item.innerHTML = `
                    <!-- Image Box -->
                    <div class="w-full lg:w-1/2 h-60 sm:h-72 rounded-2xl overflow-hidden shadow-sm relative group">
                        <img src="${c.image}" alt="${c.name}" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                        <div class="absolute top-4 left-4 bg-white/90 backdrop-blur-md px-3 py-1 rounded-full text-xs font-heading font-bold text-slate-800 shadow">
                            ${c.emoji} ${c.tag}
                        </div>
                    </div>

                    <!-- Content Box -->
                    <div class="w-full lg:w-1/2 space-y-4">
                        <div class="space-y-1">
                            <span class="text-xs font-bold uppercase tracking-wider text-sky-600 bg-sky-50 px-3 py-1 rounded-full">Benua Ke-${idx + 1}</span>
                            <h3 class="text-2xl sm:text-3xl font-extrabold text-slate-800">${c.name}</h3>
                        </div>

                        <p class="text-slate-600 text-sm leading-relaxed">${c.fullDesc}</p>

                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-xs">
                            <div class="bg-amber-50 p-3 rounded-xl border border-amber-100">
                                <span class="font-bold text-amber-800 block mb-0.5">🏛️ Ikon Utama:</span>
                                <span class="text-slate-700">${c.icons}</span>
                            </div>
                            <div class="bg-emerald-50 p-3 rounded-xl border border-emerald-100">
                                <span class="font-bold text-emerald-800 block mb-0.5">🐾 Flora & Fauna:</span>
                                <span class="text-slate-700">${c.nature}</span>
                            </div>
                        </div>

                        <!-- Tahukah kamu box -->
                        <div class="bg-sky-50 p-3.5 rounded-xl border border-sky-100 flex items-start space-x-2 text-xs">
                            <span class="text-base">💡</span>
                            <p class="text-sky-900"><strong class="font-bold">Tahukah Kamu?</strong> ${c.fact}</p>
                        </div>

                        <button onclick="openContinentModal('${c.id}')" class="inline-flex items-center space-x-2 text-xs font-heading font-bold text-sky-600 hover:text-sky-700">
                            <span>Buka Ringkasan Modal Detail</span>
                            <i class="fa-solid fa-chevron-right text-[10px]"></i>
                        </button>
                    </div>
                `;
                container.appendChild(item);
            });
        }

        // OPEN CONTINENT MODAL
        function openContinentModal(id) {
            const data = continentsData[id];
            if (!data) return;

            document.getElementById('modal-title').innerText = `${data.emoji} ${data.name}`;
            document.getElementById('modal-badge').innerText = data.tag;
            document.getElementById('modal-image').src = data.image;
            document.getElementById('modal-description').innerText = data.fullDesc;
            document.getElementById('modal-icons').innerText = data.icons;
            document.getElementById('modal-nature').innerText = data.nature;
            document.getElementById('modal-fact').innerText = data.fact;

            const headerBg = document.getElementById('modal-header-bg');
            headerBg.className = `p-6 text-white flex justify-between items-start relative bg-gradient-to-r ${data.color}`;

            document.getElementById('continent-modal').classList.remove('hidden');
        }

        function closeContinentModal() {
            document.getElementById('continent-modal').classList.add('hidden');
        }

        // KUIS INTERAKTIF LOGIC
        function initQuiz() {
            currentQuizIndex = 0;
            score = 0;
            userAnswers = [];
            document.getElementById('quiz-card').classList.remove('hidden');
            document.getElementById('quiz-result-card').classList.add('hidden');
            renderQuestion();
        }

        function renderQuestion() {
            const q = quizData[currentQuizIndex];
            const total = quizData.length;

            // Update Progress Header
            document.getElementById('quiz-progress-text').innerText = `Soal ${currentQuizIndex + 1} dari ${total}`;
            document.getElementById('quiz-score-badge').innerText = `${score} Poin`;

            // Progress Bar Width
            const progressPercent = ((currentQuizIndex + 1) / total) * 100;
            document.getElementById('quiz-progress-bar').style.width = `${progressPercent}%`;

            // Question Text
            document.getElementById('quiz-question').innerText = q.question;

            // Options Render
            const optionsContainer = document.getElementById('quiz-options');
            optionsContainer.innerHTML = '';

            // Hide Feedback & Next Button
            document.getElementById('quiz-feedback').classList.add('hidden');
            document.getElementById('btn-next-question').classList.add('hidden');

            q.options.forEach((opt, idx) => {
                const letter = String.fromCharCode(65 + idx); // A, B, C, D
                const btn = document.createElement('button');
                btn.className = `quiz-opt-btn w-full text-left p-4 rounded-2xl border-2 border-slate-200 hover:border-purple-300 hover:bg-purple-50/50 transition-all font-medium text-slate-700 flex items-center space-x-3`;
                btn.onclick = () => selectAnswer(idx);

                btn.innerHTML = `
                    <span class="w-8 h-8 rounded-xl bg-slate-100 text-slate-600 font-bold flex items-center justify-center shrink-0 border border-slate-200 text-sm">
                        ${letter}
                    </span>
                    <span class="text-sm sm:text-base">${opt}</span>
                `;
                optionsContainer.appendChild(btn);
            });
        }

        function selectAnswer(selectedIndex) {
            const q = quizData[currentQuizIndex];
            const optionBtns = document.querySelectorAll('.quiz-opt-btn');

            // Disable all option buttons
            optionBtns.forEach(btn => btn.disabled = true);

            const isCorrect = selectedIndex === q.answer;

            if (isCorrect) {
                score += 10;
                optionBtns[selectedIndex].classList.remove('border-slate-200');
                optionBtns[selectedIndex].classList.add('border-emerald-500', 'bg-emerald-50', 'text-emerald-900');
            } else {
                optionBtns[selectedIndex].classList.remove('border-slate-200');
                optionBtns[selectedIndex].classList.add('border-rose-500', 'bg-rose-50', 'text-rose-900');

                // Highlight correct option
                optionBtns[q.answer].classList.remove('border-slate-200');
                optionBtns[q.answer].classList.add('border-emerald-500', 'bg-emerald-50');
            }

            // Update Feedback UI
            const feedbackBox = document.getElementById('quiz-feedback');
            const statusEl = document.getElementById('feedback-status');
            const explainEl = document.getElementById('feedback-explain');

            feedbackBox.classList.remove('hidden', 'bg-emerald-50', 'border-emerald-200', 'bg-rose-50', 'border-rose-200');

            if (isCorrect) {
                feedbackBox.classList.add('bg-emerald-50', 'border-emerald-200');
                statusEl.className = 'font-bold flex items-center space-x-2 text-emerald-700 text-base';
                statusEl.innerHTML = `<span>🎉 Benar Sekali!</span>`;
            } else {
                feedbackBox.classList.add('bg-rose-50', 'border-rose-200');
                statusEl.className = 'font-bold flex items-center space-x-2 text-rose-700 text-base';
                statusEl.innerHTML = `<span>❌ Kurang Tepat!</span>`;
            }

            explainEl.innerText = q.explanation;

            // Show Next Button
            document.getElementById('btn-next-question').classList.remove('hidden');
            document.getElementById('quiz-score-badge').innerText = `${score} Poin`;
        }

        function nextQuestion() {
            currentQuizIndex++;
            if (currentQuizIndex < quizData.length) {
                renderQuestion();
            } else {
                showQuizResult();
            }
        }

        function showQuizResult() {
            document.getElementById('quiz-card').classList.add('hidden');
            document.getElementById('quiz-result-card').classList.remove('hidden');

            document.getElementById('final-score').innerText = score;

            const starsEl = document.getElementById('result-stars');
            const msgEl = document.getElementById('final-message');

            if (score === 100) {
                starsEl.innerHTML = '⭐ ⭐ ⭐';
                msgEl.innerText = 'Luar Biasa Sempurna! Kamu adalah Penjelajah Dunia Hebat! 🌟';
            } else if (score >= 70) {
                starsEl.innerHTML = '⭐ ⭐ ⚪';
                msgEl.innerText = 'Hebat Sekali! Pengetahuanmu tentang benua sangat baik! 👍';
            } else {
                starsEl.innerHTML = '⭐ ⚪ ⚪';
                msgEl.innerText = 'Tetap Semangat! Yuk baca lagi materinya agar nilaimu makin sempurna! 💪';
            }
        }

        function restartQuiz() {
            initQuiz();
        }
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Petualangan Pecahan ke Desimal - Kelas 6 MI</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Fredoka & Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;500;600;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Canvas Confetti -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <!-- Tone.js for Sound Effects -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tone/14.8.49/Tone.js"></script>

    <style>
        body {
            font-family: 'Fredoka', sans-serif;
            background-color: #f0fdf4;
        }
        .font-body {
            font-family: 'Inter', sans-serif;
        }
        .tab-btn.active {
            background-color: #16a34a;
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(22, 163, 74, 0.3);
        }
        .card-bounce {
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }
        .card-bounce:hover {
            transform: translateY(-4px);
        }
        .fraction-input {
            width: 60px;
            text-align: center;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col text-slate-800">

    <!-- Navigation Header -->
    <header class="bg-gradient-to-r from-green-500 via-emerald-500 to-teal-600 text-white shadow-lg sticky top-0 z-50">
        <div class="max-w-5xl mx-auto px-4 py-3 flex flex-wrap justify-between items-center">
            <div class="flex items-center space-x-3">
                <div class="bg-white p-2 rounded-2xl shadow-inner text-green-600 text-2xl font-bold">
                    <i class="fa-solid fa-calculator"></i>
                </div>
                <div>
                    <h1 class="text-xl md:text-2xl font-bold tracking-wide">Dunia Matematika MI</h1>
                    <p class="text-xs text-green-100 font-body">Kelas 6 • Pecahan Biasa & Campuran ke Desimal</p>
                </div>
            </div>
            <!-- Audio Toggle & Stars -->
            <div class="flex items-center space-x-3 mt-2 sm:mt-0">
                <button id="soundToggle" onclick="toggleSound()" class="bg-green-700/50 hover:bg-green-700 text-white px-3 py-1.5 rounded-full text-sm font-body flex items-center gap-2 transition">
                    <i id="soundIcon" class="fa-solid fa-volume-high"></i>
                    <span id="soundText" class="hidden sm:inline">Suara: On</span>
                </button>
            </div>
        </div>
    </header>

    <!-- Main Container -->
    <main class="max-w-5xl mx-auto px-4 py-6 flex-grow w-full">
        <!-- Navigation Tabs -->
        <div class="flex flex-wrap justify-center gap-2 mb-6 bg-white p-2 rounded-2xl shadow-md border border-green-100">
            <button onclick="switchTab('materi')" id="tab-materi" class="tab-btn active px-5 py-2.5 rounded-xl font-semibold transition flex items-center gap-2 text-sm md:text-base">
                <i class="fa-solid fa-book-open"></i> 1. Belajar Materi
            </button>
            <button onclick="switchTab('simulasi')" id="tab-simulasi" class="tab-btn bg-slate-100 text-slate-600 hover:bg-slate-200 px-5 py-2.5 rounded-xl font-semibold transition flex items-center gap-2 text-sm md:text-base">
                <i class="fa-solid fa-wand-magic-sparkles"></i> 2. Mesin Ubah Pecahan
            </button>
            <button onclick="switchTab('kuis')" id="tab-kuis" class="tab-btn bg-slate-100 text-slate-600 hover:bg-slate-200 px-5 py-2.5 rounded-xl font-semibold transition flex items-center gap-2 text-sm md:text-base">
                <i class="fa-solid fa-gamepad"></i> 3. Kuis Interaktif
            </button>
        </div>

        <!-- TAB 1: MATERI PEMBELAJARAN -->
        <section id="materi" class="tab-content space-y-6">
            <!-- Hero Concept -->
            <div class="bg-white rounded-3xl p-6 shadow-md border-2 border-green-200 relative overflow-hidden">
                <div class="absolute -right-6 -bottom-6 opacity-10 text-green-700 text-9xl">
                    <i class="fa-solid fa-pie-chart"></i>
                </div>
                <h2 class="text-2xl md:text-3xl font-bold text-green-700 mb-2 flex items-center gap-2">
                    <i class="fa-solid fa-lightbulb text-yellow-500"></i> Apa itu Bilangan Desimal?
                </h2>
                <p class="font-body text-slate-600 leading-relaxed text-base md:text-lg">
                    Bilangan desimal adalah bilangan pecahan yang ditulis menggunakan tanda koma <span class="bg-yellow-200 font-bold px-2 py-0.5 rounded text-yellow-900">( , )</span>. 
                    Setiap angka di belakang koma menunjukkan persepuluhan, perseratusan, atau perseribuan.
                </p>
                
                <!-- Visualizing Tenths/Hundredths -->
                <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mt-6">
                    <div class="bg-green-50 p-4 rounded-2xl border border-green-200 text-center">
                        <span class="text-3xl font-bold text-green-600">0,1</span>
                        <p class="font-body text-sm font-semibold text-slate-700 mt-1">Sama dengan <sup>1</sup>/<sub>10</sub></p>
                        <p class="font-body text-xs text-slate-500 mt-0.5">1 angka di belakang koma (Persepuluhan)</p>
                    </div>
                    <div class="bg-emerald-50 p-4 rounded-2xl border border-emerald-200 text-center">
                        <span class="text-3xl font-bold text-emerald-600">0,01</span>
                        <p class="font-body text-sm font-semibold text-slate-700 mt-1">Sama dengan <sup>1</sup>/<sub>100</sub></p>
                        <p class="font-body text-xs text-slate-500 mt-0.5">2 angka di belakang koma (Perseratusan)</p>
                    </div>
                    <div class="bg-teal-50 p-4 rounded-2xl border border-teal-200 text-center">
                        <span class="text-3xl font-bold text-teal-600">0,001</span>
                        <p class="font-body text-sm font-semibold text-slate-700 mt-1">Sama dengan <sup>1</sup>/<sub>1000</sub></p>
                        <p class="font-body text-xs text-slate-500 mt-0.5">3 angka di belakang koma (Perseribuan)</p>
                    </div>
                </div>
            </div>

            <!-- Method 1: Pecahan Biasa -->
            <div class="bg-white rounded-3xl p-6 shadow-md border-2 border-blue-100">
                <span class="bg-blue-100 text-blue-700 text-xs font-bold px-3 py-1 rounded-full uppercase tracking-wider">Metode 1</span>
                <h3 class="text-xl md:text-2xl font-bold text-blue-800 mt-2 mb-3">
                    Mengubah Pecahan Biasa ke Desimal
                </h3>
                <p class="font-body text-slate-600 mb-4">
                    Ada 2 cara gampang yang bisa adik-adik pilih:
                </p>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <!-- Cara A -->
                    <div class="bg-blue-50/60 p-5 rounded-2xl border border-blue-200 flex flex-col justify-between">
                        <div>
                            <h4 class="font-bold text-blue-900 text-lg mb-2 flex items-center gap-2">
                                <span class="bg-blue-600 text-white w-6 h-6 rounded-full inline-flex items-center justify-center text-xs">A</span>
                                Ubah Penyebut Jadi 10, 100, atau 1000
                            </h4>
                            <p class="font-body text-sm text-slate-600 mb-3">
                                Kalikan pembilang dan penyebut dengan angka yang sama sampai penyebutnya jadi 10, 100, atau 1000.
                            </p>
                            <div class="bg-white p-3 rounded-xl border border-blue-200 font-body text-sm space-y-2">
                                <p class="font-bold text-slate-700">Contoh: <sup>2</sup>/<sub>5</sub> = ... ?</p>
                                <p class="text-slate-600">1. Penyebut 5 bisa diubah ke 10 dengan dikali 2.</p>
                                <p class="text-slate-600">2. Maka: <sup>(2 × 2)</sup>/<sub>(5 × 2)</sub> = <sup>4</sup>/<sub>10</sub></p>
                                <p class="font-bold text-green-600">3. Hasil: <sup>4</sup>/<sub>10</sub> = 0,4</p>
                            </div>
                        </div>
                    </div>

                    <!-- Cara B -->
                    <div class="bg-indigo-50/60 p-5 rounded-2xl border border-indigo-200 flex flex-col justify-between">
                        <div>
                            <h4 class="font-bold text-indigo-900 text-lg mb-2 flex items-center gap-2">
                                <span class="bg-indigo-600 text-white w-6 h-6 rounded-full inline-flex items-center justify-center text-xs">B</span>
                                Pembagian Bersusun (Porogapit)
                            </h4>
                            <p class="font-body text-sm text-slate-600 mb-3">
                                Bagi angka Pembilang (atas) dengan angka Penyebut (bawah) secara langsung.
                            </p>
                            <div class="bg-white p-3 rounded-xl border border-indigo-200 font-body text-sm space-y-2">
                                <p class="font-bold text-slate-700">Contoh: <sup>3</sup>/<sub>4</sub> = ... ?</p>
                                <p class="text-slate-600">Bagi 3 dengan 4 (3 ÷ 4):</p>
                                <p class="text-slate-600">• 3 ÷ 4 tidak bisa, tulis <span class="font-bold">0,</span> lalu tambah angka 0 jadi 30.</p>
                                <p class="text-slate-600">• 30 ÷ 4 = 7 (sisa 2). Tambah 0 lagi jadi 20.</p>
                                <p class="text-slate-600">• 20 ÷ 4 = 5.</p>
                                <p class="font-bold text-indigo-600">Hasil Akhir: 0,75</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Method 2: Pecahan Campuran -->
            <div class="bg-white rounded-3xl p-6 shadow-md border-2 border-purple-100">
                <span class="bg-purple-100 text-purple-700 text-xs font-bold px-3 py-1 rounded-full uppercase tracking-wider">Metode 2</span>
                <h3 class="text-xl md:text-2xl font-bold text-purple-800 mt-2 mb-3">
                    Mengubah Pecahan Campuran ke Desimal
                </h3>
                <p class="font-body text-slate-600 mb-4">
                    Pecahan campuran punya angka utuh dan pecahan biasa. Contoh: <span class="font-bold text-purple-700">2 <sup>1</sup>/<sub>4</sub></span>.
                </p>

                <div class="bg-purple-50/70 p-5 rounded-2xl border border-purple-200">
                    <h4 class="font-bold text-purple-900 text-lg mb-2">Trik Mudah 2 Langkah:</h4>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4 font-body text-sm">
                        <div class="bg-white p-4 rounded-xl border border-purple-200">
                            <span class="font-bold text-purple-700 text-base block mb-1">Langkah 1: Simpan Angka Depan</span>
                            <p class="text-slate-600">
                                Angka depan (utuh) akan menjadi angka di depan koma.<br>
                                Pada <span class="font-bold">2</span> <sup>1</sup>/<sub>4</sub>, simpan angka <span class="font-bold text-purple-700">2</span>.
                            </p>
                        </div>
                        <div class="bg-white p-4 rounded-xl border border-purple-200">
                            <span class="font-bold text-purple-700 text-base block mb-1">Langkah 2: Ubah Pecahannya</span>
                            <p class="text-slate-600">
                                Ubah <sup>1</sup>/<sub>4</sub> jadi desimal:<br>
                                <sup>1</sup>/<sub>4</sub> = <sup>(1×25)</sup>/<sub>(4×25)</sub> = <sup>25</sup>/<sub>100</sub> = <span class="font-bold text-purple-700">0,25</span>
                            </p>
                        </div>
                    </div>
                    <div class="mt-4 bg-purple-600 text-white p-3 rounded-xl text-center font-bold text-lg">
                        Gabungkan: 2 + 0,25 = 2,25 ✨
                    </div>
                </div>
            </div>
        </section>

        <!-- TAB 2: MESIN UBAH PECAHAN (SIMULASI INTERAKTIF) -->
        <section id="simulasi" class="tab-content hidden space-y-6">
            <div class="bg-white rounded-3xl p-6 shadow-md border-2 border-emerald-200 text-center max-w-2xl mx-auto">
                <h2 class="text-2xl font-bold text-emerald-700 mb-2">
                    <i class="fa-solid fa-wand-magic-sparkles text-yellow-500"></i> Mesin Ubah Pecahan
                </h2>
                <p class="font-body text-slate-600 text-sm mb-6">
                    Masukkan angka pecahan biasa atau campuran pilihanmu, lalu klik tombol untuk melihat cara mengubahnya!
                </p>

                <!-- Input Form -->
                <div class="bg-slate-50 p-6 rounded-2xl border border-slate-200 inline-block mb-6 shadow-inner">
                    <div class="flex items-center justify-center gap-3">
                        <!-- Bilangan Utuh (Opsional) -->
                        <div class="flex flex-col items-center">
                            <label class="text-xs text-slate-500 font-body mb-1">Angka Utuh</label>
                            <input type="number" id="simUtuh" placeholder="0" min="0" max="99" 
                                class="w-16 h-16 text-2xl font-bold text-center border-2 border-slate-300 rounded-xl focus:border-green-500 focus:outline-none bg-white">
                        </div>

                        <span class="text-2xl font-bold text-slate-400 mt-5">+</span>

                        <!-- Fraction Part -->
                        <div class="flex flex-col items-center">
                            <label class="text-xs text-slate-500 font-body mb-1">Pembilang</label>
                            <input type="number" id="simPembilang" placeholder="1" min="0" max="99"
                                class="w-16 h-12 text-xl font-bold text-center border-2 border-slate-300 rounded-xl focus:border-green-500 focus:outline-none bg-white">
                            <div class="w-16 h-1 bg-slate-400 my-1 rounded-full"></div>
                            <input type="number" id="simPenyebut" placeholder="2" min="1" max="99"
                                class="w-16 h-12 text-xl font-bold text-center border-2 border-slate-300 rounded-xl focus:border-green-500 focus:outline-none bg-white">
                            <label class="text-xs text-slate-500 font-body mt-1">Penyebut</label>
                        </div>
                    </div>

                    <button onclick="hitungSimulasi()" class="mt-6 w-full bg-green-600 hover:bg-green-700 text-white font-bold py-3 px-6 rounded-xl shadow-lg transition active:scale-95 flex items-center justify-center gap-2">
                        <i class="fa-solid fa-gears"></i> Ubah Jadi Desimal Sekarang!
                    </button>
                </div>

                <!-- Simulation Output -->
                <div id="simulasiResult" class="hidden text-left bg-gradient-to-br from-green-50 to-emerald-50 p-6 rounded-2xl border-2 border-green-300 font-body space-y-4">
                    <div class="flex justify-between items-center border-b border-green-200 pb-3">
                        <span class="font-bold text-green-800 text-lg">Hasil Konversi:</span>
                        <span id="resDesimal" class="text-3xl font-extrabold text-green-600 bg-white px-4 py-1 rounded-xl shadow-sm border border-green-200"></span>
                    </div>

                    <div id="resLangkah" class="space-y-3 text-slate-700 text-sm md:text-base">
                        <!-- Step details generated by JS -->
                    </div>
                </div>
            </div>
        </section>

        <!-- TAB 3: KUIS INTERAKTIF (5 SOAL) -->
        <section id="kuis" class="tab-content hidden space-y-6">
            <!-- Quiz Card Header -->
            <div class="bg-white rounded-3xl p-6 shadow-md border-2 border-yellow-200 max-w-3xl mx-auto">
                <div id="quizContainer">
                    <!-- Progress Bar -->
                    <div class="flex justify-between items-center mb-4">
                        <span id="quizProgressText" class="text-xs font-bold text-slate-500 uppercase tracking-wider font-body">Soal 1 dari 5</span>
                        <span id="quizScoreText" class="text-xs font-bold text-green-600 bg-green-100 px-3 py-1 rounded-full font-body">Skor: 0</span>
                    </div>
                    <div class="w-full bg-slate-100 h-3 rounded-full mb-6 overflow-hidden">
                        <div id="quizProgressBar" class="bg-yellow-400 h-full w-1/5 transition-all duration-300 rounded-full"></div>
                    </div>

                    <!-- Question Text -->
                    <div class="mb-6">
                        <h3 id="quizQuestion" class="text-xl md:text-2xl font-bold text-slate-800 mb-2">
                            <!-- Question injected here -->
                        </h3>
                        <p class="text-sm text-slate-500 font-body">Pilihlah satu jawaban yang paling tepat!</p>
                    </div>

                    <!-- Options Grid -->
                    <div id="quizOptions" class="grid grid-cols-1 md:grid-cols-2 gap-4 font-body">
                        <!-- Options injected here -->
                    </div>

                    <!-- Feedback & Explanation Box -->
                    <div id="quizFeedback" class="hidden mt-6 p-4 rounded-2xl font-body border">
                        <div id="feedbackTitle" class="font-bold text-lg mb-1 flex items-center gap-2"></div>
                        <div id="feedbackText" class="text-sm text-slate-700 leading-relaxed"></div>
                        <button id="btnNextQuestion" onclick="nextQuestion()" class="mt-4 bg-green-600 hover:bg-green-700 text-white font-bold py-2.5 px-6 rounded-xl transition shadow text-sm">
                            Lanjut Soal Berikutnya <i class="fa-solid fa-arrow-right ml-1"></i>
                        </button>
                    </div>
                </div>

                <!-- Quiz Completion Screen -->
                <div id="quizResultScreen" class="hidden text-center py-8 font-body space-y-4">
                    <div class="text-6xl text-yellow-500 mb-2">
                        <i class="fa-solid fa-trophy animate-bounce"></i>
                    </div>
                    <h2 class="text-3xl font-bold text-slate-800">Kuis Selesai! Hore!</h2>
                    <p class="text-slate-600">Kamu telah menyelesaikan semua percobaan soal matematika.</p>
                    
                    <div class="bg-gradient-to-r from-green-500 to-emerald-600 text-white p-6 rounded-2xl max-w-sm mx-auto shadow-lg my-4">
                        <p class="text-sm text-green-100 uppercase tracking-widest font-bold mb-1">Skor Akhir Kamu</p>
                        <span id="finalScore" class="text-6xl font-extrabold">100</span>
                        <p id="scoreMessage" class="text-sm text-green-100 mt-2 font-medium">Luar biasa! Kamu sangat hebat!</p>
                    </div>

                    <button onclick="restartQuiz()" class="bg-yellow-500 hover:bg-yellow-600 text-slate-900 font-bold py-3 px-8 rounded-xl transition shadow-lg inline-flex items-center gap-2">
                        <i class="fa-solid fa-rotate-right"></i> Coba Kuis Lagi
                    </button>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-slate-800 text-slate-400 py-6 text-center font-body text-xs border-t border-slate-700 mt-8">
        <p>© 2026 Media Pembelajaran Interaktif Matematika Kelas 6 MI</p>
        <p class="mt-1 text-slate-500">Materi: Mengubah Pecahan Biasa & Campuran menjadi Desimal</p>
    </footer>

    <script>
        /* sound system initialization */
        let soundEnabled = true;
        
        function playSound(type) {
            if (!soundEnabled) return;
            try {
                const now = Tone.now();
                if (type === 'correct') {
                    const synth = new Tone.Synth().toDestination();
                    synth.triggerAttackRelease("C5", "8n", now);
                    synth.triggerAttackRelease("E5", "8n", now + 0.1);
                    synth.triggerAttackRelease("G5", "8n", now + 0.2);
                } else if (type === 'wrong') {
                    const synth = new Tone.MembraneSynth().toDestination();
                    synth.triggerAttackRelease("C2", "8n", now);
                } else if (type === 'click') {
                    const synth = new Tone.Synth({ envelope: { release: 0.05 } }).toDestination();
                    synth.triggerAttackRelease("A4", "16n", now);
                } else if (type === 'win') {
                    const synth = new Tone.PolySynth().toDestination();
                    synth.triggerAttackRelease(["C4", "E4", "G4", "C5"], "4n");
                }
            } catch(e) {
                console.log("Audio play error", e);
            }
        }

        function toggleSound() {
            soundEnabled = !soundEnabled;
            const icon = document.getElementById('soundIcon');
            const text = document.getElementById('soundText');
            if (soundEnabled) {
                icon.className = 'fa-solid fa-volume-high';
                text.innerText = 'Suara: On';
            } else {
                icon.className = 'fa-solid fa-volume-xmark';
                text.innerText = 'Suara: Off';
            }
        }

        /* Tab Switcher Logic */
        function switchTab(tabId) {
            playSound('click');
            document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('active');
                btn.classList.add('bg-slate-100', 'text-slate-600');
            });

            document.getElementById(tabId).classList.remove('hidden');
            const activeBtn = document.getElementById(`tab-${tabId}`);
            activeBtn.classList.add('active');
            activeBtn.classList.remove('bg-slate-100', 'text-slate-600');
        }

        /* Simulator Calculation Logic */
        function hitungSimulasi() {
            playSound('click');
            const utuh = parseInt(document.getElementById('simUtuh').value) || 0;
            const pembilang = parseInt(document.getElementById('simPembilang').value);
            const penyebut = parseInt(document.getElementById('simPenyebut').value);

            const resultDiv = document.getElementById('simulasiResult');
            const resDesimal = document.getElementById('resDesimal');
            const resLangkah = document.getElementById('resLangkah');

            if (isNaN(pembilang) || isNaN(penyebut) || penyebut <= 0) {
                alert('Mohon masukkan Pembilang dan Penyebut yang valid (Penyebut harus lebih dari 0)!');
                return;
            }

            // Calculations
            const nilaiPecahan = pembilang / penyebut;
            const totalNilai = utuh + nilaiPecahan;
            // Format to maximum 3 decimal places without trailing zeros
            const hasilDesimalFormatted = Number(totalNilai.toFixed(3)).toString().replace('.', ',');

            resDesimal.innerText = hasilDesimalFormatted;

            let htmlLangkah = '';

            if (utuh > 0) {
                htmlLangkah += `
                    <p class="font-bold text-purple-700">📌 Ini adalah Pecahan Campuran (${utuh} <sup>${pembilang}</sup>/<sub>${penyebut}</sub>):</p>
                    <p>1. Angka utuh <span class="font-bold text-purple-700">${utuh}</span> disimpan untuk angka di depan koma.</p>
                    <p>2. Sekarang ubah pecahan biasanya yaitu <sup>${pembilang}</sup>/<sub>${penyebut}</sub> :</p>
                `;
            } else {
                htmlLangkah += `<p class="font-bold text-blue-700">📌 Mengubah Pecahan Biasa (<sup>${pembilang}</sup>/<sub>${penyebut}</sub>):</p>`;
            }

            // Check if denominator easily expands to 10, 100, 1000
            let multiplier = null;
            let targetTen = null;

            [10, 100, 1000].forEach(target => {
                if (!multiplier && target % penyebut === 0) {
                    targetTen = target;
                    multiplier = target / penyebut;
                }
            });

            if (multiplier) {
                const pembilangBaru = pembilang * multiplier;
                const desimalPecahan = (pembilangBaru / targetTen).toString().replace('.', ',');
                htmlLangkah += `
                    <div class="bg-white p-3 rounded-xl border border-green-200">
                        <p class="text-green-800 font-bold">Cara Penyebut (10/100/1000):</p>
                        <p>• Ubah penyebut ${penyebut} menjadi ${targetTen} (dikalikan ${multiplier}).</p>
                        <p>• Pembilang & Penyebut dikali ${multiplier}: <sup>(${pembilang} × ${multiplier})</sup>/<sub>(${penyebut} × ${multiplier})</sub> = <sup>${pembilangBaru}</sup>/<sub>${targetTen}</sub></p>
                        <p>• <sup>${pembilangBaru}</sup>/<sub>${targetTen}</sub> = <span class="font-bold text-green-700">${desimalPecahan}</span></p>
                    </div>
                `;
            } else {
                const desimalPecahan = (pembilang / penyebut).toFixed(3).replace('.', ',');
                htmlLangkah += `
                    <div class="bg-white p-3 rounded-xl border border-indigo-200">
                        <p class="text-indigo-800 font-bold">Cara Pembagian Porogapit (${pembilang} ÷ ${penyebut}):</p>
                        <p>• Bagi angka ${pembilang} dengan ${penyebut} secara langsung.</p>
                        <p>• Hasil pecahan desimalnya = <span class="font-bold text-indigo-700">${desimalPecahan}</span></p>
                    </div>
                `;
            }

            if (utuh > 0) {
                htmlLangkah += `
                    <div class="bg-purple-100 p-3 rounded-xl text-purple-900 font-bold">
                        Gabungkan angka utuh dan pecahan: ${utuh} + ${(pembilang/penyebut).toFixed(3).replace('.', ',')} = ${hasilDesimalFormatted}
                    </div>
                `;
            }

            resLangkah.innerHTML = htmlLangkah;
            resultDiv.classList.remove('hidden');
        }

        /* Quiz Logic & Questions */
        const quizData = [
            {
                question: "Bentuk desimal dari pecahan <sup>1</sup>/<sub>2</sub> adalah ...",
                options: ["0,2", "0,5", "0,25", "0,12"],
                answer: 1,
                explanation: "Penyebut 2 bisa dikali 5 agar menjadi 10. Maka: <sup>(1 × 5)</sup>/<sub>(2 × 5)</sub> = <sup>5</sup>/<sub>10</sub> = 0,5."
            },
            {
                question: "Ubah pecahan <sup>3</sup>/<sub>4</sub> menjadi bilangan desimal!",
                options: ["0,34", "0,43", "0,75", "0,80"],
                answer: 2,
                explanation: "Penyebut 4 bisa dikali 25 agar jadi 100. Maka: <sup>(3 × 25)</sup>/<sub>(4 × 25)</sub> = <sup>75</sup>/<sub>100</sub> = 0,75."
            },
            {
                question: "Aisyah mempunyai pecahan <sup>2</sup>/<sub>5</sub> m pita. Jika diubah ke desimal, panjang pita Aisyah adalah ...",
                options: ["0,4", "0,25", "0,2", "0,5"],
                answer: 0,
                explanation: "Penyebut 5 dikali 2 jadi 10. Pembilang 2 dikali 2 jadi 4. Maka <sup>4</sup>/<sub>10</sub> = 0,4."
            },
            {
                question: "Bentuk desimal dari pecahan campuran 1 <sup>1</sup>/<sub>4</sub> adalah ...",
                options: ["1,14", "1,25", "1,50", "1,75"],
                answer: 1,
                explanation: "Simpan angka utuh 1 di depan. Lalu ubah <sup>1</sup>/<sub>4</sub> = 0,25. Gabungkan menjadi 1 + 0,25 = 1,25."
            },
            {
                question: "Bentuk desimal dari pecahan campuran 2 <sup>3</sup>/<sub>10</sub> adalah ...",
                options: ["2,03", "2,13", "2,3", "2,300"],
                answer: 2,
                explanation: "Angka utuh = 2. Pecahan <sup>3</sup>/<sub>10</sub> sudah persepuluhan yaitu 0,3. Maka hasilnya 2 + 0,3 = 2,3."
            }
        ];

        let currentQuestion = 0;
        let score = 0;
        let answered = false;

        function loadQuestion() {
            answered = false;
            const q = quizData[currentQuestion];

            document.getElementById('quizProgressText').innerText = `Soal ${currentQuestion + 1} dari ${quizData.length}`;
            document.getElementById('quizProgressBar').style.width = `${((currentQuestion + 1) / quizData.length) * 100}%`;
            document.getElementById('quizQuestion').innerHTML = q.question;

            const optionsContainer = document.getElementById('quizOptions');
            optionsContainer.innerHTML = '';

            q.options.forEach((opt, idx) => {
                const btn = document.createElement('button');
                btn.className = 'w-full text-left p-4 rounded-2xl border-2 border-slate-200 hover:border-green-500 hover:bg-green-50/50 transition font-medium flex items-center justify-between text-base bg-white shadow-sm';
                btn.innerHTML = `
                    <span>${opt}</span>
                    <i class="fa-regular fa-circle text-slate-300"></i>
                `;
                btn.onclick = () => checkAnswer(idx, btn);
                optionsContainer.appendChild(btn);
            });

            document.getElementById('quizFeedback').classList.add('hidden');
        }

        function checkAnswer(selectedIndex, btnElement) {
            if (answered) return;
            answered = true;

            const q = quizData[currentQuestion];
            const options = document.getElementById('quizOptions').children;
            const feedbackBox = document.getElementById('quizFeedback');
            const feedbackTitle = document.getElementById('feedbackTitle');
            const feedbackText = document.getElementById('feedbackText');

            if (selectedIndex === q.answer) {
                playSound('correct');
                score += 20;
                document.getElementById('quizScoreText').innerText = `Skor: ${score}`;
                btnElement.className = 'w-full text-left p-4 rounded-2xl border-2 border-green-500 bg-green-100 font-bold flex items-center justify-between text-base text-green-800 shadow';
                btnElement.querySelector('i').className = 'fa-solid fa-circle-check text-green-600';

                feedbackBox.className = 'mt-6 p-4 rounded-2xl font-body border border-green-300 bg-green-50 text-green-900';
                feedbackTitle.innerHTML = `<i class="fa-solid fa-face-smile text-green-600 text-xl"></i> Jawaban Kamu Benar! Great Job!`;
            } else {
                playSound('wrong');
                btnElement.className = 'w-full text-left p-4 rounded-2xl border-2 border-red-400 bg-red-100 font-bold flex items-center justify-between text-base text-red-800 shadow';
                btnElement.querySelector('i').className = 'fa-solid fa-circle-xmark text-red-600';

                // Highlight correct answer
                options[q.answer].className = 'w-full text-left p-4 rounded-2xl border-2 border-green-500 bg-green-50 font-bold flex items-center justify-between text-base text-green-800';
                options[q.answer].querySelector('i').className = 'fa-solid fa-circle-check text-green-600';

                feedbackBox.className = 'mt-6 p-4 rounded-2xl font-body border border-red-200 bg-red-50 text-red-900';
                feedbackTitle.innerHTML = `<i class="fa-solid fa-face-frown text-red-500 text-xl"></i> Ups, Belum Tepat!`;
            }

            feedbackText.innerHTML = `<strong>Pembahasan:</strong> ${q.explanation}`;
            feedbackBox.classList.remove('hidden');
        }

        function nextQuestion() {
            playSound('click');
            currentQuestion++;
            if (currentQuestion < quizData.length) {
                loadQuestion();
            } else {
                showQuizResult();
            }
        }

        function showQuizResult() {
            document.getElementById('quizContainer').classList.add('hidden');
            const resultScreen = document.getElementById('quizResultScreen');
            resultScreen.classList.remove('hidden');

            document.getElementById('finalScore').innerText = score;

            const msg = document.getElementById('scoreMessage');
            if (score === 100) {
                msg.innerText = "Sempurna! Kamu sudah sangat paham materi pecahan ke desimal!";
                confetti({ particleCount: 100, spread: 70, origin: { y: 0.6 } });
                playSound('win');
            } else if (score >= 60) {
                msg.innerText = "Hebat! Kamu sudah bisa. Tingkatkan lagi ya!";
                playSound('win');
            } else {
                msg.innerText = "Tetap semangat! Yuk baca lagi materinya dan coba lagi!";
            }
        }

        function restartQuiz() {
            playSound('click');
            currentQuestion = 0;
            score = 0;
            document.getElementById('quizScoreText').innerText = `Skor: 0`;
            document.getElementById('quizResultScreen').classList.add('hidden');
            document.getElementById('quizContainer').classList.remove('hidden');
            loadQuestion();
        }

        // Initialize quiz on window load
        window.onload = function() {
            loadQuestion();
        };
    </script>
</body>
</html>
