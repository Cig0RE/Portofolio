<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Portofolio Developer - Pengembang Web Full-Stack & Problem Solver">
    <meta name="keywords" content="developer, programmer, web development, portfolio, full-stack">
    <title>Portofolio Developer</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        primary: '#5D5CDE',
                        secondary: '#6EE7B7',
                        dark: {
                            bg: '#181818',
                            card: '#262626',
                            text: '#E5E7EB'
                        },
                        light: {
                            bg: '#FFFFFF',
                            card: '#F3F4F6',
                            text: '#1F2937'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'Roboto', 'sans-serif']
                    },
                    animation: {
                        'fade-in': 'fadeIn 0.5s ease-in-out',
                        'slide-up': 'slideUp 0.5s ease-in-out',
                    },
                    keyframes: {
                        fadeIn: {
                            '0%': { opacity: '0' },
                            '100%': { opacity: '1' },
                        },
                        slideUp: {
                            '0%': { transform: 'translateY(20px)', opacity: '0' },
                            '100%': { transform: 'translateY(0)', opacity: '1' },
                        },
                    }
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        
        .progress-bar {
            height: 8px;
            width: 100%;
            background-color: #E5E7EB;
            border-radius: 4px;
            overflow: hidden;
        }
        
        .progress {
            height: 100%;
            background-color: #5D5CDE;
            border-radius: 4px;
            transition: width 1s ease-in-out;
        }
        
        .dark .progress-bar {
            background-color: #374151;
        }
        
        .timeline-item {
            position: relative;
            padding-left: 28px;
            padding-bottom: 32px;
        }
        
        .timeline-item::before {
            content: "";
            position: absolute;
            left: 0;
            top: 4px;
            width: 14px;
            height: 14px;
            border-radius: 50%;
            background-color: #5D5CDE;
        }
        
        .timeline-item::after {
            content: "";
            position: absolute;
            left: 7px;
            top: 20px;
            bottom: 0;
            width: 2px;
            background-color: #5D5CDE;
        }
        
        .timeline-item:last-child::after {
            display: none;
        }
        
        .project-card:hover .project-overlay {
            opacity: 1;
        }
        
        .project-card:hover img {
            transform: scale(1.05);
        }
        
        /* GitHub contributions chart */
        .contribution-graph {
            display: grid;
            grid-template-columns: repeat(52, 1fr);
            gap: 3px;
            margin-top: 10px;
        }
        
        .contribution-cell {
            width: 10px;
            height: 10px;
            border-radius: 2px;
            transition: transform 0.2s;
        }
        
        .contribution-cell:hover {
            transform: scale(1.2);
        }
    </style>
