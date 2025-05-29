# swiftexpress-site<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SwiftExpress - Livraison Express</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-fade-in {
            animation: fadeIn 0.8s ease-out forwards;
        }
        .delivery-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        .tracking-progress {
            height: 6px;
            background: linear-gradient(90deg, #3B82F6 0%, #10B981 100%);
        }
        .map-container {
            height: 400px;
            background-image: url('https://maps.googleapis.com/maps/api/staticmap?center=Paris,France&zoom=12&size=800x400&maptype=roadmap&markers=color:red%7C48.8566,2.3522&key=YOUR_API_KEY');
            background-size: cover;
            background-position: center;
        }
    </style>
</head>
<body class="font-sans bg-gray-50">
    <!-- Navigation -->
    <nav class="bg-white shadow-lg">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16">
                <div class="flex items-center">
                    <div class="flex-shrink-0 flex items-center">
                        <i class="fas fa-bolt text-blue-500 text-2xl mr-2"></i>
                        <span class="text-xl font-bold text-gray-900">SwiftExpress</span>
                    </div>
                    <div class="hidden md:ml-10 md:flex md:space-x-8">
                        <a href="#" class="text-blue-600 border-blue-500 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">Accueil</a>
                        <a href="#services" class="text-gray-500 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 border-transparent hover:border-gray-300 text-sm font-medium">Services</a>
                        <a href="#tracking" class="text-gray-500 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 border-transparent hover:border-gray-300 text-sm font-medium">Suivi</a>
                        <a href="#pricing" class="text-gray-500 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 border-transparent hover:border-gray-300 text-sm font-medium">Tarifs</a>
                        <a href="#contact" class="text-gray-500 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 border-transparent hover:border-gray-300 text-sm font-medium">Contact</a>
                    </div>
                </div>
                <div class="hidden md:ml-6 md:flex md:items-center">
                    <button class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-md text-sm font-medium transition duration-300">Connexion</button>
                </div>
                <div class="-mr-2 flex items-center md:hidden">
                    <button id="mobile-menu-button" class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none">
                        <i class="fas fa-bars"></i>
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Mobile menu -->
        <div id="mobile-menu" class="hidden md:hidden">
            <div class="pt-2 pb-3 space-y-1">
                <a href="#" class="bg-blue-50 border-blue-500 text-blue-700 block pl-3 pr-4 py-2 border-l-4 text-base font-medium">Accueil</a>
                <a href="#services" class="border-transparent text-gray-600 hover:bg-gray-50 hover:border-gray-300 hover:text-gray-800 block pl-3 pr-4 py-2 border-l-4 text-base font-medium">Services</a>
                <a href="#tracking" class="border-transparent text-gray-600 hover:bg-gray-50 hover:border-gray-300 hover:text-gray-800 block pl-3 pr-4 py-2 border-l-4 text-base font-medium">Suivi</a>
                <a href="#pricing" class="border-transparent text-gray-600 hover:bg-gray-50 hover:border-gray-300 hover:text-gray-800 block pl-3 pr-4 py-2 border-l-4 text-base font-medium">Tarifs</a>
                <a href="#contact" class="border-transparent text-gray-600 hover:bg-gray-50 hover:border-gray-300 hover:text-gray-800 block pl-3 pr-4 py-2 border-l-4 text-base font-medium">Contact</a>
                <div class="mt-4 pl-3">
                    <button class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-md text-sm font-medium w-full transition duration-300">Connexion</button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <div class="relative bg-blue-600 overflow-hidden">
        <div class="max-w-7xl mx-auto">
            <div class="relative z-10 pb-8 bg-blue-600 sm:pb-16 md:pb-20 lg:max-w-2xl lg:w-full lg:pb-28 xl:pb-32">
                <main class="mt-10 mx-auto max-w-7xl px-4 sm:mt-12 sm:px-6 lg:mt-16 lg:px-8 xl:mt-20">
                    <div class="sm:text-center lg:text-left">
                        <h1 class="text-4xl tracking-tight font-extrabold text-white sm:text-5xl md:text-6xl animate-fade-in">
                            <span class="block">Livraison Express</span>
                            <span class="block text-blue-200">en moins de 24h</span>
                        </h1>
                        <p class="mt-3 text-base text-blue-100 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0 animate-fade-in" style="animation-delay: 0.2s;">
                            Nous livrons vos colis rapidement et en toute sécurité partout en France. Suivi en temps réel et service client disponible 24/7.
                        </p>
                        <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start animate-fade-in" style="animation-delay: 0.4s;">
                            <div class="rounded-md shadow">
                                <a href="#" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-blue-600 bg-white hover:bg-gray-50 md:py-4 md:text-lg md:px-10 transition duration-300">
                                    Commander maintenant
                                </a>
                            </div>
                            <div class="mt-3 sm:mt-0 sm:ml-3">
                                <a href="#tracking" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-blue-500 bg-opacity-60 hover:bg-opacity-70 md:py-4 md:text-lg md:px-10 transition duration-300">
                                    Suivre un colis
                                </a>
                            </div>
                        </div>
                    </div>
                </main>
            </div>
        </div>
        <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2 hidden lg:block">
            <img class="h-56 w-full object-cover sm:h-72 md:h-96 lg:w-full lg:h-full" src="https://images.unsplash.com/photo-1556740738-b6a63e27c4df?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80" alt="Delivery person">
        </div>
    </div>

    <!-- Services Section -->
    <section id="services" class="py-12 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center">
                <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
                    Nos Services Express
                </h2>
                <p class="mt-4 max-w-2xl text-xl text-gray-500 mx-auto">
                    Des solutions adaptées à tous vos besoins de livraison
                </p>
            </div>

            <div class="mt-10">
                <div class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-3">
                    <!-- Service 1 -->
                    <div class="pt-6 delivery-card transition duration-500 ease-in-out transform hover:scale-105">
                        <div class="flow-root bg-gray-50 rounded-lg px-6 pb-8 h-full">
                            <div class="-mt-6">
                                <div>
                                    <span class="inline-flex items-center justify-center p-3 bg-blue-500 rounded-md shadow-lg">
                                        <i class="fas fa-clock text-white text-2xl"></i>
                                    </span>
                                </div>
                                <h3 class="mt-8 text-lg font-medium text-gray-900 tracking-tight">Livraison Express 24h</h3>
                                <p class="mt-5 text-base text-gray-500">
                                    Recevez votre colis en moins de 24 heures partout en France métropolitaine. Parfait pour les urgences.
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Service 2 -->
                    <div class="pt-6 delivery-card transition duration-500 ease-in-out transform hover:scale-105">
                        <div class="flow-root bg-gray-50 rounded-lg px-6 pb-8 h-full">
                            <div class="-mt-6">
                                <div>
                                    <span class="inline-flex items-center justify-center p-3 bg-green-500 rounded-md shadow-lg">
                                        <i class="fas fa-calendar-day text-white text-2xl"></i>
                                    </span>
                                </div>
                                <h3 class="mt-8 text-lg font-medium text-gray-900 tracking-tight">Livraison Programmable</h3>
                                <p class="mt-5 text-base text-gray-500">
                                    Choisissez le jour et l'heure de livraison qui vous conviennent. Livraison le soir et le week-end disponible.
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Service 3 -->
                    <div class="pt-6 delivery-card transition duration-500 ease-in-out transform hover:scale-105">
                        <div class="flow-root bg-gray-50 rounded-lg px-6 pb-8 h-full">
                            <div class="-mt-6">
                                <div>
                                    <span class="inline-flex items-center justify-center p-3 bg-purple-500 rounded-md shadow-lg">
                                        <i class="fas fa-gem text-white text-2xl"></i>
                                    </span>
                                </div>
                                <h3 class="mt-8 text-lg font-medium text-gray-900 tracking-tight">Livraison Premium</h3>
                                <p class="mt-5 text-base text-gray-500">
                                    Service haut de gamme avec emballage sécurisé, assurance et livraison en main propre avec signature.
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Tracking Section -->
    <section id="tracking" class="py-12 bg-gray-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="lg:text-center">
                <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
                    Suivi de Colis en Temps Réel
                </h2>
                <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
                    Entrez votre numéro de suivi pour connaître la position exacte de votre colis
                </p>
            </div>

            <div class="mt-10">
                <div class="bg-white shadow rounded-lg overflow-hidden">
                    <div class="px-4 py-5 sm:p-6">
                        <div class="flex flex-col md:flex-row">
                            <div class="flex-grow">
                                <label for="tracking-number" class="block text-sm font-medium text-gray-700">Numéro de suivi</label>
                                <div class="mt-1 flex rounded-md shadow-sm">
                                    <input type="text" id="tracking-number" class="focus:ring-blue-500 focus:border-blue-500 flex-1 block w-full rounded-md sm:text-sm border-gray-300 p-3 border" placeholder="EX123456789FR">
                                </div>
                            </div>
                            <div class="mt-4 md:mt-0 md:ml-4">
                                <button id="track-button" class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-md shadow-sm text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 transition duration-300">
                                    <i class="fas fa-search mr-2"></i> Suivre
                                </button>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Tracking Results (Hidden by default) -->
                <div id="tracking-results" class="mt-8 bg-white shadow rounded-lg overflow-hidden hidden">
                    <div class="px-4 py-5 sm:p-6">
                        <div class="flex justify-between items-center mb-6">
                            <div>
                                <h3 class="text-lg leading-6 font-medium text-gray-900">Colis #EX123456789FR</h3>
                                <p class="mt-1 text-sm text-gray-500">Expédié le 15/06/2023</p>
                            </div>
                            <span class="px-3 py-1 rounded-full text-sm font-medium bg-green-100 text-green-800">En cours de livraison</span>
                        </div>

                        <div class="mb-6">
                            <div class="flex justify-between text-sm text-gray-500 mb-1">
                                <span>Paris</span>
                                <span>Lyon</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-2.5">
                                <div class="tracking-progress h-2.5 rounded-full" style="width: 75%"></div>
                            </div>
                        </div>

                        <div class="space-y-4">
                            <!-- Tracking Step 1 -->
                            <div class="flex items-start">
                                <div class="flex-shrink-0 pt-0.5">
                                    <div class="h-8 w-8 rounded-full bg-blue-500 flex items-center justify-center">
                                        <i class="fas fa-check text-white text-sm"></i>
                                    </div>
                                </div>
                                <div class="ml-3">
                                    <p class="text-sm font-medium text-gray-900">Colis pris en charge</p>
                                    <p class="text-sm text-gray-500">15/06/2023 - 09:30 • Paris, France</p>
                                </div>
                            </div>

                            <!-- Tracking Step 2 -->
                            <div class="flex items-start">
                                <div class="flex-shrink-0 pt-0.5">envoie moi la
                                    <div class="h-8 w-8 rounded-full bg-blue-500 flex items-center justify-center">
                                        <i class="fas fa-check text-white text-sm"></i>
                                    </div>
                                </div>
                                <div class="ml-3">
                                    <p class="text-sm font-medium text-gray-900">En transit</p>
                                    <p class="text-sm text-gray-500">15/06/2023 - 12:45 • Centre de tri de Melun</p>
                                </div>
                            </div>

                            <!-- Tracking Step 3 -->
                            <div class="flex items-start">
                                <div class="flex-shrink-0 pt-0.5">
                                    <div class="h-8 w-8 rounded-full bg-blue-500 flex items-center justify-center">
                                        <i class="fas fa-check text-white text-sm"></i
</html>
