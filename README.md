<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Garasi Detailing - Booking Layanan</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts: Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide-icons@latest/dist/lucide.min.js"></script>
    
    <style>
        /* Custom styles */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc; /* gray-50 */
        }
        .hero-section {
            background-image: linear-gradient(to right, rgba(0,0,0,0.7), rgba(0,0,0,0.4)), url('https://placehold.co/1200x600/1e293b/ffffff?text=Garasi+Detailing');
            background-size: cover;
            background-position: center;
        }
        .card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
        }
        /* New dark card style */
        .card-dark {
            background-color: #1e293b; /* slate-800 */
            border-color: #334155; /* slate-700 */
            background-image: linear-gradient(145deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
        }
        .loader {
            border: 3px solid #f3f3f3; /* Light grey */
            border-top: 3px solid #3498db; /* Blue */
            border-radius: 50%;
            width: 20px;
            height: 20px;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .whatsapp-button {
            background-color: #25D366;
        }
        .whatsapp-button:hover {
            background-color: #128C7E;
        }
        /* Styling for read-only fields */
        .readonly-field {
            background-color: #f3f4f6; /* gray-100 */
            color: #4b5563; /* gray-600 */
            cursor: not-allowed;
        }
    </style>
</head>
<body class="text-gray-800">

    <!-- Header -->
    <header class="bg-white shadow-md sticky top-0 z-40">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center">
                    <i data-lucide="car" class="h-8 w-8 text-blue-600"></i>
                    <span class="ml-2 text-xl font-bold text-gray-800">Garasi Detailing</span>
                </div>
                <nav class="flex items-center">
                    <a href="#layanan" class="text-gray-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium">Layanan</a>
                    <a href="#pesanan-saya" class="text-gray-600 hover:text-blue-600 px-3 py-2 rounded-md text-sm font-medium">Pesanan Saya</a>
                </nav>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main>
        <!-- Hero Section -->
        <section class="hero-section text-white">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-24 sm:py-32 text-center">
                <h1 class="text-4xl sm:text-5xl font-extrabold tracking-tight">Perawatan Detailing Premium</h1>
                <p class="mt-4 max-w-2xl mx-auto text-lg text-gray-200">Solusi lengkap untuk membuat kendaraan Anda tampak seperti baru, luar dan dalam.</p>
                <a href="#layanan" class="mt-8 inline-block bg-blue-600 text-white font-semibold px-8 py-3 rounded-lg shadow-lg hover:bg-blue-700 transition-colors duration-300">Lihat Semua Paket</a>
            </div>
        </section>

        <!-- Services Section -->
        <section id="layanan" class="py-16 sm:py-20 bg-white">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center">
                    <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Price List Layanan</h2>
                    <p class="mt-3 max-w-2xl mx-auto text-lg text-gray-600">Pilih paket terbaik sesuai kebutuhan dan ukuran kendaraan Anda.</p>
                </div>
                <div id="service-list" class="mt-12 grid gap-8 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
                    <!-- Service cards will be dynamically inserted here -->
                </div>
            </div>
        </section>

        <!-- My Bookings Section -->
        <section id="pesanan-saya" class="py-16 sm:py-20 bg-gray-50">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center">
                    <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Riwayat Pesanan Anda</h2>
                    <p class="mt-3 max-w-md mx-auto text-lg text-gray-600">Lacak status pesanan detailing Anda di sini.</p>
                    <div id="user-info" class="mt-4 text-sm text-gray-500"></div>
                </div>
                <div id="daftar-pesanan" class="mt-12 max-w-4xl mx-auto space-y-4">
                    <!-- Booking list will be dynamically inserted here -->
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-6 text-center">
            <p>&copy; 2025 Garasi Detailing. Semua Hak Cipta Dilindungi.</p>
        </div>
    </footer>

    <!-- Booking Modal -->
    <div id="booking-modal" class="fixed inset-0 bg-black bg-opacity-60 flex items-center justify-center z-50 hidden">
        <div class="bg-white rounded-lg shadow-2xl p-6 sm:p-8 w-11/12 max-w-lg mx-auto transform transition-all" id="modal-content">
            <div class="flex justify-between items-center">
                <h3 id="modal-title" class="text-2xl font-bold text-gray-900">Formulir Pemesanan</h3>
                <button id="close-modal" class="text-gray-500 hover:text-gray-800">&times;</button>
            </div>
            <form id="booking-form" class="mt-6 space-y-4">
                 <div>
                    <label for="car-name" class="block text-sm font-medium text-gray-700">Nama Mobil (Contoh: Avanza, Brio)</label>
                     <div class="relative mt-1">
                        <input type="text" id="car-name" name="car-name" class="block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-500 focus:ring-blue-500 sm:text-sm pr-10" placeholder="Ketik nama mobil Anda..." required>
                        <div id="car-name-loader" class="loader absolute top-1/2 right-3 -translate-y-1/2 hidden"></div>
                    </div>
                </div>

                <div>
                    <label for="car-size-display" class="block text-sm font-medium text-gray-700">Ukuran Kendaraan (Otomatis)</label>
                    <input type="text" id="car-size-display" name="car-size-display" class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm readonly-field" readonly placeholder="Ukuran akan terdeteksi otomatis">
                </div>
                
                <div class="p-4 bg-gray-100 rounded-lg">
                    <p class="text-sm text-gray-600">Total Biaya</p>
                    <p id="final-price-container" class="text-2xl font-bold text-gray-900">Rp 0</p>
                </div>
                
                <div>
                    <label for="customer-name" class="block text-sm font-medium text-gray-700">Nama Lengkap</label>
                    <input type="text" id="customer-name" name="customer-name" required class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 sm:text-sm">
                </div>
                <div>
                    <label for="customer-phone" class="block text-sm font-medium text-gray-700">Nomor Telepon (WhatsApp)</label>
                    <input type="tel" id="customer-phone" name="customer-phone" required class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 sm:text-sm" placeholder="Contoh: 08123456789">
                </div>
                <div>
                    <label for="customer-address" class="block text-sm font-medium text-gray-700">Alamat Lengkap (Untuk Home Service)</label>
                    <textarea id="customer-address" name="customer-address" rows="3" required class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 sm:text-sm" placeholder="Contoh: Jl. Sudirman No. 123, Kel. Suka Maju, Kec. Maju Jaya, Jakarta Pusat, 10220"></textarea>
                </div>
                <div>
                    <label for="booking-date" class="block text-sm font-medium text-gray-700">Pilih Tanggal & Waktu</label>
                    <input type="datetime-local" id="booking-date" name="booking-date" required class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 sm:text-sm">
                </div>
                <div class="pt-2 text-right">
                    <button id="submit-booking-btn" type="submit" class="w-full sm:w-auto inline-flex justify-center items-center py-3 px-6 border border-transparent shadow-sm text-base font-medium rounded-md text-white whatsapp-button focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 disabled:bg-gray-400 disabled:cursor-not-allowed" disabled>
                        <i data-lucide="send" class="w-5 h-5 mr-2"></i>
                        Pesan via WhatsApp
                    </button>
                </div>
            </form>
        </div>
    </div>
    
    <!-- Toast Notification -->
    <div id="toast" class="fixed top-5 right-5 bg-green-500 text-white py-2 px-4 rounded-lg shadow-lg hidden animate-pulse">
        <p id="toast-message"></p>
    </div>

    <script type="module">
        // Firebase Imports
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, collection, addDoc, query, onSnapshot } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";
            
        window.onload = () => {
            // --- KONFIGURASI ---
            const waBusinessNumber = '6281223210834';

            // --- DATA LAYANAN ---
            const services = [
                { id: 'ceramic_bronze', title: 'Ceramic Coating Bronze', icon: 'shield', pricing: [ { size: 'Small', price: 1500000 }, { size: 'Medium', price: 1800000 }, { size: 'Large', price: 2200000 }, { size: 'XL/Lux', price: 2500000 } ], details: ["3-Step Paint Correction", "Aplikasi Coating 1 Layer", "Pembersihan Eksterior & Interior", "Garansi 1 Tahun"] },
                { id: 'ceramic_gold', title: 'Ceramic Coating Gold', icon: 'gem', pricing: [ { size: 'Small', price: 2500000 }, { size: 'Medium', price: 3000000 }, { size: 'Large', price: 3500000 }, { size: 'XL/Lux', price: 4000000 } ], details: ["Multi-Step Paint Correction", "Aplikasi Coating 2 Layer", "Detailing Kaca & Mesin", "Garansi 2 Tahun"] },
                { id: 'ceramic_platinum', title: 'Ceramic Coating Platinum', icon: 'award', pricing: [ { size: 'Small', price: 4500000 }, { size: 'Medium', price: 5000000 }, { size: 'Large', price: 5500000 }, { size: 'XL/Lux', price: 6000000 } ], details: ["Full Paint Correction", "Aplikasi Coating 3 Layer", "Interior & Engine Detailing Lengkap", "Garansi 3 Tahun"] },
                { id: 'full_salon', title: 'Full Salon', icon: 'spray-can', pricing: [ { size: 'Small', price: 800000 }, { size: 'Medium', price: 1000000 }, { size: 'Large', price: 1200000 }, { size: 'XL/Lux', price: 1500000 } ], details: ["Eksterior Detailing (Poles & Wax)", "Interior Cleaning Lengkap", "Pembersihan Ruang Mesin", "Detailing Velg & Ban"] },
                { id: 'eksterior_detailing', title: 'Eksterior Detailing', icon: 'car', pricing: [ { size: 'Small', price: 600000 }, { size: 'Medium', price: 650000 }, { size: 'Large', price: 700000 }, { size: 'XL/Lux', price: 750000 } ], details: ["Cuci & Dekontaminasi", "Clay Bar Treatment", "1-Step Polish (menghilangkan baret halus)", "Aplikasi Premium Wax/Sealant"] },
                { id: 'interior_cleaning', title: 'Interior Cleaning', icon: 'armchair', pricing: [ { size: '2 Baris', price: 600000 }, { size: '3 Baris', price: 700000 }, { size: '2 Baris + Bongkar Jok', price: 800000 }, { size: '3 Baris + Bongkar Jok', price: 900000 } ], details: ["Vacuuming menyeluruh", "Pembersihan Dashboard & Panel", "Cuci Karpet & Jok (Fabric/Leather)", "Disinfeksi Kabin"] },
                { id: 'windows_coating', title: 'Windows Coating', icon: 'wind', pricing: [ { size: 'Small', price: 700000 }, { size: 'Medium', price: 900000 }, { size: 'Large', price: 1100000 } ], details: ["Pembersihan Jamur Kaca", "Poles Kaca (menghilangkan baret halus)", "Aplikasi Coating Water Repellent", "Untuk semua kaca"] },
                { id: 'engine_detailing', title: 'Engine Detailing', icon: 'cog', pricing: [ { size: 'All Size', price: 400000 } ], details: ["Pembersihan dari oli & kotoran", "Degreasing aman untuk mesin", "Dressing pada bagian plastik & karet", "Membuat ruang mesin bersih & terawat"] },
                { id: 'jamur_kaca', title: 'Treatment Jamur Kaca', icon: 'droplets', pricing: [ { size: 'All Size Full Kaca', price: 400000 } ], details: ["Menghilangkan noda jamur & waterspot", "Meningkatkan kejernihan kaca", "Aman untuk semua jenis kaca mobil", "Membuat visibilitas lebih baik"] },
                { id: 'coating_motor', title: 'Ceramic Coating Motorcycle', icon: 'bike', pricing: [ { size: 'Small', price: 500000 }, { size: 'Medium', price: 800000 }, { size: 'Large', price: 1200000 }, { size: 'XL/Lux', price: 1500000 } ], details: ["Detailing body & sasis", "Paint Correction", "Aplikasi Coating 1 Layer", "Proteksi dari cuaca & goresan halus"] },
            ];

            // --- RENDER SERVICES ---
            const serviceListContainer = document.getElementById('service-list');
            services.forEach(service => {
                const card = document.createElement('div');
                card.className = 'card card-dark rounded-lg p-6 flex flex-col text-center';
                const startingPrice = service.pricing[0].price;

                const detailsHtml = service.details.map(detail => `
                    <li class="flex items-start text-left">
                        <i data-lucide="check" class="w-4 h-4 mr-2 mt-1 text-green-400 flex-shrink-0"></i>
                        <span>${detail}</span>
                    </li>
                `).join('');

                card.innerHTML = `
                    <div class="bg-slate-700 p-4 rounded-full mx-auto">
                        <i data-lucide="${service.icon}" class="w-8 h-8 text-blue-400"></i>
                    </div>
                    <h3 class="mt-4 text-xl font-bold text-white h-14 flex items-center justify-center gap-2">
                         <i data-lucide="shield-check" class="w-6 h-6 text-green-400"></i>
                         <span>${service.title}</span>
                    </h3>
                    <div class="my-4 text-gray-300 text-sm flex-grow">
                        <h4 class="font-semibold mb-2 text-left">Termasuk Pengerjaan:</h4>
                        <ul class="space-y-2">
                            ${detailsHtml}
                        </ul>
                    </div>
                    <p class="mt-4 text-gray-400">Mulai dari</p>
                    <p class="text-2xl font-bold text-white">Rp ${startingPrice.toLocaleString('id-ID')}</p>
                    <button data-service-id="${service.id}" class="select-service-btn mt-6 w-full bg-blue-600 text-white font-semibold py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors">Pilih Paket</button>
                `;
                serviceListContainer.appendChild(card);
            });
            
            // --- FIREBASE SETUP ---
            const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : { apiKey: "DEMO_KEY", authDomain: "DEMO.firebaseapp.com", projectId: "DEMO" };
            const appId = typeof __app_id !== 'undefined' ? __app_id : 'garasi-detailing-app';
            const app = initializeApp(firebaseConfig);
            const db = getFirestore(app);
            const auth = getAuth(app);
            
            let userId = null;
            let selectedService = null;
            let selectedPrice = 0;
            let selectedSize = '';

            // --- AUTHENTICATION ---
            onAuthStateChanged(auth, async (user) => {
                if (user) {
                    userId = user.uid;
                    document.getElementById('user-info').innerHTML = `ID Pengguna: <span class="font-mono bg-gray-200 px-1 rounded">${userId}</span>`;
                    loadBookings(userId);
                } else {
                    try { await signInAnonymously(auth); } catch (error) { console.error(error); }
                }
            });

            // --- UTILITY & API CALLER ---
            function debounce(func, delay) {
                let timeout;
                return function(...args) {
                    clearTimeout(timeout);
                    timeout = setTimeout(() => func.apply(this, args), delay);
                };
            }

            async function callGemini(prompt) {
                const apiKey = "";
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;
                const payload = { contents: [{ role: "user", parts: [{ text: prompt }] }] };
                try {
                    const response = await fetch(apiUrl, { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(payload) });
                    if (!response.ok) throw new Error(`HTTP error! status: ${response.status}`);
                    const result = await response.json();
                    return result.candidates?.[0]?.content?.parts?.[0]?.text || null;
                } catch (error) {
                    console.error("Gemini API Error:", error);
                    return null;
                }
            }

            // --- DOM ELEMENTS ---
            const bookingModal = document.getElementById('booking-modal');
            const closeModalBtn = document.getElementById('close-modal');
            const bookingForm = document.getElementById('booking-form');
            const carNameInput = document.getElementById('car-name');
            const carNameLoader = document.getElementById('car-name-loader');
            const modalTitle = document.getElementById('modal-title');
            const carSizeDisplay = document.getElementById('car-size-display');
            const finalPriceContainer = document.getElementById('final-price-container');
            const daftarPesananContainer = document.getElementById('daftar-pesanan');
            const submitBtn = document.getElementById('submit-booking-btn');

            // --- MODAL & FORM LOGIC ---
            document.querySelectorAll('.select-service-btn').forEach(button => {
                button.addEventListener('click', (e) => {
                    selectedService = services.find(s => s.i