</head>
<body class="bg-light-bg dark:bg-dark-bg text-light-text dark:text-dark-text transition-colors duration-300">
    <header class="sticky top-0 z-50 bg-white/80 dark:bg-dark-bg/90 backdrop-blur-sm shadow-sm py-4 transition-colors duration-300">
        <div class="container mx-auto px-4 md:px-6 flex justify-between items-center">
            <div class="flex items-center">
                <a href="#" class="text-xl md:text-2xl font-bold text-dark:text-purple-300 text-light:text-purple-700">CIG0R3</a>
            </div>
            
            <nav class="hidden md:flex space-x-6 font-medium">
                <a href="#about" class="hover:text-primary transition-colors">Tentang</a>
                <a href="#projects" class="hover:text-primary transition-colors">Proyek</a>
                <a href="#experience" class="hover:text-primary transition-colors">Pengalaman</a>
                <a href="#skills" class="hover:text-primary transition-colors">Keahlian</a>
                <a href="#testimonials" class="hover:text-primary transition-colors">Testimoni</a>
                <a href="#contact" class="hover:text-primary transition-colors">Kontak</a>
            </nav>
            
            <div class="flex items-center space-x-3">
                <button id="theme-toggle" class="p-2 rounded-full hover:bg-gray-100 dark:hover:bg-dark-card transition-colors">
                    <i class="fa-solid fa-moon hidden dark:inline-block"></i>
                    <i class="fa-solid fa-sun inline-block dark:hidden"></i>
                </button>
                
                <button class="md:hidden" id="menu-toggle">
                    <i class="fa-solid fa-bars text-xl"></i>
                </button>
            </div>
        </div>
        
        <!-- Mobile menu -->
        <div id="mobile-menu" class="hidden md:hidden container mx-auto px-4 pt-4 pb-2">
            <nav class="flex flex-col space-y-2 font-medium">
                <a href="#about" class="py-2 hover:text-primary transition-colors">Tentang</a>
                <a href="#projects" class="py-2 hover:text-primary transition-colors">Proyek</a>
                <a href="#experience" class="py-2 hover:text-primary transition-colors">Pengalaman</a>
                <a href="#skills" class="py-2 hover:text-primary transition-colors">Keahlian</a>
                <a href="#testimonials" class="py-2 hover:text-primary transition-colors">Testimoni</a>
                <a href="#contact" class="py-2 hover:text-primary transition-colors">Kontak</a>
            </nav>
        </div>
    </header>

    <main>
        <!-- Hero Section -->
        <section class="py-20 md:py-28 transition-colors duration-300">
            <div class="container mx-auto px-4 md:px-6">
                <div class="flex flex-col md:flex-row items-center">
                    <div class="md:w-1/2 mb-10 md:mb-0 md:pr-10 animate-fade-in">
                        <div class="w-48 h-48 md:w-64 md:h-64 mx-auto md:mx-0 rounded-full overflow-hidden border-4 border-primary">
                            <div class="w-full h-full bg-gradient-to-br from-primary to-secondary flex items-center justify-center text-white text-6xl">
                                <i class="fa-solid fa-code"></i>
                            </div>
                        </div>
                    </div>
                    
                    <div class="md:w-1/2 text-center md:text-left animate-slide-up">
                        <h1 class="text-3xl md:text-5xl font-bold mb-4">
                            Eko <span class="text-primary">Maidiansyah</span>
                        </h1>
                        <p class="text-xl md:text-2xl text-gray-600 dark:text-gray-300 mb-6">
                            Full-Stack Developer | Problem Solver | Tech Enthusiast
                        </p>
                        <p class="text-gray-600 dark:text-gray-400 mb-8 max-w-lg mx-auto md:mx-0">
                            Menghadirkan solusi teknologi yang inovatif dengan kode bersih dan performa tinggi. Spesialis dalam pengembangan web modern dan aplikasi multi-platform.
                        </p>
                        <div class="flex flex-wrap gap-4 justify-center md:justify-start">
                            <a href="#contact" class="px-6 py-3 bg-primary text-white font-medium rounded-lg hover:bg-indigo-600 transition-colors">
                                Hubungi Saya
                            </a>
                            <a href="#" class="px-6 py-3 border border-primary text-primary font-medium rounded-lg hover:bg-primary hover:text-white transition-colors">
                                Download CV
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Me Section -->
        <section id="about" class="py-16 bg-light-card dark:bg-dark-card transition-colors duration-300">
            <div class="container mx-auto px-4 md:px-6">
                <h2 class="text-3xl font-bold text-center mb-12">Tentang Saya</h2>
                
                <div class="grid md:grid-cols-2 gap-8 items-center">
                    <div>
                        <p class="text-lg mb-6">
                            Saya adalah seorang <span class="font-semibold text-primary">Full-Stack Developer</span> dengan pengalaman lebih dari 5 tahun dalam mengembangkan aplikasi web dan mobile yang skalabel. Saya menggabungkan keahlian teknis dengan pemahaman bisnis untuk memberikan solusi yang optimal.
                        </p>
                        <p class="text-lg mb-6">
                            Latar belakang saya dalam Computer Science dan pengalaman bekerja dengan berbagai startup dan perusahaan teknologi memberikan saya perspektif yang unik dalam mengatasi tantangan teknis.
                        </p>
                        <p class="text-lg">
                            Saya passionate tentang code quality, arsitektur software yang bersih, dan selalu berusaha mengikuti perkembangan teknologi terbaru.
                        </p>
                    </div>
                    
                    <div class="grid grid-cols-3 gap-4 md:gap-6">
                        <div class="bg-white dark:bg-dark-bg p-4 rounded-lg shadow-sm text-center hover:shadow-md transition-shadow">
                            <div class="text-3xl text-primary mb-2">
                                <i class="fa-solid fa-code"></i>
                            </div>
                            <h3 class="font-semibold mb-1">Frontend</h3>
                            <p class="text-sm text-gray-600 dark:text-gray-400">React, Vue, Angular</p>
                        </div>
                        
                        <div class="bg-white dark:bg-dark-bg p-4 rounded-lg shadow-sm text-center hover:shadow-md transition-shadow">
                            <div class="text-3xl text-primary mb-2">
                                <i class="fa-solid fa-server"></i>
                            </div>
                            <h3 class="font-semibold mb-1">Backend</h3>
                            <p class="text-sm text-gray-600 dark:text-gray-400">Node.js, Python, PHP</p>
                        </div>
                        
                        <div class="bg-white dark:bg-dark-bg p-4 rounded-lg shadow-sm text-center hover:shadow-md transition-shadow">
                            <div class="text-3xl text-primary mb-2">
                                <i class="fa-solid fa-database"></i>
                            </div>
                            <h3 class="font-semibold mb-1">Database</h3>
                            <p class="text-sm text-gray-600 dark:text-gray-400">MySQL, MongoDB, PostgreSQL</p>
                        </div>
                        
                        <div class="bg-white dark:bg-dark-bg p-4 rounded-lg shadow-sm text-center hover:shadow-md transition-shadow">
                            <div class="text-3xl text-primary mb-2">
                                <i class="fa-solid fa-cloud"></i>
                            </div>
                            <h3 class="font-semibold mb-1">Cloud</h3>
                            <p class="text-sm text-gray-600 dark:text-gray-400">AWS, GCP, Azure</p>
                        </div>
                        
                        <div class="bg-white dark:bg-dark-bg p-4 rounded-lg shadow-sm text-center hover:shadow-md transition-shadow">
                            <div class="text-3xl text-primary mb-2">
                                <i class="fa-solid fa-gears"></i>
                            </div>
                            <h3 class="font-semibold mb-1">DevOps</h3>
                            <p class="text-sm text-gray-600 dark:text-gray-400">Docker, CI/CD, Kubernetes</p>
                        </div>
                        
                        <div class="bg-white dark:bg-dark-bg p-4 rounded-lg shadow-sm text-center hover:shadow-md transition-shadow">
                            <div class="text-3xl text-primary mb-2">
                                <i class="fa-solid fa-mobile-screen"></i>
                            </div>
                            <h3 class="font-semibold mb-1">Mobile</h3>
                            <p class="text-sm text-gray-600 dark:text-gray-400">React Native, Flutter</p>
                        </div>
                    </div>
                </div>

                <!-- GitHub Stats -->
                <div class="mt-16 bg-white dark:bg-dark-bg p-6 rounded-lg shadow-sm">
                    <div class="flex flex-col md:flex-row justify-between items-center mb-4">
                        <h3 class="text-xl font-semibold mb-2 md:mb-0">GitHub Contributions</h3>
                        <a href="#" target="_blank" class="text-primary hover:underline">
                            <i class="fa-brands fa-github mr-1"></i>
                            View GitHub Profile
                        </a>
                    </div>
                    
                    <div class="contribution-graph overflow-auto pb-4" id="github-contributions">
                        <!-- JavaScript will generate this graph -->
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="py-16 transition-colors duration-300">
            <div class="container mx-auto px-4 md:px-6">
                <h2 class="text-3xl font-bold text-center mb-12">Proyek Terbaik</h2>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Project 1 -->
                    <div class="project-card bg-light-card dark:bg-dark-card rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="relative overflow-hidden h-48">
                            <div class="w-full h-full bg-gradient-to-r from-blue-500 to-primary flex items-center justify-center">
                                <i class="fa-solid fa-shopping-cart text-white text-4xl"></i>
                            </div>
                            <div class="project-overlay absolute inset-0 bg-black/70 opacity-0 transition-opacity flex items-center justify-center">
                                <div class="text-white text-center p-4">
                                    <p>React, Node.js, MongoDB</p>
                                    <p class="mt-2">Platform e-commerce dengan fitur pembayaran dan sistem manajemen produk canggih</p>
                                </div>
                            </div>
                        </div>
                        <div class="p-5">
                            <h3 class="text-xl font-semibold mb-2">E-Commerce Platform</h3>
                            <p class="text-gray-600 dark:text-gray-400 text-sm mb-4">
                                Lead Developer | 2022
                            </p>
                            <div class="flex flex-wrap gap-2 mb-4">
                                <span class="px-2 py-1 bg-blue-100 dark:bg-blue-900/30 text-blue-600 dark:text-blue-300 rounded text-xs">React</span>
                                <span class="px-2 py-1 bg-green-100 dark:bg-green-900/30 text-green-600 dark:text-green-300 rounded text-xs">Node.js</span>
                                <span class="px-2 py-1 bg-yellow-100 dark:bg-yellow-900/30 text-yellow-600 dark:text-yellow-300 rounded text-xs">MongoDB</span>
                            </div>
                            <a href="#" class="text-primary hover:underline flex items-center text-sm font-medium">
                                Lihat Detail
                                <i class="fa-solid fa-arrow-right ml-1"></i>
                            </a>
                        </div>
                    </div>
                    
                    <!-- Project 2 -->
                    <div class="project-card bg-light-card dark:bg-dark-card rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="relative overflow-hidden h-48">
                            <div class="w-full h-full bg-gradient-to-r from-purple-500 to-pink-500 flex items-center justify-center">
                                <i class="fa-solid fa-chart-line text-white text-4xl"></i>
                            </div>
                            <div class="project-overlay absolute inset-0 bg-black/70 opacity-0 transition-opacity flex items-center justify-center">
                                <div class="text-white text-center p-4">
                                    <p>Vue.js, Laravel, MySQL</p>
                                    <p class="mt-2">Dashboard analitik dengan visualisasi data real-time dan laporan kustom</p>
                                </div>
                            </div>
                        </div>
                        <div class="p-5">
                            <h3 class="text-xl font-semibold mb-2">Analytics Dashboard</h3>
                            <p class="text-gray-600 dark:text-gray-400 text-sm mb-4">
                                Full-Stack Developer | 2021
                            </p>
                            <div class="flex flex-wrap gap-2 mb-4">
                                <span class="px-2 py-1 bg-green-100 dark:bg-green-900/30 text-green-600 dark:text-green-300 rounded text-xs">Vue.js</span>
                                <span class="px-2 py-1 bg-red-100 dark:bg-red-900/30 text-red-600 dark:text-red-300 rounded text-xs">Laravel</span>
                                <span class="px-2 py-1 bg-blue-100 dark:bg-blue-900/30 text-blue-600 dark:text-blue-300 rounded text-xs">MySQL</span>
                            </div>
                            <a href="#" class="text-primary hover:underline flex items-center text-sm font-medium">
                                Lihat Detail
                                <i class="fa-solid fa-arrow-right ml-1"></i>
                            </a>
                        </div>
                    </div>
                    
                    <!-- Project 3 -->
                    <div class="project-card bg-light-card dark:bg-dark-card rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="relative overflow-hidden h-48">
                            <div class="w-full h-full bg-gradient-to-r from-green-500 to-teal-500 flex items-center justify-center">
                                <i class="fa-solid fa-mobile-screen text-white text-4xl"></i>
                            </div>
                            <div class="project-overlay absolute inset-0 bg-black/70 opacity-0 transition-opacity flex items-center justify-center">
                                <div class="text-white text-center p-4">
                                    <p>React Native, Firebase</p>
                                    <p class="mt-2">Aplikasi kesehatan mobile dengan fitur tracking dan notifikasi personal</p>
                                </div>
                            </div>
                        </div>
                        <div class="p-5">
                            <h3 class="text-xl font-semibold mb-2">Health Tracker App</h3>
                            <p class="text-gray-600 dark:text-gray-400 text-sm mb-4">
                                Mobile Developer | 2021
                            </p>
                            <div class="flex flex-wrap gap-2 mb-4">
                                <span class="px-2 py-1 bg-blue-100 dark:bg-blue-900/30 text-blue-600 dark:text-blue-300 rounded text-xs">React Native</span>
                                <span class="px-2 py-1 bg-yellow-100 dark:bg-yellow-900/30 text-yellow-600 dark:text-yellow-300 rounded text-xs">Firebase</span>
                                <span class="px-2 py-1 bg-red-100 dark:bg-red-900/30 text-red-600 dark:text-red-300 rounded text-xs">Redux</span>
                            </div>
                            <a href="#" class="text-primary hover:underline flex items-center text-sm font-medium">
                                Lihat Detail
                                <i class="fa-solid fa-arrow-right ml-1"></i>
                            </a>
                        </div>
                    </div>
                    
                    <!-- Project 4 -->
                    <div class="project-card bg-light-card dark:bg-dark-card rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="relative overflow-hidden h-48">
                            <div class="w-full h-full bg-gradient-to-r from-yellow-500 to-orange-500 flex items-center justify-center">
                                <i class="fa-solid fa-graduation-cap text-white text-4xl"></i>
                            </div>
                            <div class="project-overlay absolute inset-0 bg-black/70 opacity-0 transition-opacity flex items-center justify-center">
                                <div class="text-white text-center p-4">
                                    <p>Angular, Django, PostgreSQL</p>
                                    <p class="mt-2">Platform pendidikan online dengan video courses dan forum diskusi</p>
                                </div>
                            </div>
                        </div>
                        <div class="p-5">
                            <h3 class="text-xl font-semibold mb-2">Learning Management System</h3>
                            <p class="text-gray-600 dark:text-gray-400 text-sm mb-4">
                                Backend Developer | 2020
                            </p>
                            <div class="flex flex-wrap gap-2 mb-4">
                                <span class="px-2 py-1 bg-red-100 dark:bg-red-900/30 text-red-600 dark:text-red-300 rounded text-xs">Angular</span>
                                <span class="px-2 py-1 bg-green-100 dark:bg-green-900/30 text-green-600 dark:text-green-300 rounded text-xs">Django</span>
                                <span class="px-2 py-1 bg-blue-100 dark:bg-blue-900/30 text-blue-600 dark:text-blue-300 rounded text-xs">PostgreSQL</span>
                            </div>
                            <a href="#" class="text-primary hover:underline flex items-center text-sm font-medium">
                                Lihat Detail
                                <i class="fa-solid fa-arrow-right ml-1"></i>
                            </a>
                        </div>
                    </div>
                    
                    <!-- Project 5 -->
                    <div class="project-card bg-light-card dark:bg-dark-card rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="relative overflow-hidden h-48">
                            <div class="w-full h-full bg-gradient-to-r from-red-500 to-pink-500 flex items-center justify-center">
                                <i class="fa-solid fa-comments text-white text-4xl"></i>
                            </div>
                            <div class="project-overlay absolute inset-0 bg-black/70 opacity-0 transition-opacity flex items-center justify-center">
                                <div class="text-white text-center p-4">
                                    <p>React, WebSocket, Express.js</p>
                                    <p class="mt-2">Platform komunikasi real-time dengan fitur chat dan video call</p>
                                </div>
                            </div>
                        </div>
                        <div class="p-5">
                            <h3 class="text-xl font-semibold mb-2">Real-time Chat Application</h3>
                            <p class="text-gray-600 dark:text-gray-400 text-sm mb-4">
                                Frontend Developer | 2020
                            </p>
                            <div class="flex flex-wrap gap-2 mb-4">
                                <span class="px-2 py-1 bg-blue-100 dark:bg-blue-900/30 text-blue-600 dark:text-blue-300 rounded text-xs">React</span>
                                <span class="px-2 py-1 bg-purple-100 dark:bg-purple-900/30 text-purple-600 dark:text-purple-300 rounded text-xs">WebSocket</span>
                                <span class="px-2 py-1 bg-green-100 dark:bg-green-900/30 text-green-600 dark:text-green-300 rounded text-xs">Express.js</span>
                            </div>
                            <a href="#" class="text-primary hover:underline flex items-center text-sm font-medium">
                                Lihat Detail
                                <i class="fa-solid fa-arrow-right ml-1"></i>
                            </a>
                        </div>
                    </div>
                    
                    <!-- Project 6 -->
                    <div class="project-card bg-light-card dark:bg-dark-card rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="relative overflow-hidden h-48">
                            <div class="w-full h-full bg-gradient-to-r from-cyan-500 to-blue-500 flex items-center justify-center">
                                <i class="fa-solid fa-robot text-white text-4xl"></i>
                            </div>
                            <div class="project-overlay absolute inset-0 bg-black/70 opacity-0 transition-opacity flex items-center justify-center">
                                <div class="text-white text-center p-4">
                                    <p>Python, TensorFlow, Flask</p>
                                    <p class="mt-2">Chatbot cerdas dengan kemampuan NLP untuk layanan pelanggan</p>
                                </div>
                            </div>
                        </div>
                        <div class="p-5">
                            <h3 class="text-xl font-semibold mb-2">AI Customer Service Chatbot</h3>
                            <p class="text-gray-600 dark:text-gray-400 text-sm mb-4">
                                ML Engineer | 2019
                            </p>
                            <div class="flex flex-wrap gap-2 mb-4">
                                <span class="px-2 py-1 bg-blue-100 dark:bg-blue-900/30 text-blue-600 dark:text-blue-300 rounded text-xs">Python</span>
                                <span class="px-2 py-1 bg-orange-100 dark:bg-orange-900/30 text-orange-600 dark:text-orange-300 rounded text-xs">TensorFlow</span>
                                <span class="px-2 py-1 bg-gray-100 dark:bg-gray-900/30 text-gray-600 dark:text-gray-300 rounded text-xs">Flask</span>
                            </div>
                            <a href="#" class="text-primary hover:underline flex items-center text-sm font-medium">
                                Lihat Detail
                                <i class="fa-solid fa-arrow-right ml-1"></i>
                            </a>
                        </div>
                    </div>
                </div>
                
                <div class="text-center mt-12">
                    <a href="#" class="inline-flex items-center px-6 py-3 bg-primary text-white font-medium rounded-lg hover:bg-indigo-600 transition-colors">
                        Lihat Semua Proyek
                        <i class="fa-solid fa-arrow-right ml-2"></i>
                    </a>
                </div>
            </div>
        </section>

        <!-- Experience & Education Section -->
        <section id="experience" class="py-16 bg-light-card dark:bg-dark-card transition-colors duration-300">
            <div class="container mx-auto px-4 md:px-6">
                <h2 class="text-3xl font-bold text-center mb-12">Pengalaman & Pendidikan</h2>
                
                <div class="grid md:grid-cols-2 gap-10 lg:gap-16">
                    <!-- Experience -->
                    <div>
                        <h3 class="text-2xl font-semibold mb-8 flex items-center">
                            <i class="fa-solid fa-briefcase text-primary mr-3"></i>
                            Pengalaman Kerja
                        </h3>
                        
                        <div class="timeline">
                            <div class="timeline-item">
                                <h4 class="text-xl font-semibold">Senior Full-Stack Developer</h4>
                                <p class="text-primary font-medium">TechCorp Inc.</p>
                                <p class="text-sm text-gray-600 dark:text-gray-400 mb-2">2021 - Sekarang</p>
                                <p class="text-gray-700 dark:text-gray-300">
                                    Memimpin tim pengembangan untuk sistem e-commerce skala enterprise. Meningkatkan performa aplikasi hingga 40% dengan implementasi caching dan optimasi database.
                                </p>
                            </div>
                            
                            <div class="timeline-item">
                                <h4 class="text-xl font-semibold">Frontend Developer</h4>
                                <p class="text-primary font-medium">WebSolutions</p>
                                <p class="text-sm text-gray-600 dark:text-gray-400 mb-2">2019 - 2021</p>
                                <p class="text-gray-700 dark:text-gray-300">
                                    Mengembangkan UI/UX untuk berbagai aplikasi web dengan fokus pada accessibilitas dan performa. Berhasil mengurangi waktu loading halaman hingga 60%.
                                </p>
                            </div>
                            
                            <div class="timeline-item">
                                <h4 class="text-xl font-semibold">Backend Developer</h4>
                                <p class="text-primary font-medium">DataTech Startup</p>
                                <p class="text-sm text-gray-600 dark:text-gray-400 mb-2">2018 - 2019</p>
                                <p class="text-gray-700 dark:text-gray-300">
                                    Mengembangkan API dan layanan mikroservis untuk platform analitik data. Mengimplementasikan sistem autentikasi dan otorisasi berbasis token.
                                </p>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Education -->
                    <div>
                        <h3 class="text-2xl font-semibold mb-8 flex items-center">
                            <i class="fa-solid fa-graduation-cap text-primary mr-3"></i>
                            Pendidikan
                        </h3>
                        
                        <div class="timeline">
                            <div class="timeline-item">
                                <h4 class="text-xl font-semibold">Master in Computer Science</h4>
                                <p class="text-primary font-medium">University of Technology</p>
                                <p class="text-sm text-gray-600 dark:text-gray-400 mb-2">2016 - 2018</p>
                                <p class="text-gray-700 dark:text-gray-300">
                                    Fokus pada Machine Learning dan Distributed Systems. Tesis tentang optimasi algoritma untuk data streaming dalam arsitektur cloud.
                                </p>
                            </div>
                            
                            <div class="timeline-item">
                                <h4 class="text-xl font-semibold">Bachelor in Software Engineering</h4>
                                <p class="text-primary font-medium">Technical Institute</p>
                                <p class="text-sm text-gray-600 dark:text-gray-400 mb-2">2012 - 2016</p>
                                <p class="text-gray-700 dark:text-gray-300">
                                    Lulus dengan predikat Cum Laude. Aktif dalam klub pemrograman dan kompetisi hackathon nasional.
                                </p>
                            </div>
                            
                            <div class="timeline-item">
                                <h4 class="text-xl font-semibold">Certification</h4>
                                <p class="text-primary font-medium">Berbagai sertifikasi profesional</p>
                                <p class="text-sm text-gray-600 dark:text-gray-400 mb-2">2017 - Sekarang</p>
                                <p class="text-gray-700 dark:text-gray-300">
                                    AWS Certified Solutions Architect, Google Cloud Professional Developer, Certified Kubernetes Administrator (CKA).
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills & Tools Section -->
        <section id="skills" class="py-16 transition-colors duration-300">
            <div class="container mx-auto px-4 md:px-6">
                <h2 class="text-3xl font-bold text-center mb-12">Keahlian & Tools</h2>
                
                <div class="grid md:grid-cols-2 gap-10">
                    <!-- Technical Skills -->
                    <div class="bg-light-card dark:bg-dark-card p-6 rounded-lg shadow-sm">
                        <h3 class="text-xl font-semibold mb-6">Keahlian Teknis</h3>
                        
                        <div class="space-y-6">
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">JavaScript/TypeScript</span>
                                    <span>95%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress" style="width: 95%;"></div>
                                </div>
                            </div>
                            
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">React & React Native</span>
                                    <span>90%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress" style="width: 90%;"></div>
                                </div>
                            </div>
                            
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">Node.js & Express</span>
                                    <span>85%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress" style="width: 85%;"></div>
                                </div>
                            </div>
                            
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">HTML/CSS/SASS</span>
                                    <span>90%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress" style="width: 90%;"></div>
                                </div>
                            </div>
                            
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">Python</span>
                                    <span>80%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress" style="width: 80%;"></div>
                                </div>
                            </div>
                            
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">SQL & NoSQL Databases</span>
                                    <span>85%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress" style="width: 85%;"></div>
                                </div>
                            </div>
                            
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">DevOps & Cloud Services</span>
                                    <span>75%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress" style="width: 75%;"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Tools & Technologies -->
                    <div class="bg-light-card dark:bg-dark-card p-6 rounded-lg shadow-sm">
                        <h3 class="text-xl font-semibold mb-6">Tools & Teknologi</h3>
                        
                        <div class="grid grid-cols-3 gap-4 md:gap-6">
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-react text-4xl text-blue-500 mb-2"></i>
                                <span class="text-sm font-medium">React</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-vuejs text-4xl text-green-500 mb-2"></i>
                                <span class="text-sm font-medium">Vue.js</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-angular text-4xl text-red-500 mb-2"></i>
                                <span class="text-sm font-medium">Angular</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-node-js text-4xl text-green-600 mb-2"></i>
                                <span class="text-sm font-medium">Node.js</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-python text-4xl text-blue-600 mb-2"></i>
                                <span class="text-sm font-medium">Python</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-php text-4xl text-indigo-500 mb-2"></i>
                                <span class="text-sm font-medium">PHP</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-aws text-4xl text-orange-500 mb-2"></i>
                                <span class="text-sm font-medium">AWS</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-docker text-4xl text-blue-500 mb-2"></i>
                                <span class="text-sm font-medium">Docker</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-git-alt text-4xl text-orange-600 mb-2"></i>
                                <span class="text-sm font-medium">Git</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-brands fa-figma text-4xl text-purple-500 mb-2"></i>
                                <span class="text-sm font-medium">Figma</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-solid fa-database text-4xl text-blue-600 mb-2"></i>
                                <span class="text-sm font-medium">MongoDB</span>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center p-3 bg-white dark:bg-dark-bg rounded hover:shadow-md transition-shadow">
                                <i class="fa-solid fa-server text-4xl text-gray-600 dark:text-gray-400 mb-2"></i>
                                <span class="text-sm font-medium">SQL</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Testimonials Section -->
        <section id="testimonials" class="py-16 bg-light-card dark:bg-dark-card transition-colors duration-300">
            <div class="container mx-auto px-4 md:px-6">
                <h2 class="text-3xl font-bold text-center mb-12">Testimonial</h2>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div class="bg-white dark:bg-dark-bg p-6 rounded-lg shadow relative">
                        <div class="absolute -top-5 left-6 text-4xl text-primary">
                            <i class="fa-solid fa-quote-left"></i>
                        </div>
                        <p class="italic text-gray-700 dark:text-gray-300 mb-6 pt-4">
                            "Satu dari sedikit developer yang saya kenal yang bisa menggabungkan keahlian teknis dengan pemahaman bisnis yang mendalam. Solusi yang diberikan selalu tepat sasaran dan scalable."
                        </p>
                        <div class="flex items-center">
                            <div class="w-12 h-12 rounded-full bg-gray-300 flex items-center justify-center text-gray-600">
                                <i class="fa-solid fa-user"></i>
                            </div>
                            <div class="ml-4">
                                <h4 class="font-semibold">Sarah Johnson</h4>
                                <p class="text-sm text-gray-600 dark:text-gray-400">CTO, TechCorp Inc.</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="bg-white dark:bg-dark-bg p-6 rounded-lg shadow relative">
                        <div class="absolute -top-5 left-6 text-4xl text-primary">
                            <i class="fa-solid fa-quote-left"></i>
                        </div>
                        <p class="italic text-gray-700 dark:text-gray-300 mb-6 pt-4">
                            "Tim sangat terkesan dengan pendekatan sistematis dan kualitas kode yang dihasilkan. Proyek kami selesai tepat waktu dan performa aplikasi melebihi ekspektasi kami."
                        </p>
                        <div class="flex items-center">
                            <div class="w-12 h-12 rounded-full bg-gray-300 flex items-center justify-center text-gray-600">
                                <i class="fa-solid fa-user"></i>
                            </div>
                            <div class="ml-4">
                                <h4 class="font-semibold">David Lee</h4>
                                <p class="text-sm text-gray-600 dark:text-gray-400">Product Manager, InnovateTech</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="bg-white dark:bg-dark-bg p-6 rounded-lg shadow relative">
                        <div class="absolute -top-5 left-6 text-4xl text-primary">
                            <i class="fa-solid fa-quote-left"></i>
                        </div>
                        <p class="italic text-gray-700 dark:text-gray-300 mb-6 pt-4">
                            "Kolaborasi yang sangat menyenangkan! Kemampuan komunikasi yang baik dan pendekatan proaktif dalam memecahkan masalah membuat proses pengembangan menjadi lancar."
                        </p>
                        <div class="flex items-center">
                            <div class="w-12 h-12 rounded-full bg-gray-300 flex items-center justify-center text-gray-600">
                                <i class="fa-solid fa-user"></i>
                            </div>
                            <div class="ml-4">
                                <h4 class="font-semibold">Michelle Wong</h4>
                                <p class="text-sm text-gray-600 dark:text-gray-400">UI/UX Designer, DesignHub</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="mt-12 text-center">
                    <a href="https://www.linkedin.com" target="_blank" class="inline-flex items-center text-primary hover:underline">
                        <i class="fa-brands fa-linkedin mr-2"></i>
                        Lihat lebih banyak rekomendasi di LinkedIn
                    </a>
                </div>
            </div>
        </section>

        <!-- Blog/Tutorial Section -->
        <section id="blog" class="py-16 transition-colors duration-300">
            <div class="container mx-auto px-4 md:px-6">
                <h2 class="text-3xl font-bold text-center mb-12">Blog & Tutorial</h2>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div class="bg-light-card dark:bg-dark-card rounded-lg overflow-hidden shadow hover:shadow-md transition-shadow">
                        <div class="h-40 bg-gradient-to-r from-blue-500 to-primary flex items-center justify-center text-white text-5xl">
                            <i class="fa-solid fa-code"></i>
                        </div>
                        <div class="p-5">
                            <span class="text-xs font-semibold inline-block py-1 px-2 rounded-full bg-blue-100 dark:bg-blue-900/30 text-blue-600 dark:text-blue-300 mb-3">React</span>
                            <h3 class="text-xl font-semibold mb-2">
                                <a href="#" class="hover:text-primary transition-colors">Membangun UI Reaktif dengan React Hooks</a>
                            </h3>
                            <p class="text-gray-600 dark:text-gray-400 text-sm mb-3">
                                Tutorial step-by-step untuk menggunakan React Hooks secara efektif dalam membangun interface yang dinamis.
                            </p>
                            <div class="flex justify-between items-center">
                                <span class="text-sm text-gray-500 dark:text-gray-400">
                                    <i class="fa-regular fa-calendar mr-1"></i> 15 Mei 2023
                                </span>
                                <a href="#" class="text-primary hover:underline text-sm font-medium">Baca Selengkapnya</a>
                            </div>
                        </div>
                    </div>
                    
                    <div class="bg-light-card dark:bg-dark-card rounded-lg overflow-hidden shadow hover:shadow-md transition-shadow">
                        <div class="h-40 bg-gradient-to-r from-green-500 to-teal-500 flex items-center justify-center text-white text-5xl">
                            <i class="fa-solid fa-server"></i>
                        </div>
                        <div class="p-5">
                            <span class="text-xs font-semibold inline-block py-1 px-2 rounded-full bg-green-100 dark:bg-green-900/30 text-green-600 dark:text-green-300 mb-3">Node.js</span>
                            <h3 class="text-xl font-semibold mb-2">
                                <a href="#" class="hover:text-primary transition-colors">Arsitektur Mikroservis dengan Node.js dan Docker</a>
                            </h3>
                            <p class="text-gray-600 dark:text-gray-400 text-sm mb-3">
                                Panduan praktis untuk membangun, men-deploy, dan menskalakan aplikasi menggunakan arsitektur mikroservis.
                            </p>
                            <div class="flex justify-between items-center">
                                <span class="text-sm text-gray-500 dark:text-gray-400">
                                    <i class="fa-regular fa-calendar mr-1"></i> 3 April 2023
                                </span>
                                <a href="#" class="text-primary hover:underline text-sm font-medium">Baca Selengkapnya</a>
                            </div>
                        </div>
                    </div>
                    
                    <div class="bg-light-card dark:bg-dark-card rounded-lg overflow-hidden shadow hover:shadow-md transition-shadow">
                        <div class="h-40 bg-gradient-to-r from-purple-500 to-pink-500 flex items-center justify-center text-white text-5xl">
                            <i class="fa-solid fa-database"></i>
                        </div>
                        <div class="p-5">
                            <span class="text-xs font-semibold inline-block py-1 px-2 rounded-full bg-purple-100 dark:bg-purple-900/30 text-purple-600 dark:text-purple-300 mb-3">Database</span>
                            <h3 class="text-xl font-semibold mb-2">
                                <a href="#" class="hover:text-primary transition-colors">Optimasi Query NoSQL untuk Aplikasi Skala Besar</a>
                            </h3>
                            <p class="text-gray-600 dark:text-gray-400 text-sm mb-3">
                                Teknik dan strategi optimasi query MongoDB untuk menangani jutaan data dengan performa tinggi.
                            </p>
                            <div class="flex justify-between items-center">
                                <span class="text-sm text-gray-500 dark:text-gray-400">
                                    <i class="fa-regular fa-calendar mr-1"></i> 20 Februari 2023
                                </span>
                                <a href="#" class="text-primary hover:underline text-sm font-medium">Baca Selengkapnya</a>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="text-center mt-12">
                    <a href="#" class="inline-flex items-center px-6 py-3 border border-primary text-primary font-medium rounded-lg hover:bg-primary hover:text-white transition-colors">
                        Lihat Semua Artikel
                        <i class="fa-solid fa-arrow-right ml-2"></i>
                    </a>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="py-16 bg-light-card dark:bg-dark-card transition-colors duration-300">
            <div class="container mx-auto px-4 md:px-6">
                <h2 class="text-3xl font-bold text-center mb-12">Hubungi Saya</h2>
                
                <div class="grid md:grid-cols-2 gap-10 items-center">
                    <div>
                        <h3 class="text-2xl font-semibold mb-4">Tertarik untuk berkolaborasi?</h3>
                        <p class="text-gray-700 dark:text-gray-300 mb-6">
                            Saya selalu terbuka untuk mendiskusikan proyek baru atau peluang kerja. Hubungi saya melalui formulir di samping atau melalui platform media sosial berikut.
                        </p>
                        
                        <div class="flex flex-col space-y-4">
                            <div class="flex items-center">
                                <div class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center text-primary mr-4">
                                    <i class="fa-solid fa-envelope"></i>
                                </div>
                                <span>email@example.com</span>
                            </div>
                            
                            <div class="flex items-center">
                                <div class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center text-primary mr-4">
                                    <i class="fa-solid fa-location-dot"></i>
                                </div>
                                <span>Jakarta, Indonesia</span>
                            </div>
                        </div>
                        
                        <div class="mt-8">
                            <h4 class="font-semibold mb-4">Temukan saya di:</h4>
                            <div class="flex space-x-4">
                                <a href="#" class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-all">
                                    <i class="fa-brands fa-github"></i>
                                </a>
                                <a href="#" class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-all">
                                    <i class="fa-brands fa-linkedin-in"></i>
                                </a>
                                <a href="#" class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-all">
                                    <i class="fa-brands fa-twitter"></i>
                                </a>
                                <a href="#" class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-all">
                                    <i class="fa-brands fa-gitlab"></i>
                                </a>
                            </div>
                        </div>
                    </div>
                    
                    <div class="bg-white dark:bg-dark-bg p-6 rounded-lg shadow-sm">
                        <form id="contact-form" class="space-y-4">
                            <div>
                                <label for="name" class="block text-sm font-medium mb-1">Nama</label>
                                <input type="text" id="name" name="name" class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary dark:bg-gray-800 dark:text-white text-base" required>
                            </div>
                            
                            <div>
                                <label for="email" class="block text-sm font-medium mb-1">Email</label>
                                <input type="email" id="email" name="email" class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary dark:bg-gray-800 dark:text-white text-base" required>
                            </div>
                            
                            <div>
                                <label for="subject" class="block text-sm font-medium mb-1">Subjek</label>
                                <input type="text" id="subject" name="subject" class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary dark:bg-gray-800 dark:text-white text-base" required>
                            </div>
                            
                            <div>
                                <label for="message" class="block text-sm font-medium mb-1">Pesan</label>
                                <textarea id="message" name="message" rows="4" class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary dark:bg-gray-800 dark:text-white text-base" required></textarea>
                            </div>
                            
                            <button type="submit" class="w-full px-6 py-3 bg-primary text-white font-medium rounded-lg hover:bg-indigo-600 transition-colors">
                                Kirim Pesan
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer class="py-12 bg-gray-900 text-white">
            <div class="text-center text-gray-400">
                <p>&copy;2025. All rights reserved.</p>
            </div>
    </footer>
    
    <a href="#" id="back-to-top" class="fixed bottom-6 right-6 w-12 h-12 rounded-full bg-primary text-white flex items-center justify-center shadow-lg transform translate-y-20 opacity-0 transition-all duration-300">
        <i class="fa-solid fa-arrow-up"></i>
    </a>

    <script>
        // Dark mode toggle
        const themeToggle = document.getElementById('theme-toggle');
        
        // Check for dark mode preference
        if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
            document.documentElement.classList.add('dark');
        }
        
        // Listen for changes in color scheme preference
        window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', event => {
            if (event.matches) {
                document.documentElement.classList.add('dark');
            } else {
                document.documentElement.classList.remove('dark');
            }
        });
        
        themeToggle.addEventListener('click', () => {
            document.documentElement.classList.toggle('dark');
        });
        
        // Mobile menu toggle
        const menuToggle = document.getElementById('menu-toggle');
        const mobileMenu = document.getElementById('mobile-menu');
        
        menuToggle.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });
        
        // Close mobile menu when clicking on a link
        const mobileLinks = mobileMenu.querySelectorAll('a');
        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
            });
        });
        
        // Back to top button
        const backToTop = document.getElementById('back-to-top');
        
        window.addEventListener('scroll', () => {
            if (window.scrollY > 300) {
                backToTop.classList.remove('translate-y-20', 'opacity-0');
                backToTop.classList.add('translate-y-0', 'opacity-100');
            } else {
                backToTop.classList.remove('translate-y-0', 'opacity-100');
                backToTop.classList.add('translate-y-20', 'opacity-0');
            }
        });
        
        backToTop.addEventListener('click', (e) => {
            e.preventDefault();
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // Contact form
        const contactForm = document.getElementById('contact-form');
        
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // Replace with actual form submission logic or API call
            const formData = new FormData(contactForm);
            const formValues = Object.fromEntries(formData.entries());
            
            // Simple validation
            let valid = true;
            for (const key in formValues) {
                if (!formValues[key].trim()) {
                    valid = false;
                    break;
                }
            }
            
            if (valid) {
                // In a real app, you would submit to a server here
                alert('Pesan telah dikirim! Terima kasih.');
                contactForm.reset();
            } else {
                alert('Silakan isi semua field yang diperlukan.');
            }
        });
        
        // Generate GitHub contribution chart
        const contributionGraph = document.getElementById('github-contributions');
        const weeks = 52;
        const daysPerWeek = 7;
        
        // Generate random contribution data
        for (let week = 0; week < weeks; week++) {
            for (let day = 0; day < daysPerWeek; day++) {
                const intensity = Math.floor(Math.random() * 5); // 0-4 for intensity levels
                
                const cell = document.createElement('div');
                cell.className = 'contribution-cell';
                
                // Set color based on intensity
                let bgColor = '';
                if (intensity === 0) {
                    bgColor = 'bg-gray-200 dark:bg-gray-700';
                } else if (intensity === 1) {
                    bgColor = 'bg-green-200 dark:bg-green-900';
                } else if (intensity === 2) {
                    bgColor = 'bg-green-300 dark:bg-green-800';
                } else if (intensity === 3) {
                    bgColor = 'bg-green-400 dark:bg-green-700';
                } else {
                    bgColor = 'bg-green-500 dark:bg-green-600';
                }
                
                cell.classList.add(...bgColor.split(' '));
                
                // Add tooltip with data (in a real app, this would be actual dates and commit counts)
                const date = new Date();
                date.setDate(date.getDate() - ((weeks - week) * 7 + (daysPerWeek - day)));
                
                const tooltip = `${intensity} contributions on ${date.toLocaleDateString()}`;
                cell.setAttribute('title', tooltip);
                
                contributionGraph.appendChild(cell);
            }
        }
        
        // Animate skill bars on scroll
        const animateSkillBars = () => {
            const skillBars = document.querySelectorAll('.progress');
            
            skillBars.forEach(bar => {
                const targetWidth = bar.style.width;
                bar.style.width = '0%';
                
                setTimeout(() => {
                    bar.style.width = targetWidth;
                }, 300);
            });
        };
        
        // Create intersection observer for skills section
        const skillsSection = document.getElementById('skills');
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateSkillBars();
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.2 });
        
        observer.observe(skillsSection);
    </script>
</body>
</html>
