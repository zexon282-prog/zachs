<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ZACHS Car Rental | Rent a Ride, Own the Road</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;900&display=swap');
        
        body {
            font-family: 'Inter', sans-serif;
            scroll-behavior: smooth;
            overflow-x: hidden;
        }

        .gradient-bg {
            background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 100%);
        }

        /* --- Dynamic Motion Design Classes --- */
        
        /* Reveal on Scroll Animations */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.2, 1, 0.3, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        .reveal-left {
            opacity: 0;
            transform: translateX(-50px);
            transition: all 0.8s cubic-bezier(0.2, 1, 0.3, 1);
        }

        .reveal-left.active {
            opacity: 1;
            transform: translateX(0);
        }

        /* Floating Animation for Hero Images */
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }

        .float-anim {
            animation: float 6s ease-in-out infinite;
        }

        /* Background Pulse */
        @keyframes pulse-slow {
            0%, 100% { transform: scale(1); opacity: 0.3; }
            50% { transform: scale(1.1); opacity: 0.5; }
        }

        .pulse-blob {
            animation: pulse-slow 10s infinite;
        }

        .card-hover:hover {
            transform: translateY(-12px) scale(1.02);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .hero-img-mask {
            mask-image: linear-gradient(to bottom, black 85%, transparent 100%);
        }

        /* Brand Slider Animation */
        @keyframes scroll {
            0% { transform: translateX(0); }
            100% { transform: translateX(calc(-250px * 7)); }
        }

        .slider {
            background: white;
            height: 100px;
            margin: auto;
            overflow: hidden;
            position: relative;
            width: 100%;
        }

        .slide-track {
            animation: scroll 30s linear infinite;
            display: flex;
            width: calc(250px * 14);
        }

        .slide {
            height: 100px;
            width: 250px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: 900;
            color: #e2e8f0;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            transition: color 0.3s;
        }

        .slide:hover {
            color: #3b82f6;
        }

        /* --- Premium Price Tag Styling --- */
        .price-tag-container {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(8px);
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transform: rotate(-2deg);
            transition: all 0.3s ease;
        }

        .group:hover .price-tag-container {
            transform: rotate(0deg) scale(1.1);
            background: #ffffff;
        }

        .currency-symbol {
            font-size: 0.8rem;
            vertical-align: super;
            margin-right: 2px;
        }

        /* FAQ Accordion Styling */
        .faq-item {
            border-bottom: 1px solid #e5e7eb;
        }
        .faq-item:last-child {
            border-bottom: none;
        }
        .faq-answer {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.4s ease-out;
        }
        .faq-item.active .faq-answer {
            max-height: 200px;
        }
        .faq-item.active .faq-icon {
            transform: rotate(180deg);
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <!-- Navigation -->
    <nav class="sticky top-0 z-50 bg-white/90 backdrop-blur-md shadow-sm">
        <div class="container mx-auto px-6 py-4 flex justify-between items-center">
            <div class="flex items-center">
                <div class="text-2xl font-bold text-blue-900 tracking-tighter">
                    ZACHS <span class="text-blue-500 text-sm block -mt-2">CAR RENTAL</span>
                </div>
            </div>
            <div class="hidden md:flex space-x-8 font-semibold text-blue-900 items-center">
                <a href="#home" class="hover:text-blue-500 transition-colors">Home</a>
                <a href="#about" class="hover:text-blue-500 transition-colors">About Us</a>
                <a href="#fleet" class="hover:text-blue-500 transition-colors">Our Fleet</a>
                <a href="#faq" class="hover:text-blue-500 transition-colors">FAQ</a>
                <a href="#booking" class="bg-blue-900 text-white px-6 py-2 rounded-full hover:bg-blue-800 transition transform hover:scale-105 active:scale-95 shadow-md">Book Now</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="gradient-bg text-white py-16 lg:py-32 overflow-hidden relative">
        <div class="absolute top-0 right-0 w-96 h-96 bg-white/10 rounded-full blur-3xl pulse-blob -translate-y-1/2 translate-x-1/4"></div>
        <div class="absolute bottom-0 left-0 w-64 h-64 bg-blue-400/20 rounded-full blur-3xl pulse-blob delay-700"></div>

        <div class="container mx-auto px-6 flex flex-col lg:flex-row items-center relative z-10">
            <div class="lg:w-1/2 mb-12 lg:mb-0 reveal-left active">
                <h1 class="text-5xl lg:text-7xl font-black mb-4 uppercase tracking-tight leading-[1.1]">
                    NEED A CAR FOR <br> YOUR TRIP OR <br> DAILY NEEDS?
                </h1>
                
                <p class="text-xl md:text-2xl font-medium text-blue-100 italic mb-8 opacity-80">
                    "Rent a Ride, Own the Road"
                </p>

                <p class="text-lg text-blue-50/90 mb-10 max-w-lg leading-relaxed">
                    Drive More, Pay Less. The most affordable and reliable car rental service in Malaysia.
                </p>

                <div class="flex gap-4">
                    <a href="#booking" class="bg-white text-blue-900 font-bold py-4 px-12 rounded-xl shadow-xl text-center hover:bg-blue-50 transition transform hover:translate-y-[-4px] uppercase tracking-wider">
                        RENT NOW
                    </a>
                </div>
            </div>
            <div class="lg:w-1/2 flex justify-center relative reveal">
                <div class="float-anim">
                    <img src="https://images.unsplash.com/photo-1494976388531-d1058494cdd8?auto=format&fit=crop&q=80&w=800" 
                         alt="Modern Car" 
                         class="w-full h-auto rounded-[3rem] shadow-2xl hero-img-mask">
                </div>
            </div>
        </div>
    </section>

    <!-- Brand Slider Section -->
    <div class="slider border-b border-gray-100 py-2">
        <div class="slide-track">
            <div class="slide">Toyota</div><div class="slide">Honda</div><div class="slide">Perodua</div>
            <div class="slide">Proton</div><div class="slide">Nissan</div><div class="slide">BMW</div><div class="slide">Mercedes</div>
            <div class="slide">Toyota</div><div class="slide">Honda</div><div class="slide">Perodua</div>
            <div class="slide">Proton</div><div class="slide">Nissan</div><div class="slide">BMW</div><div class="slide">Mercedes</div>
        </div>
    </div>

    <!-- About Us Section -->
    <section id="about" class="py-20 bg-white overflow-hidden">
        <div class="container mx-auto px-6">
            <div class="flex flex-col lg:flex-row items-center gap-16">
                <div class="lg:w-1/2 reveal-left">
                    <div class="relative group">
                        <img src="https://images.unsplash.com/photo-1552519507-da3b142c6e3d?auto=format&fit=crop&q=80&w=800" 
                             alt="Professional Car Rental Service" 
                             class="rounded-3xl shadow-xl z-10 relative transition-transform duration-500 group-hover:scale-[1.02]">
                        
                        <div class="absolute -top-6 -left-6 w-full h-full bg-blue-100 rounded-3xl -z-10 group-hover:translate-x-2 group-hover:translate-y-2 transition-transform duration-500"></div>
                        
                        <div class="absolute -bottom-6 -right-6 bg-blue-600 text-white p-6 rounded-2xl shadow-lg z-20 hidden md:block group-hover:bg-blue-500 transition-colors">
                            <p class="text-2xl font-bold">100%</p>
                            <p class="text-xs uppercase tracking-wider">Trusted Service</p>
                        </div>
                    </div>
                </div>
                <div class="lg:w-1/2 reveal">
                    <h2 class="text-sm font-bold text-blue-500 mb-2 uppercase tracking-widest">Founded in 2025</h2>
                    <h3 class="text-4xl font-bold text-blue-900 mb-6 leading-tight">About Us: Empowering Malaysians with Quality Transportation</h3>
                    <p class="text-gray-600 mb-6 leading-relaxed">
                        Every Malaysian deserves access to quality transportation without breaking the bank. Recognizing the growing need for flexible and budget-friendly mobility solutions, ZACHS was born to bridge the gap between premium service and affordable pricing.
                    </p>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                        <div class="bg-blue-50 p-6 rounded-2xl border border-blue-100 hover:border-blue-300 transition-colors">
                            <h4 class="font-bold text-blue-900 mb-2 uppercase tracking-wide"><i class="fas fa-bullseye text-blue-500 mr-2"></i> Our Mission</h4>
                            <p class="text-sm text-gray-600">To empower Malaysians with affordable, reliable, and hassle-free car rental services that enable personal and professional growth.</p>
                        </div>
                        <div class="bg-blue-50 p-6 rounded-2xl border border-blue-100 hover:border-blue-300 transition-colors">
                            <h4 class="font-bold text-blue-900 mb-2 uppercase tracking-wide"><i class="fas fa-eye text-blue-500 mr-2"></i> Our Vision</h4>
                            <p class="text-sm text-gray-600">To become Malaysia's most trusted and customer-centric car rental brand, settiing the standard for excellence in mobility.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Why Choose Us -->
    <section class="py-20 bg-blue-50 border-y border-blue-100">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16 reveal">
                <h2 class="text-3xl font-bold text-blue-900 mb-4 uppercase">Why Choose Us</h2>
                <div class="h-1 w-20 bg-blue-500 mx-auto"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div class="p-8 bg-white rounded-2xl text-center card-hover border border-blue-100 shadow-sm reveal" style="transition-delay: 0.1s;">
                    <div class="bg-blue-900 w-12 h-12 rounded-lg flex items-center justify-center text-white mx-auto mb-6">
                        <i class="fas fa-calendar-check"></i>
                    </div>
                    <h3 class="font-bold text-xl mb-2 text-blue-900">Flexible Rentals</h3>
                    <p class="text-gray-600 text-sm">Daily, weekly, or monthly solutions.</p>
                </div>
                <div class="p-8 bg-white rounded-2xl text-center card-hover border border-blue-100 shadow-sm reveal" style="transition-delay: 0.2s;">
                    <div class="bg-blue-900 w-12 h-12 rounded-lg flex items-center justify-center text-white mx-auto mb-6">
                        <i class="fas fa-search-dollar"></i>
                    </div>
                    <h3 class="font-bold text-xl mb-2 text-blue-900">No Hidden Fees</h3>
                    <p class="text-gray-600 text-sm">Transparency first. No surprises.</p>
                </div>
                <div class="p-8 bg-white rounded-2xl text-center card-hover border border-blue-100 shadow-sm reveal" style="transition-delay: 0.3s;">
                    <div class="bg-blue-900 w-12 h-12 rounded-lg flex items-center justify-center text-white mx-auto mb-6">
                        <i class="fas fa-hand-holding-usd"></i>
                    </div>
                    <h3 class="font-bold text-xl mb-2 text-blue-900">Price Match</h3>
                    <p class="text-gray-600 text-sm">We guarantee the best local rates.</p>
                </div>
                <div class="p-8 bg-white rounded-2xl text-center card-hover border border-blue-100 shadow-sm reveal" style="transition-delay: 0.4s;">
                    <div class="bg-blue-900 w-12 h-12 rounded-lg flex items-center justify-center text-white mx-auto mb-6">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h3 class="font-bold text-xl mb-2 text-blue-900">24/7 Roadside</h3>
                    <p class="text-gray-600 text-sm">Assistance whenever you need.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Our Fleet Section -->
    <section id="fleet" class="py-24 bg-white">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16 reveal">
                <span class="text-blue-600 font-black uppercase tracking-[0.4em] text-xs mb-3 block">Premium Fleet</span>
                <h2 class="text-4xl md:text-5xl font-black text-blue-900 mb-6 uppercase">Our Ready Unit</h2>
                <div class="h-1.5 w-24 bg-blue-600 mx-auto rounded-full"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-10">
                <!-- Unit Card 1 -->
                <div class="group bg-gray-50 rounded-[2.5rem] overflow-hidden border border-gray-100 transition-all duration-500 hover:shadow-2xl reveal">
                    <div class="relative h-72 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1541899481282-d53bffe3c35d?auto=format&fit=crop&q=80&w=800" 
                             alt="Economy" class="w-full h-full object-cover group-hover:scale-110 transition duration-700">
                        <div class="absolute top-6 left-6 price-tag-container py-2 px-6 rounded-xl">
                            <span class="block text-blue-600 text-[10px] font-black uppercase tracking-widest mb-1">Low Rate</span>
                            <div class="text-blue-900 font-black flex items-center">
                                <span class="currency-symbol">RM</span>
                                <span class="text-4xl tracking-tighter">100</span>
                                <span class="text-xs ml-1 font-bold text-gray-400">/day</span>
                            </div>
                        </div>
                    </div>
                    <div class="p-8">
                        <div class="flex justify-between items-start mb-4">
                            <h3 class="text-2xl font-black text-blue-900 uppercase">ECONOMY</h3>
                            <span class="bg-green-100 text-green-600 text-[10px] font-bold px-3 py-1 rounded-full">AVAILABLE</span>
                        </div>
                        <a href="#booking" class="block text-center w-full bg-blue-900 text-white py-4 rounded-2xl font-black text-sm uppercase tracking-widest hover:bg-blue-800 transition transform hover:scale-[1.02]">Rent This Unit</a>
                    </div>
                </div>

                <!-- Unit Card 2 (Featured) -->
                <div class="group bg-blue-900 rounded-[2.5rem] overflow-hidden transition-all duration-500 hover:shadow-2xl relative md:-translate-y-4 reveal">
                    <div class="relative h-72 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1550355291-bbee04a92027?auto=format&fit=crop&q=80&w=800" 
                             alt="Sedan" class="w-full h-full object-cover group-hover:scale-110 transition duration-700">
                        <div class="absolute top-6 left-6 price-tag-container py-2 px-6 rounded-xl">
                            <span class="block text-blue-600 text-[10px] font-black uppercase tracking-widest mb-1">Most Popular</span>
                            <div class="text-blue-900 font-black flex items-center">
                                <span class="currency-symbol">RM</span>
                                <span class="text-4xl tracking-tighter">150</span>
                                <span class="text-xs ml-1 font-bold text-gray-400">/day</span>
                            </div>
                        </div>
                    </div>
                    <div class="p-8">
                        <div class="flex justify-between items-start mb-4">
                            <h3 class="text-2xl font-black text-white uppercase">SEDAN</h3>
                            <span class="bg-blue-700 text-blue-100 text-[10px] font-bold px-3 py-1 rounded-full">RECOMMENDED</span>
                        </div>
                        <a href="#booking" class="block text-center w-full bg-white text-blue-900 py-4 rounded-2xl font-black text-sm uppercase tracking-widest hover:bg-gray-100 transition transform hover:scale-[1.02]">Rent This Unit</a>
                    </div>
                </div>

                <!-- Unit Card 3 -->
                <div class="group bg-gray-50 rounded-[2.5rem] overflow-hidden border border-gray-100 transition-all duration-500 hover:shadow-2xl reveal">
                    <div class="relative h-72 overflow-hidden">
                        <img src="https://images.unsplash.com/photo-1618353482480-61ca5a9a7879?auto=format&fit=crop&q=80&w=800" 
                             alt="SUV" class="w-full h-full object-cover group-hover:scale-110 transition duration-700">
                        <div class="absolute top-6 left-6 price-tag-container py-2 px-6 rounded-xl">
                            <span class="block text-blue-600 text-[10px] font-black uppercase tracking-widest mb-1">Premium</span>
                            <div class="text-blue-900 font-black flex items-center">
                                <span class="currency-symbol">RM</span>
                                <span class="text-4xl tracking-tighter">200</span>
                                <span class="text-xs ml-1 font-bold text-gray-400">/day</span>
                            </div>
                        </div>
                    </div>
                    <div class="p-8">
                        <div class="flex justify-between items-start mb-4">
                            <h3 class="text-2xl font-black text-blue-900 uppercase">SUV</h3>
                            <span class="bg-orange-100 text-orange-600 text-[10px] font-bold px-3 py-1 rounded-full">FAMILY CHOICE</span>
                        </div>
                        <a href="#booking" class="block text-center w-full bg-blue-900 text-white py-4 rounded-2xl font-black text-sm uppercase tracking-widest hover:bg-blue-800 transition transform hover:scale-[1.02]">Rent This Unit</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Form Section -->
    <section id="booking" class="py-24 bg-blue-50 relative overflow-hidden">
        <div class="container mx-auto px-6 relative z-10 reveal">
            <div class="max-w-5xl mx-auto">
                <div class="text-center mb-12">
                    <span class="text-blue-600 font-black uppercase tracking-[0.4em] text-xs mb-3 block">Reservation</span>
                    <h2 class="text-4xl font-black text-blue-900 mb-4 uppercase">Book Your Ride</h2>
                </div>

                <form class="bg-white p-8 md:p-12 rounded-[2.5rem] shadow-2xl border border-gray-100">
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-10">
                        
                        <!-- Column 1: Personal Info -->
                        <div class="space-y-6">
                            <h3 class="text-lg font-black text-blue-900 uppercase tracking-wider border-b border-blue-100 pb-2 flex items-center">
                                <i class="fas fa-user-circle mr-2 text-blue-500"></i> Personal Info
                            </h3>
                            <input type="text" placeholder="Full Name" class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition">
                            <input type="tel" placeholder="Phone Number" class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition">
                            <select class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition">
                                <option value="" disabled selected>Select Car Unit</option>
                                <option>Economy Car (RM100/day)</option>
                                <option>Sedan (RM150/day)</option>
                                <option>SUV (RM200/day)</option>
                            </select>
                        </div>

                        <!-- Column 2: Date & Time -->
                        <div class="space-y-6">
                            <h3 class="text-lg font-black text-blue-900 uppercase tracking-wider border-b border-blue-100 pb-2 flex items-center">
                                <i class="fas fa-calendar-alt mr-2 text-blue-500"></i> Schedule
                            </h3>
                            <div>
                                <label class="text-[10px] font-bold text-gray-400 uppercase ml-1">Pickup Date</label>
                                <input type="date" class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 outline-none">
                            </div>
                            <div>
                                <label class="text-[10px] font-bold text-gray-400 uppercase ml-1">Return Date</label>
                                <input type="date" class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 outline-none">
                            </div>
                            <div>
                                <label class="text-[10px] font-bold text-gray-400 uppercase ml-1">Pickup Time</label>
                                <input type="time" class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 outline-none">
                            </div>
                        </div>

                        <!-- Column 3: Locations -->
                        <div class="space-y-6">
                            <h3 class="text-lg font-black text-blue-900 uppercase tracking-wider border-b border-blue-100 pb-2 flex items-center">
                                <i class="fas fa-map-marker-alt mr-2 text-blue-500"></i> Route
                            </h3>
                            <div class="relative">
                                <i class="fas fa-map-pin absolute left-4 top-1/2 -translate-y-1/2 text-blue-400"></i>
                                <input type="text" placeholder="Pickup Location Address" class="w-full bg-gray-50 border border-gray-200 rounded-xl pl-10 pr-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition">
                            </div>
                            <div class="relative">
                                <i class="fas fa-flag-checkered absolute left-4 top-1/2 -translate-y-1/2 text-blue-400"></i>
                                <input type="text" placeholder="Drop-off Location Address" class="w-full bg-gray-50 border border-gray-200 rounded-xl pl-10 pr-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition">
                            </div>
                            <textarea placeholder="Special Instructions (Optional)" rows="2" class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 focus:ring-2 focus:ring-blue-500 outline-none transition resize-none"></textarea>
                        </div>
                    </div>
                    <button type="button" class="w-full bg-blue-900 text-white py-5 rounded-2xl font-black uppercase tracking-widest shadow-xl hover:bg-blue-800 transition-all hover:tracking-[0.4em] flex items-center justify-center">
                        <i class="fas fa-paper-plane mr-3"></i> Submit Booking Request
                    </button>
                    <p class="text-center text-[10px] text-gray-400 mt-4 uppercase tracking-widest font-bold">Our team will contact you within 30 minutes for confirmation.</p>
                </form>
            </div>
        </div>
    </section>

    <!-- Feedback Section -->
    <section id="feedback" class="py-24 bg-blue-900 text-white overflow-hidden">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16 reveal">
                <h2 class="text-3xl font-black uppercase tracking-widest">Feedback</h2>
                <div class="h-1 w-20 bg-blue-400 mx-auto mt-4"></div>
            </div>
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                <div class="bg-blue-800/40 p-8 rounded-3xl border border-blue-700 backdrop-blur-sm reveal" style="transition-delay: 0.1s;">
                    <div class="text-yellow-400 mb-4"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p class="italic mb-6 leading-relaxed">"Best rental deal in KL! Smooth and affordable."</p>
                    <div class="flex items-center">
                        <div class="w-10 h-10 bg-blue-500 rounded-full flex items-center justify-center font-bold mr-3">M</div>
                        <div><h4 class="font-bold">Mei Lin</h4><p class="text-blue-300 text-xs">Kuala Lumpur</p></div>
                    </div>
                </div>
                <div class="bg-blue-800/40 p-8 rounded-3xl border border-blue-700 backdrop-blur-sm reveal" style="transition-delay: 0.2s;">
                    <div class="text-yellow-400 mb-4"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p class="italic mb-6 leading-relaxed">"No hidden fees, great customer service."</p>
                    <div class="flex items-center">
                        <div class="w-10 h-10 bg-blue-500 rounded-full flex items-center justify-center font-bold mr-3">J</div>
                        <div><h4 class="font-bold">Joelyn</h4><p class="text-blue-300 text-xs">Penang</p></div>
                    </div>
                </div>
                <div class="bg-blue-800/40 p-8 rounded-3xl border border-blue-700 backdrop-blur-sm reveal" style="transition-delay: 0.3s;">
                    <div class="text-yellow-400 mb-4"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p class="italic mb-6 leading-relaxed">"Reliable for all my client meetings."</p>
                    <div class="flex items-center">
                        <div class="w-10 h-10 bg-blue-500 rounded-full flex items-center justify-center font-bold mr-3">B</div>
                        <div><h4 class="font-bold">Ben Li</h4><p class="text-blue-300 text-xs">Johor Bahru</p></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- FAQ Section -->
    <section id="faq" class="py-24 bg-white">
        <div class="container mx-auto px-6 max-w-4xl">
            <div class="text-center mb-16 reveal">
                <span class="text-blue-600 font-black uppercase tracking-[0.4em] text-xs mb-3 block">Got Questions?</span>
                <h2 class="text-4xl font-black text-blue-900 mb-6 uppercase">Frequently Asked</h2>
                <div class="h-1.5 w-24 bg-blue-600 mx-auto rounded-full"></div>
            </div>

            <div class="space-y-4 reveal">
                <!-- FAQ Item 1 -->
                <div class="faq-item bg-gray-50 rounded-2xl overflow-hidden border border-gray-100 transition-all duration-300">
                    <button class="w-full flex justify-between items-center p-6 text-left focus:outline-none" onclick="toggleFAQ(this)">
                        <span class="text-lg font-bold text-blue-900">What documents do I need to rent a car?</span>
                        <i class="fas fa-chevron-down text-blue-500 transition-transform duration-300 faq-icon"></i>
                    </button>
                    <div class="faq-answer px-6">
                        <p class="pb-6 text-gray-600 leading-relaxed">You will need a valid Malaysian driving license (or international permit), an IC or Passport for identification, and a latest utility bill for address verification.</p>
                    </div>
                </div>

                <!-- FAQ Item 2 -->
                <div class="faq-item bg-gray-50 rounded-2xl overflow-hidden border border-gray-100 transition-all duration-300">
                    <button class="w-full flex justify-between items-center p-6 text-left focus:outline-none" onclick="toggleFAQ(this)">
                        <span class="text-lg font-bold text-blue-900">Is there a security deposit?</span>
                        <i class="fas fa-chevron-down text-blue-500 transition-transform duration-300 faq-icon"></i>
                    </button>
                    <div class="faq-answer px-6">
                        <p class="pb-6 text-gray-600 leading-relaxed">Yes, a refundable security deposit of RM200-RM500 (depending on car type) is required. This is returned within 3-7 working days after the car is returned in good condition.</p>
                    </div>
                </div>

                <!-- FAQ Item 3 -->
                <div class="faq-item bg-gray-50 rounded-2xl overflow-hidden border border-gray-100 transition-all duration-300">
                    <button class="w-full flex justify-between items-center p-6 text-left focus:outline-none" onclick="toggleFAQ(this)">
                        <span class="text-lg font-bold text-blue-900">Can I drive the car outside of Kedah/Penang?</span>
                        <i class="fas fa-chevron-down text-blue-500 transition-transform duration-300 faq-icon"></i>
                    </button>
                    <div class="faq-answer px-6">
                        <p class="pb-6 text-gray-600 leading-relaxed">Yes, our cars can be driven nationwide across Peninsular Malaysia. However, we do not allow our vehicles to be driven into Thailand or Singapore without prior written approval.</p>
                    </div>
                </div>

                <!-- FAQ Item 4 -->
                <div class="faq-item bg-gray-50 rounded-2xl overflow-hidden border border-gray-100 transition-all duration-300">
                    <button class="w-full flex justify-between items-center p-6 text-left focus:outline-none" onclick="toggleFAQ(this)">
                        <span class="text-lg font-bold text-blue-900">What happens in case of an accident?</span>
                        <i class="fas fa-chevron-down text-blue-500 transition-transform duration-300 faq-icon"></i>
                    </button>
                    <div class="faq-answer px-6">
                        <p class="pb-6 text-gray-600 leading-relaxed">All our cars are covered by commercial insurance. In case of an accident, please contact our 24/7 emergency hotline immediately. You may be responsible for the insurance excess amount as per your agreement.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-blue-950 text-white py-16">
        <div class="container mx-auto px-6">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-12 text-center md:text-left mb-12">
                <div>
                    <div class="text-3xl font-bold mb-4 tracking-tighter">ZACHS</div>
                    <p class="text-blue-300 italic text-sm">"Rent a Ride, Own the Road"</p>
                </div>
                <div>
                    <h4 class="font-bold mb-6 text-blue-400 uppercase tracking-widest text-xs">Contact Us</h4>
                    <p class="text-blue-200 text-sm"><i class="fas fa-phone mr-2"></i> 05-6912033</p>
                    <p class="text-blue-200 text-sm mt-2"><i class="fas fa-map-marker-alt mr-2"></i> Sungai Petani, Kedah</p>
                </div>
                <div class="flex justify-center md:justify-end gap-6 text-2xl">
                    <a href="#" class="text-blue-400 hover:text-white transition transform hover:scale-125"><i class="fab fa-facebook"></i></a>
                    <a href="#" class="text-blue-400 hover:text-white transition transform hover:scale-125"><i class="fab fa-instagram"></i></a>
                    <a href="#" class="text-blue-400 hover:text-white transition transform hover:scale-125"><i class="fab fa-whatsapp"></i></a>
                </div>
            </div>
            <div class="border-t border-blue-900 pt-8 text-center text-xs text-blue-400">
                <p>&copy; 2025 ZACHS Car Rental. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Scroll Reveal logic
        const observerOptions = { threshold: 0.15 };
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) entry.target.classList.add('active');
            });
        }, observerOptions);
        document.querySelectorAll('.reveal, .reveal-left').forEach(el => observer.observe(el));

        // FAQ Toggle Logic
        function toggleFAQ(button) {
            const item = button.parentElement;
            const isActive = item.classList.contains('active');
            
            // Close all other FAQs
            document.querySelectorAll('.faq-item').forEach(otherItem => {
                if (otherItem !== item) otherItem.classList.remove('active');
            });

            // Toggle current FAQ
            item.classList.toggle('active');
        }
    </script>
</body>
</html>
