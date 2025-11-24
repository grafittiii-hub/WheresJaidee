Click the title "Where's Jaidee" to refresh the game page!!


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>Where's Jaidee</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Fredoka+One:wght@400&family=Inter:wght@400;500;600;700&display=swap');
        
        .game-font {
            font-family: 'Fredoka One', cursive;
        }
        
        .mascot {
            position: absolute;
            width: 35px;
            height: 35px;
            cursor: pointer;
            transition: all 0.3s ease;
            z-index: 10;
            touch-action: manipulation;
        }
        
        .mascot:hover, .mascot:active {
            transform: scale(1.2);
        }
        
        .found-mascot {
            animation: bounce 0.6s ease;
        }
        
        .wrong-click {
            position: absolute;
            font-size: 25px;
            animation: wrongPulse 2s ease-out forwards;
            z-index: 20;
            pointer-events: none;
        }
        
        .heart {
            transition: all 0.3s ease;
        }
        
        .heart.lost {
            opacity: 0.3;
            transform: scale(0.8);
        }
        
        @keyframes bounce {
            0%, 20%, 53%, 80%, 100% {
                transform: translateY(0);
            }
            40%, 43% {
                transform: translateY(-30px);
            }
            70% {
                transform: translateY(-15px);
            }
            90% {
                transform: translateY(-4px);
            }
        }
        
        @keyframes wrongPulse {
            0% {
                transform: scale(0);
                opacity: 1;
            }
            50% {
                transform: scale(1.2);
                opacity: 1;
            }
            100% {
                transform: scale(1);
                opacity: 0;
            }
        }
        
        @keyframes modalSlideIn {
            from {
                transform: scale(0.7);
                opacity: 0;
            }
            to {
                transform: scale(1);
                opacity: 1;
            }
        }
        
        .modal-enter {
            animation: modalSlideIn 0.3s ease-out;
        }
        
        @keyframes victoryGlow {
            0%, 100% {
                /* You can change these colors! Examples:
                   Gold: rgba(255, 215, 0, ...)
                   Blue: rgba(59, 130, 246, ...)
                   Purple: rgba(147, 51, 234, ...)
                   Pink: rgba(236, 72, 153, ...)
                */
                box-shadow: 0 0 20px rgba(34, 197, 94, 0.3), 0 0 40px rgba(34, 197, 94, 0.2), 0 0 60px rgba(34, 197, 94, 0.1);
                border-color: rgba(34, 197, 94, 0.5);
            }
            50% {
                box-shadow: 0 0 30px rgba(34, 197, 94, 0.6), 0 0 60px rgba(34, 197, 94, 0.4), 0 0 90px rgba(34, 197, 94, 0.2);
                border-color: rgba(34, 197, 94, 0.8);
            }
        }
        
        @keyframes rainbowGlow {
            0% {
                box-shadow: 0 0 60px rgba(239, 68, 68, 1), 0 0 120px rgba(239, 68, 68, 0.8), 0 0 180px rgba(239, 68, 68, 0.6);
                border-color: rgba(239, 68, 68, 1);
                filter: brightness(1.1) saturate(1.2);
            }
            16.66% {
                box-shadow: 0 0 60px rgba(249, 115, 22, 1), 0 0 120px rgba(249, 115, 22, 0.8), 0 0 180px rgba(249, 115, 22, 0.6);
                border-color: rgba(249, 115, 22, 1);
                filter: brightness(1.1) saturate(1.2);
            }
            33.33% {
                box-shadow: 0 0 60px rgba(234, 179, 8, 1), 0 0 120px rgba(234, 179, 8, 0.8), 0 0 180px rgba(234, 179, 8, 0.6);
                border-color: rgba(234, 179, 8, 1);
                filter: brightness(1.1) saturate(1.2);
            }
            50% {
                box-shadow: 0 0 60px rgba(34, 197, 94, 1), 0 0 120px rgba(34, 197, 94, 0.8), 0 0 180px rgba(34, 197, 94, 0.6);
                border-color: rgba(34, 197, 94, 1);
                filter: brightness(1.1) saturate(1.2);
            }
            66.66% {
                box-shadow: 0 0 60px rgba(59, 130, 246, 1), 0 0 120px rgba(59, 130, 246, 0.8), 0 0 180px rgba(59, 130, 246, 0.6);
                border-color: rgba(59, 130, 246, 1);
                filter: brightness(1.1) saturate(1.2);
            }
            83.33% {
                box-shadow: 0 0 60px rgba(147, 51, 234, 1), 0 0 120px rgba(147, 51, 234, 0.8), 0 0 180px rgba(147, 51, 234, 0.6);
                border-color: rgba(147, 51, 234, 1);
                filter: brightness(1.1) saturate(1.2);
            }
            100% {
                box-shadow: 0 0 60px rgba(239, 68, 68, 1), 0 0 120px rgba(239, 68, 68, 0.8), 0 0 180px rgba(239, 68, 68, 0.6);
                border-color: rgba(239, 68, 68, 1);
                filter: brightness(1.1) saturate(1.2);
            }
        }
        
        @keyframes victoryGlowYellow {
            0%, 100% {
                box-shadow: 0 0 20px rgba(234, 179, 8, 0.3), 0 0 40px rgba(234, 179, 8, 0.2), 0 0 60px rgba(234, 179, 8, 0.1);
                border-color: rgba(234, 179, 8, 0.5);
            }
            50% {
                box-shadow: 0 0 30px rgba(234, 179, 8, 0.6), 0 0 60px rgba(234, 179, 8, 0.4), 0 0 90px rgba(234, 179, 8, 0.2);
                border-color: rgba(234, 179, 8, 0.8);
            }
        }
        
        .victory-glow {
            border: 3px solid transparent;
            animation: victoryGlow 2s ease-in-out infinite;
        }
        
        .victory-glow-yellow {
            border: 3px solid transparent;
            animation: victoryGlowYellow 2s ease-in-out infinite;
        }
        
        .rainbow-glow {
            border: 3px solid transparent;
            animation: rainbowGlow 3s linear infinite;
        }
        
        @keyframes celebrationPulse {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
        }
        
        .celebration-pulse {
            animation: celebrationPulse 1s ease-in-out infinite;
        }
        
        @keyframes swing {
            0%, 100% {
                transform: rotate(0deg);
                transform-origin: top center;
            }
            10% {
                transform: rotate(3deg);
                transform-origin: top center;
            }
            30% {
                transform: rotate(-2deg);
                transform-origin: top center;
            }
            50% {
                transform: rotate(1deg);
                transform-origin: top center;
            }
            70% {
                transform: rotate(-0.5deg);
                transform-origin: top center;
            }
            90% {
                transform: rotate(0.2deg);
                transform-origin: top center;
            }
        }
        
        .swinging-title {
            animation: swing 3s ease-in-out infinite;
            transform-origin: top center;
        }
        
        .game-map-container {
            width: 100%;
            overflow-x: auto;
            overflow-y: auto;
            border-radius: 12px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }
        
        .game-map {
            position: relative;
            background-size: cover;
            background-position: center top;
            background-repeat: no-repeat;
            width: 200vw; /* Make wider for horizontal scrolling */
            min-width: 800px;
            aspect-ratio: 1; /* Since the maps are square */
            touch-action: pan-x pan-y pinch-zoom;
        }
        
        @media (max-width: 768px) {
            .game-map {
                width: 250vw; /* Even wider on mobile for more exploration */
                min-width: 100vh; /* Use viewport height as minimum width for square aspect */
            }
            
            .game-map-container {
                max-height: 90vh; /* Allow more vertical space on mobile */
            }
        }
        
        @media (max-width: 480px) {
            .game-map {
                width: 300vw; /* Maximum width for small phones */
            }
        }
        
        .map-button {
            transition: all 0.3s ease;
        }
        
        .map-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }
        
        .map-button.locked {
            opacity: 0.6;
            cursor: not-allowed;
        }
        
        .map-button.locked:hover {
            transform: none;
            box-shadow: none;
        }

        /* Dark mode support */
        .dark {
            color-scheme: dark;
        }

        /* Unified typography */
        body {
            font-family: 'Inter', sans-serif;
        }
        
        .game-title, .page-title {
            font-family: 'Fredoka One', cursive;
        }
        
        /* Unified color scheme */
        .text-primary {
            color: #5D5CDE;
        }
        
        .dark .text-primary {
            color: #7C7BF0;
        }
        
        .bg-primary {
            background-color: #5D5CDE;
        }
        
        .bg-primary:hover {
            background-color: #4F4EC7;
        }
        
        .dark .bg-primary {
            background-color: #7C7BF0;
        }
        
        .dark .bg-primary:hover {
            background-color: #6B6AE8;
        }
        
        /* Floating mascot animation */
        .floating-mascot {
            position: fixed;
            pointer-events: none;
            z-index: 15;
            opacity: 0;
            transition: opacity 0.5s ease-in-out;
        }
        
        .floating-mascot.visible {
            opacity: 0.8;
        }
        
        @keyframes float {
            0%, 100% {
                transform: translateY(0px) rotate(0deg);
            }
            50% {
                transform: translateY(-10px) rotate(5deg);
            }
        }
        
        .floating-mascot.floating {
            animation: float 3s ease-in-out infinite;
        }

        /* Enhanced game header */
        .game-header {
            background: linear-gradient(135deg, #FCD34D 0%, #10B981 70%);
            box-shadow: 0 4px 20px rgba(16, 185, 129, 0.3);
        }
        
        .dark .game-header {
            background: linear-gradient(135deg, #F59E0B 0%, #059669 70%);
            box-shadow: 0 4px 20px rgba(5, 150, 105, 0.4);
        }
        
        .stats-card {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .game-controls {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(0, 0, 0, 0.1);
        }
        
        .dark .game-controls {
            background: rgba(31, 41, 55, 0.95);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Hint glow effect */
        @keyframes hintGlow {
            0%, 100% {
                box-shadow: 0 0 10px rgba(255, 215, 0, 0.4), 0 0 20px rgba(255, 215, 0, 0.3), 0 0 30px rgba(255, 215, 0, 0.2);
                filter: brightness(1.2);
            }
            50% {
                box-shadow: 0 0 20px rgba(255, 215, 0, 0.8), 0 0 40px rgba(255, 215, 0, 0.6), 0 0 60px rgba(255, 215, 0, 0.4);
                filter: brightness(1.5);
            }
        }
        
        .hint-glow {
            animation: hintGlow 2s ease-in-out infinite;
            border-radius: 50%;
        }
        
        /* Confetti animation for map 9 completion */
        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            background: #f0f0f0;
            animation: confettiFall 2.5s linear forwards;
            z-index: 100;
        }
        
        @keyframes confettiFall {
            0% {
                transform: translateY(-50px) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(720deg);
                opacity: 0;
            }
        }
        
        .confetti:nth-child(1) { left: 10%; animation-delay: 0s; background: #ff6b6b; }
        .confetti:nth-child(2) { left: 20%; animation-delay: 0.1s; background: #4ecdc4; }
        .confetti:nth-child(3) { left: 30%; animation-delay: 0.2s; background: #45b7d1; }
        .confetti:nth-child(4) { left: 40%; animation-delay: 0.3s; background: #96ceb4; }
        .confetti:nth-child(5) { left: 50%; animation-delay: 0.4s; background: #feca57; }
        .confetti:nth-child(6) { left: 60%; animation-delay: 0.5s; background: #ff9ff3; }
        .confetti:nth-child(7) { left: 70%; animation-delay: 0.6s; background: #54a0ff; }
        .confetti:nth-child(8) { left: 80%; animation-delay: 0.7s; background: #5f27cd; }
        .confetti:nth-child(9) { left: 90%; animation-delay: 0.8s; background: #00d2d3; }
        .confetti:nth-child(10) { left: 5%; animation-delay: 0.9s; background: #ff6348; }
        .confetti:nth-child(11) { left: 15%; animation-delay: 1s; background: #1dd1a1; }
        .confetti:nth-child(12) { left: 25%; animation-delay: 1.1s; background: #feca57; }
        .confetti:nth-child(13) { left: 35%; animation-delay: 1.2s; background: #48dbfb; }
        .confetti:nth-child(14) { left: 45%; animation-delay: 1.3s; background: #ff9ff3; }
        .confetti:nth-child(15) { left: 55%; animation-delay: 1.4s; background: #54a0ff; }
    </style>
</head>
<body class="bg-white dark:bg-gray-900 text-gray-900 dark:text-white transition-colors duration-300">
    <!-- Homepage -->
    <div id="homepage" class="min-h-screen flex flex-col items-center justify-center bg-gradient-to-br from-yellow-400 via-yellow-300 to-green-500 p-4">
        <div class="text-center max-w-lg mx-auto">
            <h1 class="text-4xl md:text-6xl font-bold text-white mb-4 game-font drop-shadow-lg swinging-title">
                Where's Jaidee?
            </h1>
            <p class="text-lg md:text-xl text-white mb-4 font-medium drop-shadow-lg">
                Find all the hidden Jaidee mascots!
            </p>
            
            <div class="text-white text-sm md:text-base space-y-2 mb-6">
                <p class="flex items-center justify-center gap-2 drop-shadow-md font-bold">
                    <span>🎯</span> Find all 10 hidden Jaidee
                </p>
                <p class="flex items-center justify-center gap-2 drop-shadow-md font-bold">
                    <span> 🤏🏻 </span> Swipe to explore & pinch to zoom
                </p>      
            </div>
            
            <!-- Help and Language Buttons -->
            <div class="mb-6 flex items-center justify-center gap-3">
                <button id="help-btn" class="bg-white bg-opacity-20 hover:bg-opacity-30 text-black px-3 py-1.5 rounded-lg text-sm font-medium transition-all duration-200 backdrop-blur-sm border border-white border-opacity-20 flex items-center gap-1.5">
                    <span class="text-base">❓</span>
                    <span data-translate="helpButton">How to Play</span>
                </button>
                
                <button id="language-btn" class="bg-white bg-opacity-20 hover:bg-opacity-30 text-black px-3 py-1.5 rounded-lg text-sm font-medium transition-all duration-200 backdrop-blur-sm border border-white border-opacity-20 flex items-center gap-1.5">
                    <span class="text-base">🌐</span>
                    <span id="current-language">EN</span>
                </button>
            </div>
            
            <!-- Map Selection -->
            <div class="grid grid-cols-2 md:grid-cols-3 gap-3 mb-6 w-full">
                <button id="map1-btn" class="map-button bg-white rounded-lg p-3 shadow-xl" aria-label="Play Playground map - Swings and slides scene">
                    <div class="aspect-square bg-gray-200 rounded-lg mb-2 overflow-hidden relative">
                        <div class="w-full h-full bg-cover bg-center" style="background-image: url('https://pfst.cf2.poecdn.net/base/image/0647053d2306ae08b70433b423fc95863e0da936baed09ac2a3cd2fbf5b4736f?w=1024&h=1024'); background-position: 20% 30%;"></div>
                        <div class="absolute inset-0 bg-black bg-opacity-20 flex items-center justify-center">
                            <span class="text-white text-lg font-bold drop-shadow-lg" aria-hidden="true">🏞️</span>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Playground</h3>
                    <p class="text-xs text-gray-600">Swings & slides</p>
                </button>
                
                <button id="map2-btn" class="map-button bg-white rounded-lg p-3 shadow-xl locked">
                    <div class="aspect-square bg-gray-200 rounded-lg mb-2 overflow-hidden relative">
                        <div class="w-full h-full bg-cover bg-center" style="background-image: url('https://pfst.cf2.poecdn.net/base/image/1bdb30aefd94fed744d86493dec60da8bb8f00c552a47c3378f72e04aff07428?w=894&h=894'); background-position: center 30%;"></div>
                        <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center">
                            <span class="text-white text-xl">🔒</span>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Concert</h3>
                    <p class="text-xs text-gray-600">Locked</p>
                </button>
                
                <button id="map3-btn" class="map-button bg-white rounded-lg p-3 shadow-xl locked">
                    <div class="aspect-square bg-gray-200 rounded-lg mb-2 overflow-hidden relative">
                        <div class="w-full h-full bg-cover bg-center" style="background-image: url('https://pfst.cf2.poecdn.net/base/image/31ac576fc610f531d9d9a11b25aa3e519858e86ba0ac524fbd0f32c922c73aa4?w=1024&h=1024'); background-position: center 30%;"></div>
                        <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center">
                            <span class="text-white text-xl">🔒</span>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Playground 2</h3>
                    <p class="text-xs text-gray-600">Locked</p>
                </button>
                
                <button id="map4-btn" class="map-button bg-white rounded-lg p-3 shadow-xl locked">
                    <div class="aspect-square bg-gray-200 rounded-lg mb-2 overflow-hidden relative">
                        <div class="w-full h-full bg-cover bg-center" style="background-image: url('https://pfst.cf2.poecdn.net/base/image/9dd0bdb002fdeff2f704e3d250fa49e951d3b414f1fdbdb0df14b0d8d6794e1f?w=2048&h=2048'); background-position: center 30%;"></div>
                        <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center">
                            <span class="text-white text-xl">🔒</span>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Comic Story</h3>
                    <p class="text-xs text-gray-600">Locked</p>
                </button>
                
                <button id="map5-btn" class="map-button bg-white rounded-lg p-3 shadow-xl locked">
                    <div class="aspect-square bg-gray-200 rounded-lg mb-2 overflow-hidden relative">
                        <div class="w-full h-full bg-cover bg-center" style="background-image: url('https://pfst.cf2.poecdn.net/base/image/041b02ba7e4482a56fced686f865c66969a827c53d30aa1148b25e6173cc8950?w=905&h=1023'); background-position: center 30%;"></div>
                        <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center">
                            <span class="text-white text-xl">🔒</span>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Stage</h3>
                    <p class="text-xs text-gray-600">Locked</p>
                </button>
                
                <button id="map6-btn" class="map-button bg-white rounded-lg p-3 shadow-xl locked">
                    <div class="aspect-square bg-gray-200 rounded-lg mb-2 overflow-hidden relative">
                        <div class="w-full h-full bg-cover bg-center" style="background-image: url('https://pfst.cf2.poecdn.net/base/image/341976336e5d81635800004d197315ffa74915ee201bb96e384bf139fe3348e7?w=1024&h=1024'); background-position: center 30%;"></div>
                        <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center">
                            <span class="text-white text-xl">🔒</span>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Carnival</h3>
                    <p class="text-xs text-gray-600">Locked</p>
                </button>
                
                <button id="map7-btn" class="map-button bg-white rounded-lg p-3 shadow-xl locked">
                    <div class="aspect-square bg-gray-200 rounded-lg mb-2 overflow-hidden relative">
                        <div class="w-full h-full bg-cover bg-center" style="background-image: url('https://pfst.cf2.poecdn.net/base/image/2cdf3437ab490275a31664ef5abdae106e16f9d07e4fa6c1ce882fb986ad438c?w=1024&h=1024'); background-position: center 30%;"></div>
                        <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center">
                            <span class="text-white text-xl">🔒</span>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Market</h3>
                    <p class="text-xs text-gray-600">Locked</p>
                </button>
                
                <button id="map8-btn" class="map-button bg-white rounded-lg p-3 shadow-xl locked">
                    <div class="aspect-square bg-gray-200 rounded-lg mb-2 overflow-hidden relative">
                        <div class="w-full h-full bg-cover bg-center" style="background-image: url('https://pfst.cf2.poecdn.net/base/image/aae2c970cd37bd1a8d9806291788c742aa5914efbb8aff25e03678f06a504f20?w=1024&h=1024'); background-position: center 30%;"></div>
                        <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center">
                            <span class="text-white text-xl">🔒</span>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Restaurant</h3>
                    <p class="text-xs text-gray-600">Locked</p>
                </button>
                
                <button id="map9-btn" class="map-button bg-white rounded-lg p-3 shadow-xl locked">
                    <div class="aspect-square bg-gray-200 rounded-lg mb-2 overflow-hidden relative">
                        <div class="w-full h-full bg-cover bg-center" style="background-image: url('https://pfst.cf2.poecdn.net/base/image/290beeb6437b70c24a16973426680a988a84c7edf9ef78dbdde0207e654c7352?w=896&h=1152'); background-position: center 30%;"></div>
                        <div class="absolute inset-0 bg-black bg-opacity-60 flex items-center justify-center">
                            <span class="text-white text-xl">🔒</span>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Concert Hall</h3>
                    <p class="text-xs text-gray-600">Locked</p>
                </button>
                
                <button id="sudoku-btn" class="map-button bg-white rounded-lg p-3 shadow-xl border-2 border-purple-300 hover:border-purple-400">
                    <div class="aspect-square bg-gradient-to-br from-purple-100 to-pink-100 rounded-lg mb-2 overflow-hidden relative flex items-center justify-center">
                        <div class="text-center">
                            <div class="text-3xl mb-1">🧩</div>
                            <div class="text-xs font-bold text-purple-600">SUDOKU</div>
                        </div>
                    </div>
                    <h3 class="text-sm font-bold text-gray-800 mb-1">Try Sudoku</h3>
                    <p class="text-xs text-purple-600 font-medium">External Game</p>
                </button>
            </div>
            
            <!-- Spacer for footer -->
            <div class="h-16"></div>
        </div>
    </div>

    <!-- Loading Screen -->
    <div id="loading-screen" class="fixed inset-0 bg-gradient-to-br from-yellow-400 to-green-600 flex items-center justify-center z-50 hidden">
        <!-- Back Button -->
        <button id="loading-back-btn" class="absolute top-4 left-4 bg-white bg-opacity-20 hover:bg-opacity-30 text-white px-4 py-2 rounded-xl font-semibold transition-all duration-200 backdrop-blur-sm border border-white border-opacity-20 flex items-center gap-2">
            <span class="text-lg">←</span>
            <span class="hidden sm:inline">Back</span>
        </button>
        
        <!-- Reload Button -->
        <button id="loading-reload-btn" class="absolute top-4 right-4 bg-white bg-opacity-20 hover:bg-opacity-30 text-white px-4 py-2 rounded-xl font-semibold transition-all duration-200 backdrop-blur-sm border border-white border-opacity-20 flex items-center gap-2">
            <span class="text-lg">🔄</span>
            <span class="hidden sm:inline">Reload</span>
        </button>
        
        <div class="text-center text-white">
            <div class="mb-6">
                <div class="w-16 h-16 border-4 border-white border-t-transparent rounded-full animate-spin mx-auto mb-4"></div>
                <h3 class="text-2xl font-bold game-font mb-2">Preparing the Hunt...</h3>
                <p id="loading-text" class="text-lg opacity-90">Loading map...</p>
            </div>
            <div class="w-64 bg-white bg-opacity-20 rounded-full h-2 mx-auto">
                <div id="loading-progress" class="bg-white h-2 rounded-full transition-all duration-300" style="width: 0%"></div>
            </div>
            <p id="loading-percentage" class="text-sm mt-2 opacity-75">0%</p>
        </div>
    </div>

    <!-- Game Screen -->
    <div id="gamescreen" class="hidden min-h-screen bg-gray-100 dark:bg-gray-800">
        <!-- Game Header -->
        <div class="game-header text-white p-2 md:p-3">
            <div class="flex justify-between items-center">
                <!-- Back Button -->
                <button id="back-btn" class="bg-white bg-opacity-20 hover:bg-opacity-30 text-grey px-4 py-2 rounded-xl font-semibold transition-all duration-200 backdrop-blur-sm border border-white border-opacity-20 flex items-center gap-2">
                    <span class="text-lg">←</span>
                    <span class="hidden sm:inline">Back</span>
                </button>
                
                <!-- Game Title & Progress -->
                <div class="text-center flex-1 mx-4">
                    <h2 class="text-xl md:text-3xl font-bold game-title text-white drop-shadow-lg">Where's Jaidee?</h2>
                    <div class="flex items-center justify-center gap-4 mt-2">
                        <!-- Progress Stats -->
                        <div class="stats-card px-3 py-1 rounded-lg">
                            <div class="flex items-center gap-2">
                                <span class="text-lg">🎯</span>
                                <span class="font-semibold">
                                    <span id="found-count" class="text-yellow-200">0</span>
                                    <span class="text-white opacity-70">/10</span>
                                </span>
                            </div>
                        </div>
                        
                        <!-- Lives Display -->
                        <div class="stats-card px-3 py-1 rounded-lg">
                            <div class="flex items-center gap-1">
                                <span class="text-sm font-medium text-white opacity-70 hidden sm:inline">Lives:</span>
                                <div id="hearts" class="flex space-x-1">
                                    <span class="heart text-red-300 text-lg transition-all duration-300">❤️</span>
                                    <span class="heart text-red-300 text-lg transition-all duration-300">❤️</span>
                                    <span class="heart text-red-300 text-lg transition-all duration-300">❤️</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Current Map Indicator -->
                <div class="stats-card px-3 py-2 rounded-lg text-center min-w-[60px]">
                    <div class="text-xs text-white opacity-70 font-medium">Map</div>
                    <div id="current-map" class="text-lg font-bold text-yellow-200">1</div>
                </div>
            </div>
        </div>

        <!-- Controls Bar -->
        <div class="bg-white dark:bg-gray-900 border-t dark:border-gray-700 p-3">
            <div class="flex justify-between items-center max-w-4xl mx-auto">
                <!-- Zoom Controls -->
                <div class="flex items-center space-x-3 bg-gray-50 dark:bg-gray-800 rounded-xl p-2 shadow-sm">
                    <div class="flex items-center space-x-1">
                        <span class="text-xs text-gray-600 dark:text-gray-400 font-medium hidden sm:inline">🔍</span>
                        <span class="text-xs text-gray-600 dark:text-gray-400 font-medium hidden md:inline">Zoom:</span>
                    </div>
                    <button id="zoom-out" class="bg-white dark:bg-gray-700 hover:bg-gray-100 dark:hover:bg-gray-600 text-gray-700 dark:text-gray-300 w-9 h-9 rounded-lg flex items-center justify-center text-lg font-bold transition-all duration-200 shadow-sm hover:shadow-md">
                        −
                    </button>
                    <span id="zoom-level" class="text-sm text-gray-700 dark:text-gray-300 min-w-[3rem] text-center font-semibold">100%</span>
                    <button id="zoom-in" class="bg-white dark:bg-gray-700 hover:bg-gray-100 dark:hover:bg-gray-600 text-gray-700 dark:text-gray-300 w-9 h-9 rounded-lg flex items-center justify-center text-lg font-bold transition-all duration-200 shadow-sm hover:shadow-md">
                        +
                    </button>
                    <div class="w-px h-6 bg-gray-300 dark:bg-gray-600"></div>
                    <button id="zoom-reset" class="bg-blue-500 hover:bg-blue-600 dark:bg-blue-600 dark:hover:bg-blue-500 text-white px-3 py-2 rounded-lg text-xs font-semibold transition-all duration-200 shadow-sm hover:shadow-md">
                        Reset
                    </button>
                </div>
                
                <!-- Hint System -->
                <div class="flex items-center">
                    <button id="hint-btn" class="bg-gradient-to-r from-yellow-500 to-yellow-600 hover:from-yellow-600 hover:to-yellow-700 disabled:from-gray-400 disabled:to-gray-500 disabled:cursor-not-allowed text-white px-4 py-2.5 rounded-xl text-sm font-semibold transition-all duration-200 shadow-lg hover:shadow-xl disabled:shadow-sm flex items-center space-x-2">
                        <span class="text-lg">💡</span>
                        <span class="hidden sm:inline">Hint</span>
                        <span class="bg-white bg-opacity-20 text-xs px-2 py-0.5 rounded-full">
                            <span id="hints-remaining">3</span>
                        </span>
                    </button>
                </div>
            </div>
        </div>

        <!-- Game Map Container -->
        <div class="p-2 md:p-4 pb-12">
            <div class="game-map-container">
                <div id="game-map" class="game-map"></div>
            </div>
        </div>
    </div>

    <!-- Victory Modal -->
    <div id="victory-modal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white dark:bg-gray-800 rounded-2xl p-6 md:p-8 max-w-sm md:max-w-md w-full mx-4 text-center modal-enter">
            <div class="text-4xl md:text-6xl mb-3 md:mb-4">🎉</div>
            <h3 class="text-2xl md:text-3xl font-bold mb-3 md:mb-4 text-green-600 game-font">Victory!</h3>
            <p class="text-base md:text-lg mb-4 md:mb-6 text-gray-700 dark:text-gray-300">
                Congratulations! You found all the Jaidee mascots!
            </p>
            <div id="unlock-message" class="hidden bg-yellow-100 dark:bg-yellow-900 p-3 md:p-4 rounded-lg mb-4 md:mb-6">
                <p class="text-sm md:text-base text-yellow-800 dark:text-yellow-200 font-medium">
                    🔓 New map unlocked!
                </p>
            </div>
            <button id="victory-continue" class="bg-green-500 hover:bg-green-600 text-white px-6 py-3 rounded-lg font-medium transition-colors text-base">
                Continue
            </button>
        </div>
    </div>

    <!-- Game Over Modal -->
    <div id="gameover-modal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white dark:bg-gray-800 rounded-2xl p-6 md:p-8 max-w-sm md:max-w-md w-full mx-4 text-center modal-enter">
            <div class="text-4xl md:text-6xl mb-3 md:mb-4">💔</div>
            <h3 class="text-2xl md:text-3xl font-bold mb-3 md:mb-4 text-red-600 game-font">Game Over!</h3>
            <p class="text-base md:text-lg mb-4 md:mb-6 text-gray-700 dark:text-gray-300">
                Better luck next time! You found <span id="final-count">0</span> out of 10 mascots.
            </p>
            <div class="flex flex-col sm:flex-row gap-3 justify-center">
                <button id="gameover-retry" class="bg-blue-500 hover:bg-blue-600 text-white px-6 py-3 rounded-lg font-medium transition-colors text-base">
                    Try Again
                </button>
                <button id="gameover-menu" class="bg-gray-500 hover:bg-gray-600 text-white px-6 py-3 rounded-lg font-medium transition-colors text-base">
                    Main Menu
                </button>
            </div>
        </div>
    </div>

    <!-- Help Modal -->
    <div id="help-modal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white dark:bg-gray-800 rounded-2xl p-6 md:p-8 max-w-md w-full mx-4 modal-enter">
            <div class="text-center mb-6">
                <div class="text-4xl mb-3">🎯</div>
                <h3 class="text-2xl font-bold text-gray-800 dark:text-white game-font">How to Play</h3>
            </div>
            
            <div class="space-y-4 text-left">
                <div class="flex items-start gap-3">
                    <span class="text-xl">🔍</span>
                    <div>
                        <h4 class="font-semibold text-gray-800 dark:text-white">Find the Hidden Jaidee</h4>
                        <p class="text-sm text-gray-600 dark:text-gray-300">Look for 10 hidden Jaidee mascots on each map. Click on them to find them!</p>
                    </div>
                </div>
                
                <div class="flex items-start gap-3">
                    <span class="text-xl">🤏</span>
                    <div>
                        <h4 class="font-semibold text-gray-800 dark:text-white">Navigate & Zoom</h4>
                        <p class="text-sm text-gray-600 dark:text-gray-300">Swipe to explore the map. Pinch to zoom in/out or use the zoom controls. Use the reset button to return to default view.</p>
                    </div>
                </div>
                
                <div class="flex items-start gap-3">
                    <span class="text-xl">❤️</span>
                    <div>
                        <h4 class="font-semibold text-gray-800 dark:text-white">Lives System</h4>
                        <p class="text-sm text-gray-600 dark:text-gray-300">You have 3 lives. Clicking in the wrong place will cost you a life. Game over when you run out!</p>
                    </div>
                </div>
                
                <div class="flex items-start gap-3">
                    <span class="text-xl">💡</span>
                    <div>
                        <h4 class="font-semibold text-gray-800 dark:text-white">Hints Available</h4>
                        <p class="text-sm text-gray-600 dark:text-gray-300">Use up to 3 hints per map. A hint will highlight one hidden mascot and scroll to show it.</p>
                    </div>
                </div>
                
                <div class="flex items-start gap-3">
                    <span class="text-xl">🏆</span>
                    <div>
                        <h4 class="font-semibold text-gray-800 dark:text-white">Unlock New Maps</h4>
                        <p class="text-sm text-gray-600 dark:text-gray-300">Complete maps to unlock new ones. Find all 10 mascots to victory!</p>
                    </div>
                </div>
            </div>
            
            <div class="mt-6 text-center">
                <button id="help-close" class="bg-primary hover:bg-primary/90 text-white px-6 py-3 rounded-lg font-medium transition-colors">
                    Got it!
                </button>
            </div>
        </div>
    </div>

    <script>
        // Dark mode detection with obfuscation
        (function(){
            var _0x1a2b=window.matchMedia&&window.matchMedia('(prefers-color-scheme: dark)');
            if(_0x1a2b&&_0x1a2b.matches){document.documentElement.classList.add('dark')}
            _0x1a2b&&_0x1a2b.addEventListener('change',function(_0x3c4d){
                _0x3c4d.matches?document.documentElement.classList.add('dark'):document.documentElement.classList.remove('dark')
            })
        })();

        // Game state with obfuscated property names but keeping object name for compatibility
        let gameState = {
            currentMap: 1,
            lives: 3,
            foundCount: 0,
            totalMascots: 10,
            mascots: [],
            unlockedMaps: {1: true, 2: false, 3: false, 4: false, 5: false, 6: false, 7: false, 8: false, 9: false},
            zoomLevel: 0.5,
            minZoom: 0.5,
            maxZoom: 1.5,
            baseZoom: 0.5,
            hintsUsed: 0,
            maxHints: 3,
            isGameActive: false,
            isTransitioning: false,
            lastClickTime: 0,
            clickCooldown: 100,
            gameStartTime: 0,
            debugMode: false
        };

        // Simplified asset protection (minimal, non-intrusive)
        const SecurityManager = {
            init() {
                // Only basic asset protection to prevent drag/drop
                this.setupBasicAssetProtection();
            },
            
            setupBasicAssetProtection() {
                // Prevent right-click context menu on game images only
                document.addEventListener('contextmenu', (e) => {
                    if (e.target.tagName === 'IMG' && e.target.classList.contains('mascot')) {
                        e.preventDefault();
                    }
                }, false);
                
                // Prevent drag and drop of game images only
                document.addEventListener('dragstart', (e) => {
                    if (e.target.tagName === 'IMG' && (e.target.classList.contains('mascot') || e.target.classList.contains('floating-mascot'))) {
                        e.preventDefault();
                    }
                }, false);
            }
        };

        // Protection and debugging utilities
        const AppProtection = {
            // Rate limiting for user actions
            isActionAllowed(actionType = 'general') {
                const now = Date.now();
                const timeSinceLastClick = now - gameState.lastClickTime;
                
                if (timeSinceLastClick < gameState.clickCooldown) {
                    this.log(`Rate limit exceeded for action: ${actionType}`, 'warn');
                    return false;
                }
                
                gameState.lastClickTime = now;
                return true;
            },

            // Safe element access
            getElement(id, required = true) {
                try {
                    const element = document.getElementById(id);
                    if (!element && required) {
                        this.log(`Required element not found: ${id}`, 'error');
                        return null;
                    }
                    return element;
                } catch (error) {
                    this.log(`Error accessing element ${id}: ${error.message}`, 'error');
                    return null;
                }
            },

            // Safe DOM manipulation
            safeSetContent(element, content, isHTML = false) {
                try {
                    if (!element) return false;
                    if (isHTML) {
                        element.innerHTML = content;
                    } else {
                        element.textContent = content;
                    }
                    return true;
                } catch (error) {
                    this.log(`Error setting content: ${error.message}`, 'error');
                    return false;
                }
            },

            // Memory cleanup tracker
            activeTimeouts: new Set(),
            activeIntervals: new Set(),
            activeEventListeners: new Map(),

            // Safe timeout with tracking
            setTimeout(callback, delay, ...args) {
                try {
                    const timeoutId = setTimeout(() => {
                        this.activeTimeouts.delete(timeoutId);
                        callback(...args);
                    }, delay);
                    this.activeTimeouts.add(timeoutId);
                    return timeoutId;
                } catch (error) {
                    this.log(`Error setting timeout: ${error.message}`, 'error');
                    return null;
                }
            },

            // Safe interval with tracking
            setInterval(callback, interval, ...args) {
                try {
                    const intervalId = setInterval(() => {
                        callback(...args);
                    }, interval);
                    this.activeIntervals.add(intervalId);
                    return intervalId;
                } catch (error) {
                    this.log(`Error setting interval: ${error.message}`, 'error');
                    return null;
                }
            },

            // Cleanup all timeouts and intervals
            cleanup() {
                try {
                    this.activeTimeouts.forEach(id => clearTimeout(id));
                    this.activeIntervals.forEach(id => clearInterval(id));
                    this.activeTimeouts.clear();
                    this.activeIntervals.clear();
                    this.log('Cleanup completed', 'info');
                } catch (error) {
                    this.log(`Error during cleanup: ${error.message}`, 'error');
                }
            },

            // Enhanced logging with levels
            log(message, level = 'info') {
                if (!gameState.debugMode && level === 'debug') return;
                
                const timestamp = new Date().toISOString();
                const prefix = `[WhereJaidee ${level.toUpperCase()}] ${timestamp}:`;
                
                switch (level) {
                    case 'error':
                        console.error(prefix, message);
                        break;
                    case 'warn':
                        console.warn(prefix, message);
                        break;
                    case 'debug':
                        console.debug(prefix, message);
                        break;
                    default:
                        console.log(prefix, message);
                }
            },

            // Validate game state integrity
            validateGameState() {
                try {
                    const issues = [];
                    
                    if (gameState.lives < 0 || gameState.lives > 3) {
                        issues.push(`Invalid lives count: ${gameState.lives}`);
                        gameState.lives = Math.max(0, Math.min(3, gameState.lives));
                    }
                    
                    if (gameState.foundCount < 0 || gameState.foundCount > gameState.totalMascots) {
                        issues.push(`Invalid found count: ${gameState.foundCount}`);
                        gameState.foundCount = Math.max(0, Math.min(gameState.totalMascots, gameState.foundCount));
                    }
                    
                    if (gameState.currentMap < 1 || gameState.currentMap > 9) {
                        issues.push(`Invalid current map: ${gameState.currentMap}`);
                        gameState.currentMap = Math.max(1, Math.min(9, gameState.currentMap));
                    }
                    
                    if (gameState.zoomLevel < gameState.minZoom || gameState.zoomLevel > gameState.maxZoom) {
                        issues.push(`Invalid zoom level: ${gameState.zoomLevel}`);
                        gameState.zoomLevel = Math.max(gameState.minZoom, Math.min(gameState.maxZoom, gameState.zoomLevel));
                    }
                    
                    if (issues.length > 0) {
                        this.log(`Game state issues corrected: ${issues.join(', ')}`, 'warn');
                    }
                    
                    return issues.length === 0;
                } catch (error) {
                    this.log(`Error validating game state: ${error.message}`, 'error');
                    return false;
                }
            },

            // Safe audio context management
            audioContext: null,
            isAudioEnabled: true,

            getAudioContext() {
                try {
                    if (!this.isAudioEnabled) return null;
                    
                    if (!this.audioContext) {
                        this.audioContext = new (window.AudioContext || window.webkitAudioContext)();
                    }
                    
                    // Handle suspended audio context
                    if (this.audioContext.state === 'suspended') {
                        this.audioContext.resume().catch(err => {
                            this.log(`Failed to resume audio context: ${err.message}`, 'warn');
                        });
                    }
                    
                    return this.audioContext;
                } catch (error) {
                    this.log(`Audio context unavailable: ${error.message}`, 'warn');
                    this.isAudioEnabled = false;
                    return null;
                }
            },

            // Error boundary for functions
            safeExecute(fn, context = 'unknown', ...args) {
                try {
                    return fn(...args);
                } catch (error) {
                    this.log(`Error in ${context}: ${error.message}`, 'error');
                    return null;
                }
            }
        };

        // Image URLs
        const images = {
            map1: 'https://pfst.cf2.poecdn.net/base/image/0647053d2306ae08b70433b423fc95863e0da936baed09ac2a3cd2fbf5b4736f?w=1024&h=1024',
            map2: 'https://pfst.cf2.poecdn.net/base/image/1bdb30aefd94fed744d86493dec60da8bb8f00c552a47c3378f72e04aff07428?w=894&h=894',
            map3: 'https://pfst.cf2.poecdn.net/base/image/31ac576fc610f531d9d9a11b25aa3e519858e86ba0ac524fbd0f32c922c73aa4?w=1024&h=1024',
            map4: 'https://pfst.cf2.poecdn.net/base/image/9dd0bdb002fdeff2f704e3d250fa49e951d3b414f1fdbdb0df14b0d8d6794e1f?w=2048&h=2048',
            map5: 'https://pfst.cf2.poecdn.net/base/image/041b02ba7e4482a56fced686f865c66969a827c53d30aa1148b25e6173cc8950?w=905&h=1023',
            map6: 'https://pfst.cf2.poecdn.net/base/image/341976336e5d81635800004d197315ffa74915ee201bb96e384bf139fe3348e7?w=1024&h=1024',
            map7: 'https://pfst.cf2.poecdn.net/base/image/2cdf3437ab490275a31664ef5abdae106e16f9d07e4fa6c1ce882fb986ad438c?w=1024&h=1024',
            map8: 'https://pfst.cf2.poecdn.net/base/image/aae2c970cd37bd1a8d9806291788c742aa5914efbb8aff25e03678f06a504f20?w=1024&h=1024',
            map9: 'https://pfst.cf2.poecdn.net/base/image/290beeb6437b70c24a16973426680a988a84c7edf9ef78dbdde0207e654c7352?w=896&h=1152',
            mascotHidden: 'https://pfst.cf2.poecdn.net/base/image/6840a922a02fa2ca1b70d9ea6743ba899b339fd649cca25c0415330b39ef0496?w=1024&h=1024',
            mascotFound: 'https://pfst.cf2.poecdn.net/base/image/4c51c9c7ece54cd674dc510915494dfce8d5f42cdc913938ae5f92ef420d194d?w=512&h=512'
        };

        // Protected audio system with fallbacks
        function initAudio() {
            return AppProtection.safeExecute(() => {
                const context = AppProtection.getAudioContext();
                if (context) {
                    audioContext = context;
                    return true;
                }
                return false;
            }, 'initAudio');
        }

        function playBingoSound() {
            AppProtection.safeExecute(() => {
                if (!initAudio() || !audioContext) {
                    AppProtection.log('Audio not available, skipping sound', 'debug');
                    return;
                }

                const oscillator = audioContext.createOscillator();
                const gainNode = audioContext.createGain();
                
                oscillator.connect(gainNode);
                gainNode.connect(audioContext.destination);
                
                oscillator.frequency.setValueAtTime(523.25, audioContext.currentTime); // C5
                oscillator.frequency.setValueAtTime(659.25, audioContext.currentTime + 0.1); // E5
                oscillator.frequency.setValueAtTime(783.99, audioContext.currentTime + 0.2); // G5
                
                gainNode.gain.setValueAtTime(0.3, audioContext.currentTime);
                gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.5);
                
                oscillator.start(audioContext.currentTime);
                oscillator.stop(audioContext.currentTime + 0.5);
            }, 'playBingoSound');
        }

        function playWrongSound() {
            AppProtection.safeExecute(() => {
                if (!initAudio() || !audioContext) {
                    AppProtection.log('Audio not available, skipping sound', 'debug');
                    return;
                }

                const oscillator = audioContext.createOscillator();
                const gainNode = audioContext.createGain();
                
                oscillator.connect(gainNode);
                gainNode.connect(audioContext.destination);
                
                // Make the wrong sound more audible with a buzz/error sound
                oscillator.frequency.setValueAtTime(300, audioContext.currentTime);
                oscillator.frequency.setValueAtTime(250, audioContext.currentTime + 0.1);
                oscillator.frequency.setValueAtTime(200, audioContext.currentTime + 0.2);
                
                gainNode.gain.setValueAtTime(0.3, audioContext.currentTime);
                gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.4);
                
                oscillator.start(audioContext.currentTime);
                oscillator.stop(audioContext.currentTime + 0.4);
            }, 'playWrongSound');
        }

        function playVictorySound() {
            AppProtection.safeExecute(() => {
                if (!initAudio() || !audioContext) {
                    AppProtection.log('Audio not available, skipping sound', 'debug');
                    return;
                }

                const notes = [523.25, 659.25, 783.99, 1046.50]; // C-E-G-C
                notes.forEach((freq, index) => {
                    const oscillator = audioContext.createOscillator();
                    const gainNode = audioContext.createGain();
                    
                    oscillator.connect(gainNode);
                    gainNode.connect(audioContext.destination);
                    
                    oscillator.frequency.setValueAtTime(freq, audioContext.currentTime);
                    gainNode.gain.setValueAtTime(0.2, audioContext.currentTime + index * 0.2);
                    gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + index * 0.2 + 0.3);
                    
                    oscillator.start(audioContext.currentTime + index * 0.2);
                    oscillator.stop(audioContext.currentTime + index * 0.2 + 0.3);
                });
            }, 'playVictorySound');
        }

        // Generate evenly distributed positions for mascots
        function generateMascotPositions() {
            const positions = [];
            
            // Use fixed dimensions based on CSS - map is 200vw wide with 1:1 aspect ratio
            // On mobile it can be up to 300vw, so we'll use a safe area
            const mapWidth = Math.max(800, window.innerWidth * 2); // Minimum 800px or 200vw
            const mapHeight = mapWidth; // Square aspect ratio
            
            // Create a grid system for better distribution with smaller margins
            const gridSize = Math.ceil(Math.sqrt(gameState.totalMascots * 1.5)); // Slightly larger grid
            const edgeMargin = 20; // Much smaller margin to allow edge placement
            const cellWidth = (mapWidth - edgeMargin * 2) / gridSize; // Reduced margin from 160 to 40
            const cellHeight = (mapHeight - edgeMargin * 2) / gridSize;
            
            // Create all possible grid positions
            const gridPositions = [];
            for (let row = 0; row < gridSize; row++) {
                for (let col = 0; col < gridSize; col++) {
                    gridPositions.push({ row, col });
                }
            }
            
            // Shuffle the grid positions for random selection
            for (let i = gridPositions.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [gridPositions[i], gridPositions[j]] = [gridPositions[j], gridPositions[i]];
            }
            
            // Place mascots in selected grid cells with random offset within each cell
            for (let i = 0; i < gameState.totalMascots; i++) {
                const gridPos = gridPositions[i];
                
                // Calculate base position for this grid cell
                const baseX = edgeMargin + gridPos.col * cellWidth;
                const baseY = edgeMargin + gridPos.row * cellHeight;
                
                // Add random offset within the cell with very small margins to maximize spread
                const cellMargin = 5; // Very small margin within each cell
                const offsetX = Math.random() * (cellWidth - cellMargin * 2) + cellMargin;
                const offsetY = Math.random() * (cellHeight - cellMargin * 2) + cellMargin;
                
                const position = {
                    x: baseX + offsetX,
                    y: baseY + offsetY
                };
                
                // Ensure position is within map bounds with minimal edge distance
                const minEdgeDistance = 18; // Just enough space for the mascot (35px) to be fully visible and clickable
                position.x = Math.max(minEdgeDistance, Math.min(mapWidth - minEdgeDistance, position.x));
                position.y = Math.max(minEdgeDistance, Math.min(mapHeight - minEdgeDistance, position.y));
                
                positions.push(position);
            }
            
            return positions;
        }

        // Create mascots on the map
        function createMascots() {
            const mapElement = document.getElementById('game-map');
            const positions = generateMascotPositions();
            
            gameState.mascots = positions.map((pos, index) => {
                const mascot = document.createElement('img');
                mascot.src = images.mascotHidden;
                mascot.className = 'mascot';
                mascot.style.left = pos.x + 'px';
                mascot.style.top = pos.y + 'px';
                mascot.dataset.mascotId = index;
                
                mascot.addEventListener('click', () => handleMascotClick(mascot));
                
                mapElement.appendChild(mascot);
                
                return {
                    element: mascot,
                    found: false,
                    id: index
                };
            });
        }

        // Protected mascot click handler
        function handleMascotClick(mascotElement) {
            return AppProtection.safeExecute(() => {
                // Validate input and rate limiting
                if (!mascotElement || !AppProtection.isActionAllowed('mascot_click')) {
                    return;
                }

                // Validate game state
                if (!gameState.isGameActive && gameState.isTransitioning) {
                    AppProtection.log('Game not active, ignoring mascot click', 'debug');
                    return;
                }

                // Validate mascot data
                const mascotId = parseInt(mascotElement.dataset.mascotId);
                if (isNaN(mascotId) || mascotId < 0 || mascotId >= gameState.mascots.length) {
                    AppProtection.log(`Invalid mascot ID: ${mascotId}`, 'warn');
                    return;
                }

                const mascot = gameState.mascots[mascotId];
                if (!mascot || mascot.found) {
                    AppProtection.log('Mascot already found or invalid', 'debug');
                    return;
                }
                
                // Mark mascot as found
                mascot.found = true;
                mascotElement.src = images.mascotFound;
                mascotElement.classList.add('found-mascot');
                
                // Update game state safely
                gameState.foundCount++;
                AppProtection.validateGameState();
                
                // Update UI
                const foundCountElement = AppProtection.getElement('found-count');
                AppProtection.safeSetContent(foundCountElement, gameState.foundCount);
                
                // Play sound effect
                playBingoSound();
                
                AppProtection.log(`Mascot found! Total: ${gameState.foundCount}/${gameState.totalMascots}`, 'info');
                
                // Check for victory condition
                if (gameState.foundCount === gameState.totalMascots) {
                    gameState.isGameActive = false;
                    AppProtection.setTimeout(() => showVictoryModal(), 200);
                }
            }, 'handleMascotClick');
        }

        // Protected wrong click handler
        function handleWrongClick(event) {
            return AppProtection.safeExecute(() => {
                // Validate input and rate limiting
                if (!event || !AppProtection.isActionAllowed('wrong_click')) {
                    return;
                }

                // Validate game state
                if (!gameState.isGameActive || gameState.isTransitioning) {
                    AppProtection.log('Game not active, ignoring wrong click', 'debug');
                    return;
                }

                // Check if clicked on a mascot - don't penalize
                if (event.target && event.target.classList.contains('mascot')) {
                    AppProtection.log('Clicked on mascot, ignoring wrong click', 'debug');
                    return;
                }
                
                // Validate event and elements
                const mapElement = event.currentTarget;
                if (!mapElement) {
                    AppProtection.log('Invalid map element in wrong click', 'warn');
                    return;
                }

                // Safe position calculation with fallbacks
                const rect = mapElement.getBoundingClientRect();
                if (!rect.width || !rect.height) {
                    AppProtection.log('Invalid map dimensions in wrong click', 'warn');
                    return;
                }

                const x = Math.max(0, (event.clientX - rect.left) / Math.max(gameState.zoomLevel, 0.1));
                const y = Math.max(0, (event.clientY - rect.top) / Math.max(gameState.zoomLevel, 0.1));
                
                // Create wrong click indicator with safe positioning
                const wrongIndicator = document.createElement('div');
                wrongIndicator.className = 'wrong-click';
                wrongIndicator.textContent = '❌';
                
                // Ensure indicator stays within map bounds
                const mapWidth = mapElement.offsetWidth;
                const mapHeight = mapElement.offsetHeight;
                const safeX = Math.max(15, Math.min(mapWidth - 15, x - 15));
                const safeY = Math.max(15, Math.min(mapHeight - 15, y - 15));
                
                wrongIndicator.style.left = safeX + 'px';
                wrongIndicator.style.top = safeY + 'px';
                
                mapElement.appendChild(wrongIndicator);
                
                // Safe cleanup with tracking
                AppProtection.setTimeout(() => {
                    if (wrongIndicator.parentNode) {
                        wrongIndicator.parentNode.removeChild(wrongIndicator);
                    }
                }, 2000);
                
                // Deduct life with validation
                gameState.lives = Math.max(0, gameState.lives - 1);
                AppProtection.validateGameState();
                
                updateLives();
                playWrongSound();
                
                AppProtection.log(`Wrong click! Lives remaining: ${gameState.lives}`, 'info');
                
                // Check for game over
                if (gameState.lives <= 0) {
                    gameState.isGameActive = false;
                    AppProtection.setTimeout(() => showGameOverModal(), 500);
                }
            }, 'handleWrongClick');
        }

        // Update lives display
        function updateLives() {
            const hearts = document.querySelectorAll('.heart');
            hearts.forEach((heart, index) => {
                if (index >= gameState.lives) {
                    heart.classList.add('lost');
                } else {
                    heart.classList.remove('lost');
                }
            });
        }

        // Create confetti animation for map 9
        function createConfetti() {
            // Create confetti container
            const confettiContainer = document.createElement('div');
            confettiContainer.id = 'confetti-container';
            confettiContainer.style.position = 'fixed';
            confettiContainer.style.top = '0';
            confettiContainer.style.left = '0';
            confettiContainer.style.width = '100%';
            confettiContainer.style.height = '100%';
            confettiContainer.style.pointerEvents = 'none';
            confettiContainer.style.zIndex = '100';
            confettiContainer.style.overflow = 'hidden';
            
            // Create individual confetti pieces
            const colors = ['#ff6b6b', '#4ecdc4', '#45b7d1', '#96ceb4', '#feca57', '#ff9ff3', '#54a0ff', '#5f27cd', '#00d2d3', '#ff6348', '#1dd1a1'];
            
            for (let i = 0; i < 50; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti';
                confetti.style.left = Math.random() * 100 + '%';
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.animationDelay = Math.random() * 3 + 's';
                confetti.style.animationDuration = (2 + Math.random() * 3) + 's';
                
                // Random size between 8px and 15px
                const size = 8 + Math.random() * 7;
                confetti.style.width = size + 'px';
                confetti.style.height = size + 'px';
                
                // Random shapes
                if (Math.random() > 0.5) {
                    confetti.style.borderRadius = '50%'; // Circle
                } else {
                    confetti.style.borderRadius = '2px'; // Square
                }
                
                confettiContainer.appendChild(confetti);
            }
            
            document.body.appendChild(confettiContainer);
            
            // Remove confetti after animation completes
            setTimeout(() => {
                if (confettiContainer.parentNode) {
                    confettiContainer.remove();
                }
            }, 5000);
        }

        // Create mascot explosion animation for map 9 completion on homepage
        function createMascotExplosion() {
            // Only show on homepage
            const homepage = document.getElementById('homepage');
            if (homepage.classList.contains('hidden')) {
                return;
            }

            // Create explosion container
            const explosionContainer = document.createElement('div');
            explosionContainer.id = 'mascot-explosion-container';
            explosionContainer.style.position = 'fixed';
            explosionContainer.style.top = '0';
            explosionContainer.style.left = '0';
            explosionContainer.style.width = '100%';
            explosionContainer.style.height = '100%';
            explosionContainer.style.pointerEvents = 'none';
            explosionContainer.style.zIndex = '200';
            explosionContainer.style.overflow = 'hidden';
            
            // Get viewport dimensions
            const viewportWidth = window.innerWidth;
            const viewportHeight = window.innerHeight;
            const centerX = viewportWidth / 2;
            const centerY = viewportHeight / 2;
            
            // Create the central big mascot first
            const centralMascot = document.createElement('img');
            centralMascot.src = images.mascotFound;
            centralMascot.style.position = 'absolute';
            centralMascot.style.pointerEvents = 'none';
            
            // Big size for central mascot
            const centralSize = 120;
            centralMascot.style.width = centralSize + 'px';
            centralMascot.style.height = centralSize + 'px';
            
            // Position at center
            centralMascot.style.left = (centerX - centralSize/2) + 'px';
            centralMascot.style.top = (centerY - centralSize/2) + 'px';
            centralMascot.style.opacity = '1';
            centralMascot.style.transform = 'scale(1)';
            centralMascot.style.transition = 'all 1.5s cubic-bezier(0.25, 0.46, 0.45, 0.94)';
            
            explosionContainer.appendChild(centralMascot);
            
            // Create 25 surrounding mascots for the initial explosion
            for (let i = 0; i < 25; i++) {
                const mascot = document.createElement('img');
                mascot.src = images.mascotFound; // Use colorful mascot
                mascot.style.position = 'absolute';
                mascot.style.pointerEvents = 'none';
                
                // Random size between 30px and 70px
                const size = 30 + Math.random() * 40;
                mascot.style.width = size + 'px';
                mascot.style.height = size + 'px';
                
                // Start at center
                mascot.style.left = (centerX - size/2) + 'px';
                mascot.style.top = (centerY - size/2) + 'px';
                
                // Random explosion direction (angle)
                const angle = (Math.random() * 2 * Math.PI);
                const distance = 250 + Math.random() * 450; // Distance to travel
                
                // Calculate end position
                const endX = centerX + Math.cos(angle) * distance - size/2;
                const endY = centerY + Math.sin(angle) * distance - size/2;
                
                // Random rotation during animation
                const rotation = Math.random() * 720 - 360; // -360 to +360 degrees
                
                // Animation duration between 2 and 3.5 seconds
                const duration = 2 + Math.random() * 1.5;
                
                // Create the explosion animation
                mascot.style.transition = `all ${duration}s cubic-bezier(0.25, 0.46, 0.45, 0.94)`;
                mascot.style.opacity = '1';
                
                explosionContainer.appendChild(mascot);
                
                // Trigger animation after a short delay
                setTimeout(() => {
                    mascot.style.left = endX + 'px';
                    mascot.style.top = endY + 'px';
                    mascot.style.transform = `rotate(${rotation}deg) scale(0.3)`;
                    mascot.style.opacity = '0';
                }, 100 + i * 30); // Stagger the start times slightly
            }
            
            // Animate the central mascot last (after 3.5 seconds)
            setTimeout(() => {
                // Central mascot explosion - multiple directions
                const centralRotation = Math.random() * 360;
                centralMascot.style.transform = `rotate(${centralRotation}deg) scale(3)`;
                centralMascot.style.opacity = '0';
            }, 3500);
            
            document.body.appendChild(explosionContainer);
            
            // Remove explosion container after 5 seconds
            setTimeout(() => {
                if (explosionContainer.parentNode) {
                    explosionContainer.remove();
                }
            }, 5000);
            
            // Play cartoon-style explosion sound effect
            initAudio();
            
            // Create cartoon "POP" sound for initial explosion
            const popOscillator1 = audioContext.createOscillator();
            const popOscillator2 = audioContext.createOscillator();
            const popGain = audioContext.createGain();
            
            popOscillator1.connect(popGain);
            popOscillator2.connect(popGain);
            popGain.connect(audioContext.destination);
            
            // Cartoon pop frequencies - higher pitched and bouncy
            popOscillator1.frequency.setValueAtTime(800, audioContext.currentTime);
            popOscillator1.frequency.exponentialRampToValueAtTime(200, audioContext.currentTime + 0.2);
            popOscillator1.frequency.setValueAtTime(600, audioContext.currentTime + 0.25);
            popOscillator1.frequency.exponentialRampToValueAtTime(100, audioContext.currentTime + 0.4);
            
            popOscillator2.frequency.setValueAtTime(1200, audioContext.currentTime);
            popOscillator2.frequency.exponentialRampToValueAtTime(400, audioContext.currentTime + 0.15);
            popOscillator2.frequency.setValueAtTime(800, audioContext.currentTime + 0.2);
            popOscillator2.frequency.exponentialRampToValueAtTime(150, audioContext.currentTime + 0.35);
            
            // Cartoon bounce envelope
            popGain.gain.setValueAtTime(0.4, audioContext.currentTime);
            popGain.gain.exponentialRampToValueAtTime(0.2, audioContext.currentTime + 0.1);
            popGain.gain.setValueAtTime(0.3, audioContext.currentTime + 0.15);
            popGain.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.4);
            
            popOscillator1.start(audioContext.currentTime);
            popOscillator1.stop(audioContext.currentTime + 0.4);
            popOscillator2.start(audioContext.currentTime);
            popOscillator2.stop(audioContext.currentTime + 0.4);
            
            // Play bigger cartoon explosion for central mascot
            setTimeout(() => {
                const bigPopOsc1 = audioContext.createOscillator();
                const bigPopOsc2 = audioContext.createOscillator();
                const bigPopOsc3 = audioContext.createOscillator();
                const bigPopGain = audioContext.createGain();
                
                bigPopOsc1.connect(bigPopGain);
                bigPopOsc2.connect(bigPopGain);
                bigPopOsc3.connect(bigPopGain);
                bigPopGain.connect(audioContext.destination);
                
                // Triple cartoon explosion - more dramatic but still cartoony
                bigPopOsc1.frequency.setValueAtTime(600, audioContext.currentTime);
                bigPopOsc1.frequency.setValueAtTime(1000, audioContext.currentTime + 0.1);
                bigPopOsc1.frequency.exponentialRampToValueAtTime(80, audioContext.currentTime + 0.6);
                
                bigPopOsc2.frequency.setValueAtTime(900, audioContext.currentTime);
                bigPopOsc2.frequency.setValueAtTime(1400, audioContext.currentTime + 0.1);
                bigPopOsc2.frequency.exponentialRampToValueAtTime(120, audioContext.currentTime + 0.6);
                
                bigPopOsc3.frequency.setValueAtTime(1200, audioContext.currentTime);
                bigPopOsc3.frequency.setValueAtTime(1800, audioContext.currentTime + 0.1);
                bigPopOsc3.frequency.exponentialRampToValueAtTime(200, audioContext.currentTime + 0.5);
                
                // Big cartoon bounce envelope
                bigPopGain.gain.setValueAtTime(0.5, audioContext.currentTime);
                bigPopGain.gain.setValueAtTime(0.3, audioContext.currentTime + 0.05);
                bigPopGain.gain.setValueAtTime(0.6, audioContext.currentTime + 0.1);
                bigPopGain.gain.setValueAtTime(0.4, audioContext.currentTime + 0.2);
                bigPopGain.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.7);
                
                bigPopOsc1.start(audioContext.currentTime);
                bigPopOsc1.stop(audioContext.currentTime + 0.7);
                bigPopOsc2.start(audioContext.currentTime);
                bigPopOsc2.stop(audioContext.currentTime + 0.7);
                bigPopOsc3.start(audioContext.currentTime);
                bigPopOsc3.stop(audioContext.currentTime + 0.5);
            }, 3500);
        }

        // Show victory modal
        function showVictoryModal() {
            playVictorySound();
            
            const victoryModal = document.getElementById('victory-modal');
            const modalContent = victoryModal.querySelector('.bg-white');
            
            // Remove any existing animation classes
            modalContent.classList.remove('victory-glow', 'victory-glow-yellow', 'rainbow-glow', 'celebration-pulse');
            
            // Mark current map as completed and update its appearance
            markMapAsCompleted(gameState.currentMap);
            
            // Check if this unlocks the next map or if it's the final map
            const nextMap = gameState.currentMap + 1;
            const t = translations[currentLanguage];
            
            if (gameState.currentMap === 9) {
                // Final map completed - show celebration message with rainbow animation
                document.getElementById('unlock-message').innerHTML = `
                    <p class="text-sm md:text-base text-green-800 dark:text-green-200 font-medium">
                        ${t.allMapsCompleted}
                    </p>
                `;
                document.getElementById('unlock-message').classList.remove('hidden');
                
                // Apply only rainbow glow for final map (remove celebration-pulse to avoid animation conflict)
                modalContent.classList.add('rainbow-glow');
                
                // Create confetti effect for final map completion immediately
                createConfetti();
            } else {
                // Determine glow color based on map number (excluding map 9)
                // Odd maps (1,3,5,7): Green glow
                // Even maps (2,4,6,8): Yellow glow
                const isEvenMap = gameState.currentMap % 2 === 0;
                const glowClass = isEvenMap ? 'victory-glow-yellow' : 'victory-glow';
                
                if (nextMap <= 9 && !gameState.unlockedMaps[nextMap]) {
                    // Regular map unlock with appropriate glow color
                    gameState.unlockedMaps[nextMap] = true;
                    document.getElementById('unlock-message').innerHTML = `
                        <p class="text-sm md:text-base text-yellow-800 dark:text-yellow-200 font-medium">
                            ${t.newMapUnlocked}
                        </p>
                    `;
                    document.getElementById('unlock-message').classList.remove('hidden');
                    unlockMapButton(nextMap);
                    
                    // Apply appropriate glow based on map number
                    modalContent.classList.add(glowClass);
                } else {
                    // Map already completed, show appropriate glow
                    modalContent.classList.add(glowClass);
                }
            }
            
            victoryModal.classList.remove('hidden');
        }

        // Function to unlock a map button
        function unlockMapButton(mapNumber) {
            const mapBtn = document.getElementById(`map${mapNumber}-btn`);
            
            // Remove locked class
            mapBtn.classList.remove('locked');
            
            // Remove the dark overlay and lock icon
            const overlay = mapBtn.querySelector('.absolute.inset-0.bg-black');
            if (overlay) {
                overlay.remove();
            }
            
            // Update description text based on map
            const descriptions = {
                2: 'Stage performance',
                3: 'More fun awaits',
                4: 'Panel adventures',
                5: 'Live performance',
                6: 'Amusement park',
                7: 'Busy marketplace',
                8: 'Dining experience',
                9: 'Final challenge'
            };
            
            const descriptionElement = mapBtn.querySelector('p');
            if (descriptionElement && descriptions[mapNumber]) {
                descriptionElement.textContent = descriptions[mapNumber];
            }
        }

        // Function to mark a map as completed
        function markMapAsCompleted(mapNumber) {
            const mapBtn = document.getElementById(`map${mapNumber}-btn`);
            if (!mapBtn) return;
            
            // Check if already has a completion overlay
            const existingOverlay = mapBtn.querySelector('.completion-overlay');
            if (existingOverlay) return; // Already marked as completed
            
            // Remove any existing overlay (like the landscape emoji for map 1 or lock icons for other maps)
            const existingOverlayToRemove = mapBtn.querySelector('.absolute.inset-0.bg-black');
            if (existingOverlayToRemove) {
                existingOverlayToRemove.remove();
            }
            
            // Create grey completion overlay for all maps
            const completionOverlay = document.createElement('div');
            completionOverlay.className = 'completion-overlay absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center';
            completionOverlay.innerHTML = '<span class="text-white text-xl">✅</span>';
            
            // Add to the image container
            const imageContainer = mapBtn.querySelector('.aspect-square');
            if (imageContainer) {
                imageContainer.appendChild(completionOverlay);
            }
            
            // Update description to show completed status
            const descriptionElement = mapBtn.querySelector('p');
            if (descriptionElement) {
                descriptionElement.textContent = 'Completed';
                descriptionElement.classList.add('text-green-600', 'font-medium');
            }
        }

        // Show game over modal
        function showGameOverModal() {
            document.getElementById('final-count').textContent = gameState.foundCount;
            document.getElementById('gameover-modal').classList.remove('hidden');
        }

        // Zoom functionality
        function updateZoom() {
            const mapElement = document.getElementById('game-map');
            const container = mapElement.parentElement;
            
            // Apply zoom transform
            mapElement.style.transform = `scale(${gameState.zoomLevel})`;
            mapElement.style.transformOrigin = '0 0';
            
            // Update zoom level display - show relative to the new base (0.5 = 100%)
            const displayPercentage = Math.round((gameState.zoomLevel / gameState.baseZoom) * 100);
            document.getElementById('zoom-level').textContent = displayPercentage + '%';
            
            // Enable/disable zoom buttons
            document.getElementById('zoom-out').disabled = gameState.zoomLevel <= gameState.minZoom;
            document.getElementById('zoom-in').disabled = gameState.zoomLevel >= gameState.maxZoom;
            
            // Update button styles based on state
            const zoomOutBtn = document.getElementById('zoom-out');
            const zoomInBtn = document.getElementById('zoom-in');
            
            if (zoomOutBtn.disabled) {
                zoomOutBtn.classList.add('opacity-50', 'cursor-not-allowed');
            } else {
                zoomOutBtn.classList.remove('opacity-50', 'cursor-not-allowed');
            }
            
            if (zoomInBtn.disabled) {
                zoomInBtn.classList.add('opacity-50', 'cursor-not-allowed');
            } else {
                zoomInBtn.classList.remove('opacity-50', 'cursor-not-allowed');
            }
        }

        function zoomIn() {
            if (gameState.zoomLevel < gameState.maxZoom) {
                gameState.zoomLevel = Math.min(gameState.maxZoom, gameState.zoomLevel + 0.125);
                updateZoom();
            }
        }

        function zoomOut() {
            if (gameState.zoomLevel > gameState.minZoom) {
                gameState.zoomLevel = Math.max(gameState.minZoom, gameState.zoomLevel - 0.125);
                updateZoom();
            }
        }

        function resetZoom() {
            gameState.zoomLevel = gameState.baseZoom; // Reset to the new default (0.5)
            updateZoom();
            
            // Reset scroll position
            const container = document.querySelector('.game-map-container');
            container.scrollLeft = 0;
        }

        // Loading system
        function updateLoadingProgress(percentage, text) {
            document.getElementById('loading-progress').style.width = percentage + '%';
            document.getElementById('loading-percentage').textContent = percentage + '%';
            document.getElementById('loading-text').textContent = text;
        }

        function preloadAssets(mapNumber) {
            return new Promise((resolve) => {
                // Only preload essential images for current game session
                const essentialImages = [
                    images[`map${mapNumber}`],
                    images.mascotHidden,
                    images.mascotFound
                ];
                
                let loadedCount = 0;
                const totalImages = essentialImages.length;
                let resolved = false;
                
                // Overall timeout - resolve after 1.5 seconds regardless of loading status
                const overallTimeout = setTimeout(() => {
                    if (!resolved) {
                        resolved = true;
                        resolve();
                    }
                }, 1500);
                
                const checkComplete = () => {
                    if (!resolved && loadedCount >= totalImages) {
                        resolved = true;
                        clearTimeout(overallTimeout);
                        resolve();
                    }
                };
                
                // Load essential images with simplified logic
                essentialImages.forEach((src, index) => {
                    const img = new Image();
                    
                    img.onload = () => {
                        loadedCount++;
                        const progress = Math.floor((loadedCount / totalImages) * 60); // Up to 60% for image loading
                        updateLoadingProgress(progress, `Loading assets...`);
                        checkComplete();
                    };
                    
                    img.onerror = () => {
                        loadedCount++;
                        const progress = Math.floor((loadedCount / totalImages) * 60);
                        updateLoadingProgress(progress, `Loading assets...`);
                        checkComplete();
                    };
                    
                    img.src = src;
                });
                
                // Start loading other maps in background (non-blocking)
                setTimeout(() => {
                    preloadBackgroundAssets();
                }, 50);
            });
        }

        function preloadBackgroundAssets() {
            // Load other map images in background after game starts
            const otherImages = Object.keys(images)
                .filter(key => key.startsWith('map') && key !== `map${gameState.currentMap}`)
                .map(key => images[key]);
            
            otherImages.forEach(src => {
                const img = new Image();
                img.src = src;
                // No need to wait for these or show progress
            });
        }

        // Add loading state management with protection
        let isLoading = false;
        let currentLoadingTimeout = null;

        // Protected game initialization
        async function initGame(mapNumber) {
            return AppProtection.safeExecute(async () => {
                // Input validation
                if (!mapNumber || mapNumber < 1 || mapNumber > 9) {
                    AppProtection.log(`Invalid map number: ${mapNumber}`, 'error');
                    return false;
                }

                // Prevent multiple simultaneous loading
                if (isLoading) {
                    AppProtection.log('Already loading, cancelling previous load...', 'warn');
                    if (currentLoadingTimeout) {
                        clearTimeout(currentLoadingTimeout);
                        currentLoadingTimeout = null;
                    }
                    AppProtection.cleanup(); // Clean up any pending operations
                }
                
                isLoading = true;
                gameState.isTransitioning = true;
                gameState.isGameActive = false;
                gameState.gameStartTime = Date.now();
                
                AppProtection.log(`Initializing game for map ${mapNumber}`, 'info');
                
                // Stop floating mascot animation safely
                stopFloatingMascotAnimation();
                
                // Show loading screen and reset progress
                const homepage = AppProtection.getElement('homepage');
                const gamescreen = AppProtection.getElement('gamescreen');
                const loadingScreen = AppProtection.getElement('loading-screen');
                
                if (homepage) homepage.classList.add('hidden');
                if (gamescreen) gamescreen.classList.add('hidden');
                if (loadingScreen) loadingScreen.classList.remove('hidden');
                
                // Reset loading progress safely
                updateLoadingProgress(0, 'Starting...');
                
                try {
                    // Initialize game state with validation
                    gameState.currentMap = mapNumber;
                    gameState.lives = 3;
                    gameState.foundCount = 0;
                    gameState.mascots = [];
                    gameState.zoomLevel = gameState.baseZoom;
                    gameState.hintsUsed = 0;
                    
                    // Validate initial state
                    AppProtection.validateGameState();
                    
                    // Update UI elements safely
                    const currentMapElement = AppProtection.getElement('current-map');
                    AppProtection.safeSetContent(currentMapElement, mapNumber);
                    
                    updateLoadingProgress(10, 'Initializing game...');
                    
                    // Preload essential assets for current map
                    await preloadAssets(mapNumber);
                    
                    // Check if loading was cancelled
                    if (!isLoading) {
                        AppProtection.log('Loading was cancelled during asset loading', 'info');
                        return false;
                    }
                    
                    updateLoadingProgress(70, 'Setting up map...');
                    
                    // Clear previous game state safely
                    const mapElement = AppProtection.getElement('game-map');
                    if (mapElement) {
                        const existingMascots = mapElement.querySelectorAll('.mascot');
                        existingMascots.forEach(mascot => {
                            try {
                                mascot.remove();
                            } catch (e) {
                                AppProtection.log(`Error removing mascot: ${e.message}`, 'warn');
                            }
                        });
                        
                        const wrongIndicators = mapElement.querySelectorAll('.wrong-click');
                        wrongIndicators.forEach(indicator => {
                            try {
                                indicator.remove();
                            } catch (e) {
                                AppProtection.log(`Error removing indicator: ${e.message}`, 'warn');
                            }
                        });
                        
                        // Set map background safely
                        const mapImage = images[`map${mapNumber}`];
                        if (mapImage) {
                            mapElement.style.backgroundImage = `url(${mapImage})`;
                        }
                    }
                    
                    updateLoadingProgress(80, 'Positioning mascots...');
                    
                    // Generate positions and create mascots safely
                    const positions = generateMascotPositions();
                    
                    // Create mascots with error handling
                    gameState.mascots = positions.map((pos, index) => {
                        try {
                            const mascot = document.createElement('img');
                            mascot.src = images.mascotHidden;
                            mascot.className = 'mascot';
                            mascot.style.left = pos.x + 'px';
                            mascot.style.top = pos.y + 'px';
                            mascot.dataset.mascotId = index;
                            
                            // Protected event listener
                            mascot.addEventListener('click', (e) => {
                                e.preventDefault();
                                e.stopPropagation();
                                handleMascotClick(mascot);
                            });
                            
                            if (mapElement) {
                                mapElement.appendChild(mascot);
                            }
                            
                            return {
                                element: mascot,
                                found: false,
                                id: index
                            };
                        } catch (error) {
                            AppProtection.log(`Error creating mascot ${index}: ${error.message}`, 'error');
                            return null;
                        }
                    }).filter(mascot => mascot !== null); // Remove failed mascot creations
                    
                    updateLoadingProgress(90, 'Finalizing...');
                    
                    // Setup game elements safely
                    updateZoom();
                    
                    const foundCountElement = AppProtection.getElement('found-count');
                    AppProtection.safeSetContent(foundCountElement, '0');
                    
                    updateLives();
                    updateHintButton();
                    
                    // Attach click handler with protection
                    if (mapElement) {
                        mapElement.onclick = (e) => {
                            if (gameState.isGameActive) {
                                handleWrongClick(e);
                            }
                        };
                    }
                    
                    updateLoadingProgress(100, 'Game ready!');
                    
                    // Activate game state
                    gameState.isGameActive = true;
                    gameState.isTransitioning = false;
                    
                    AppProtection.log(`Game initialized successfully for map ${mapNumber}`, 'info');
                    
                    // Hide loading screen and show game with protection
                    currentLoadingTimeout = AppProtection.setTimeout(() => {
                        if (isLoading) {
                            const loadingScreen = AppProtection.getElement('loading-screen');
                            const gamescreen = AppProtection.getElement('gamescreen');
                            
                            if (loadingScreen) loadingScreen.classList.add('hidden');
                            if (gamescreen) gamescreen.classList.remove('hidden');
                            
                            // Final hint button update now that game screen is visible
                            updateHintButton();
                            
                            isLoading = false;
                            currentLoadingTimeout = null;
                            
                            AppProtection.log('Game loading completed successfully', 'info');
                        }
                    }, 200);
                    
                    return true;
                    
                } catch (error) {
                    AppProtection.log(`Error during game initialization: ${error.message}`, 'error');
                    
                    // Reset state on error
                    isLoading = false;
                    gameState.isGameActive = false;
                    gameState.isTransitioning = false;
                    
                    // Show error recovery
                    const loadingScreen = AppProtection.getElement('loading-screen');
                    const homepage = AppProtection.getElement('homepage');
                    
                    if (loadingScreen) loadingScreen.classList.add('hidden');
                    if (homepage) homepage.classList.remove('hidden');
                    
                    startFloatingMascotAnimation();
                    
                    return false;
                }
            }, 'initGame');
        }

        // Protected cleanup and error recovery
        function handleAppError(error, context = 'unknown') {
            AppProtection.log(`App error in ${context}: ${error.message}`, 'error');
            
            // Reset to safe state
            gameState.isGameActive = false;
            gameState.isTransitioning = false;
            isLoading = false;
            
            // Clean up resources
            AppProtection.cleanup();
            
            // Return to homepage safely
            try {
                const screens = ['loading-screen', 'gamescreen', 'victory-modal', 'gameover-modal'];
                screens.forEach(screenId => {
                    const screen = AppProtection.getElement(screenId, false);
                    if (screen) screen.classList.add('hidden');
                });
                
                const homepage = AppProtection.getElement('homepage');
                if (homepage) homepage.classList.remove('hidden');
                
                startFloatingMascotAnimation();
            } catch (recoveryError) {
                AppProtection.log(`Error during recovery: ${recoveryError.message}`, 'error');
                // Last resort: reload page
                window.location.reload();
            }
        }

        // Global error handler
        window.addEventListener('error', (event) => {
            handleAppError(event.error, 'global');
        });

        window.addEventListener('unhandledrejection', (event) => {
            handleAppError(new Error(event.reason), 'promise');
        });

        // Event listeners for all map buttons
        for (let i = 1; i <= 9; i++) {
            document.getElementById(`map${i}-btn`).addEventListener('click', () => {
                if (!gameState.unlockedMaps[i]) return;
                initGame(i);
            });
        }

        // Sudoku button event listener
        document.getElementById('sudoku-btn').addEventListener('click', () => {
            window.open('https://poe.com/MascotSudokuGMMUnoff', '_blank');
        });

        document.getElementById('back-btn').addEventListener('click', () => {
            document.getElementById('gamescreen').classList.add('hidden');
            document.getElementById('homepage').classList.remove('hidden');
            startFloatingMascotAnimation(); // Restart animation when returning to homepage
        });

        // Loading screen back button
        document.getElementById('loading-back-btn').addEventListener('click', () => {
            // Cancel current loading
            isLoading = false;
            if (currentLoadingTimeout) {
                clearTimeout(currentLoadingTimeout);
                currentLoadingTimeout = null;
            }
            
            // Hide loading screen and go back to homepage
            document.getElementById('loading-screen').classList.add('hidden');
            document.getElementById('homepage').classList.remove('hidden');
            startFloatingMascotAnimation(); // Restart animation when returning to homepage
        });

        // Loading screen reload button
        document.getElementById('loading-reload-btn').addEventListener('click', () => {
            // Force restart the current game initialization
            isLoading = false; // Reset loading state first
            if (currentLoadingTimeout) {
                clearTimeout(currentLoadingTimeout);
                currentLoadingTimeout = null;
            }
            initGame(gameState.currentMap);
        });

        document.getElementById('victory-continue').addEventListener('click', () => {
            const wasMap9 = gameState.currentMap === 9;
            document.getElementById('victory-modal').classList.add('hidden');
            document.getElementById('gamescreen').classList.add('hidden');
            document.getElementById('homepage').classList.remove('hidden');
            
            // Special mascot explosion for map 9 completion
            if (wasMap9) {
                createMascotExplosion();
            }
            
            startFloatingMascotAnimation(); // Restart animation when returning to homepage
        });

        document.getElementById('gameover-retry').addEventListener('click', () => {
            document.getElementById('gameover-modal').classList.add('hidden');
            initGame(gameState.currentMap);
        });

        document.getElementById('gameover-menu').addEventListener('click', () => {
            document.getElementById('gameover-modal').classList.add('hidden');
            document.getElementById('gamescreen').classList.add('hidden');
            document.getElementById('homepage').classList.remove('hidden');
            startFloatingMascotAnimation(); // Restart animation when returning to homepage
        });

        // Touch gesture support for zoom
        let touches = {};
        let initialDistance = 0;
        let initialZoom = gameState.zoomLevel;

        function getDistance(touch1, touch2) {
            return Math.sqrt(
                Math.pow(touch2.clientX - touch1.clientX, 2) + 
                Math.pow(touch2.clientY - touch1.clientY, 2)
            );
        }

        function handleTouchStart(event) {
            if (event.touches.length === 2) {
                // Prevent default zooming behavior
                event.preventDefault();
                
                const touch1 = event.touches[0];
                const touch2 = event.touches[1];
                
                initialDistance = getDistance(touch1, touch2);
                initialZoom = gameState.zoomLevel;
                
                touches = {
                    touch1: { x: touch1.clientX, y: touch1.clientY },
                    touch2: { x: touch2.clientX, y: touch2.clientY }
                };
            }
        }

        function handleTouchMove(event) {
            if (event.touches.length === 2) {
                event.preventDefault();
                
                const touch1 = event.touches[0];
                const touch2 = event.touches[1];
                
                const currentDistance = getDistance(touch1, touch2);
                const zoomRatio = currentDistance / initialDistance;
                
                // Calculate new zoom level
                let newZoomLevel = initialZoom * zoomRatio;
                newZoomLevel = Math.max(gameState.minZoom, Math.min(gameState.maxZoom, newZoomLevel));
                
                gameState.zoomLevel = newZoomLevel;
                updateZoom();
            }
        }

        function handleTouchEnd(event) {
            if (event.touches.length < 2) {
                touches = {};
                initialDistance = 0;
            }
        }

        // Hint system
        function updateHintButton() {
            const hintBtn = document.getElementById('hint-btn');
            const hintsRemainingElement = document.getElementById('hints-remaining');
            const hintsRemaining = gameState.maxHints - gameState.hintsUsed;
            
            // Safety check - only update if elements exist (game screen is visible)
            if (!hintBtn) return;
            
            // Update existing hints remaining element if it exists
            if (hintsRemainingElement) {
                hintsRemainingElement.textContent = hintsRemaining;
            }
            
            if (hintsRemaining <= 0) {
                hintBtn.disabled = true;
                // Reset button text to show proper structure when disabled
                hintBtn.innerHTML = `
                    <span class="text-lg">💡</span>
                    <span class="hidden sm:inline">No hints left</span>
                    <span class="bg-white bg-opacity-20 text-xs px-2 py-0.5 rounded-full">
                        <span>0</span>
                    </span>
                `;
            } else {
                hintBtn.disabled = false;
                // Reset button text to show proper structure when enabled
                hintBtn.innerHTML = `
                    <span class="text-lg">💡</span>
                    <span class="hidden sm:inline">Hint</span>
                    <span class="bg-white bg-opacity-20 text-xs px-2 py-0.5 rounded-full">
                        <span id="hints-remaining">${hintsRemaining}</span>
                    </span>
                `;
            }
        }

        function useHint() {
            if (gameState.hintsUsed >= gameState.maxHints) return;
            
            // Find the first unfound mascot
            const unfoundMascots = gameState.mascots.filter(mascot => !mascot.found);
            if (unfoundMascots.length === 0) return;
            
            // Select a random unfound mascot
            const randomMascot = unfoundMascots[Math.floor(Math.random() * unfoundMascots.length)];
            const mascotElement = randomMascot.element;
            
            // Add glowing effect to the mascot
            mascotElement.classList.add('hint-glow');
            
            // Remove glow effect after 4 seconds
            setTimeout(() => {
                mascotElement.classList.remove('hint-glow');
            }, 4000);
            
            // Create a hint indicator that points to the mascot
            const hintIndicator = document.createElement('div');
            hintIndicator.className = 'absolute pointer-events-none z-30';
            hintIndicator.style.left = (parseInt(mascotElement.style.left) - 10) + 'px';
            hintIndicator.style.top = (parseInt(mascotElement.style.top) - 40) + 'px';
            hintIndicator.innerHTML = '👇';
            hintIndicator.style.fontSize = '30px';
            hintIndicator.style.animation = 'bounce 2s infinite';
            hintIndicator.style.textShadow = '2px 2px 4px rgba(0,0,0,0.5)';
            
            // Add hint indicator to the map
            document.getElementById('game-map').appendChild(hintIndicator);
            
            // Remove hint indicator after 3 seconds
            setTimeout(() => {
                if (hintIndicator.parentNode) {
                    hintIndicator.parentNode.removeChild(hintIndicator);
                }
            }, 3000);
            
            // Scroll the map to show the hinted mascot
            const container = document.querySelector('.game-map-container');
            const mascotRect = mascotElement.getBoundingClientRect();
            const containerRect = container.getBoundingClientRect();
            
            // Calculate scroll position to center the mascot
            const mascotX = parseInt(mascotElement.style.left) * gameState.zoomLevel;
            const mascotY = parseInt(mascotElement.style.top) * gameState.zoomLevel;
            
            container.scrollLeft = Math.max(0, mascotX - container.clientWidth / 2);
            container.scrollTop = Math.max(0, mascotY - container.clientHeight / 2);
            
            // Update hint counter
            gameState.hintsUsed++;
            updateHintButton();
            
            // Play a soft hint sound
            initAudio();
            const oscillator = audioContext.createOscillator();
            const gainNode = audioContext.createGain();
            
            oscillator.connect(gainNode);
            gainNode.connect(audioContext.destination);
            
            oscillator.frequency.setValueAtTime(800, audioContext.currentTime);
            oscillator.frequency.setValueAtTime(600, audioContext.currentTime + 0.2);
            
            gainNode.gain.setValueAtTime(0.2, audioContext.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.4);
            
            oscillator.start(audioContext.currentTime);
            oscillator.stop(audioContext.currentTime + 0.4);
        }

        // Zoom button event listeners
        document.getElementById('zoom-in').addEventListener('click', zoomIn);
        document.getElementById('zoom-out').addEventListener('click', zoomOut);
        document.getElementById('zoom-reset').addEventListener('click', resetZoom);
        
        // Hint button event listener
        document.getElementById('hint-btn').addEventListener('click', useHint);

        // Add touch gesture listeners to the game map container
        document.addEventListener('DOMContentLoaded', () => {
            const gameMapContainer = document.querySelector('.game-map-container');
            if (gameMapContainer) {
                gameMapContainer.addEventListener('touchstart', handleTouchStart, { passive: false });
                gameMapContainer.addEventListener('touchmove', handleTouchMove, { passive: false });
                gameMapContainer.addEventListener('touchend', handleTouchEnd, { passive: false });
            }
        });

        // Floating mascot animation for homepage
        let floatingMascotTimeout;
        let currentFloatingMascot = null;
        let mascotImageLoaded = false;

        function preloadMascotImage() {
            return new Promise((resolve) => {
                const img = new Image();
                img.onload = () => {
                    mascotImageLoaded = true;
                    resolve();
                };
                img.onerror = () => {
                    // Even on error, resolve to prevent hanging
                    resolve();
                };
                img.src = images.mascotFound;
            });
        }

        function createFloatingMascot() {
            // Only show on homepage and if mascot image is loaded
            const homepage = document.getElementById('homepage');
            if (homepage.classList.contains('hidden') || !mascotImageLoaded) {
                return;
            }

            // Remove existing floating mascot if any
            if (currentFloatingMascot && currentFloatingMascot.parentNode) {
                currentFloatingMascot.remove();
            }

            // Simple positioning logic - use viewport dimensions directly
            const viewportWidth = window.innerWidth;
            const viewportHeight = window.innerHeight;
            
            // Leave margins from screen edges
            const margin = 80;
            const maxSize = 80;
            
            // Random position with margins
            const x = margin + Math.random() * (viewportWidth - margin * 2 - maxSize);
            const y = margin + Math.random() * (viewportHeight - margin * 2 - maxSize);
            
            // Random size between 40px and 80px
            const size = 40 + Math.random() * 40;
            
            // Random rotation between -30° and +30°
            const rotation = (Math.random() - 0.5) * 60; // -30 to +30 degrees
            
            // Create floating mascot element
            const mascot = document.createElement('img');
            mascot.src = images.mascotFound; // Use colorful mascot
            mascot.className = 'floating-mascot';
            mascot.style.left = x + 'px';
            mascot.style.top = y + 'px';
            mascot.style.width = size + 'px';
            mascot.style.height = size + 'px';
            mascot.style.transform = `rotate(${rotation}deg)`;
            
            // Add to body (not homepage) for better visibility
            document.body.appendChild(mascot);
            currentFloatingMascot = mascot;
            
            // Fade in immediately since image is already loaded
            setTimeout(() => {
                if (mascot.parentNode) {
                    mascot.classList.add('visible', 'floating');
                }
            }, 50);
            
            // Fade out after 2 seconds
            setTimeout(() => {
                if (mascot.parentNode) {
                    mascot.classList.remove('visible');
                    // Remove element after fade transition
                    setTimeout(() => {
                        if (mascot.parentNode) {
                            mascot.remove();
                        }
                    }, 500);
                }
            }, 2000);
            
            // Schedule next mascot appearance (3-5 seconds)
            floatingMascotTimeout = setTimeout(createFloatingMascot, 3000 + Math.random() * 2000);
        }

        async function startFloatingMascotAnimation() {
            // Clear any existing timeout
            if (floatingMascotTimeout) {
                clearTimeout(floatingMascotTimeout);
            }
            
            // Wait for mascot image to load before starting animation
            if (!mascotImageLoaded) {
                await preloadMascotImage();
            }
            
            // Start the animation cycle only after image is loaded
            floatingMascotTimeout = setTimeout(createFloatingMascot, 1000);
        }

        function stopFloatingMascotAnimation() {
            // Clear timeout
            if (floatingMascotTimeout) {
                clearTimeout(floatingMascotTimeout);
                floatingMascotTimeout = null;
            }
            // Remove current mascot
            if (currentFloatingMascot && currentFloatingMascot.parentNode) {
                currentFloatingMascot.remove();
                currentFloatingMascot = null;
            }
        }

        // Translation system
        let currentLanguage = 'en';

        const translations = {
            en: {
                gameTitle: "Where's Jaidee?",
                gameSubtitle: "Find all the hidden Jaidee mascots!",
                findHidden: "Find all 10 hidden Jaidee",
                swipeExplore: "Swipe to explore & pinch to zoom",
                helpButton: "How to Play",
                copyrightNotice: "Unauthorised copying is prohibited",
                playgroundMap: "Playground",
                playgroundDesc: "Swings & slides",
                concertMap: "Mall Show",
                concertDesc: "Meeting Stage",
                playground2Map: "Playground 2", 
                playground2Desc: "More fun awaits",
                comicMap: "Comic Story",
                comicDesc: "Those memory",
                stageMap: "Stage",
                stageDesc: "Live performance",
                carnivalMap: "Carnival",
                carnivalDesc: "Amusement park",
                marketMap: "Bookfair",
                marketDesc: "Busy marketplace",
                restaurantMap: "Coffee Shop",
                restaurantDesc: "Supporting experience",
                concertHallMap: "Performance",
                concertHallDesc: "Final challenge",
                locked: "Locked",
                completed: "Completed",
                tryAgain: "Try Again",
                mainMenu: "Main Menu",
                victory: "Victory!",
                gameOver: "Game Over!",
                congratulations: "Congratulations! You found all the Jaidee mascots!",
                newMapUnlocked: "🔓 New map unlocked!",
                allMapsCompleted: "🎉 Congratulations! You've completed all maps!",
                betterLuck: "Better luck next time! You found",
                outOf: "out of 10 mascots.",
                continueBtn: "Continue",
                gotIt: "Got it!",
                howToPlayTitle: "How to Play",
                findHiddenTitle: "Find the Hidden Jaidee",
                findHiddenDesc: "Look for 10 hidden Jaidee mascots on each map. Click on them to find them!",
                navigateTitle: "Navigate & Zoom",
                navigateDesc: "Swipe to explore the map. Pinch to zoom in/out or use the zoom controls. Use the reset button to return to default view.",
                livesTitle: "Lives System",
                livesDesc: "You have 3 lives. Clicking in the wrong place will cost you a life. Game over when you run out!",
                hintsTitle: "Hints Available",
                hintsDesc: "Use up to 3 hints per map. A hint will highlight one hidden mascot and scroll to show it.",
                unlockTitle: "Unlock New Maps",
                unlockDesc: "Complete maps to unlock new ones. Find all 10 mascots to victory!"
            },
            zh: {
                gameTitle: "Jaidee在哪裡？",
                gameSubtitle: "找到所有隱藏的Jaidee！",
                findHidden: "找到所有10個隱藏的Jaidee",
                swipeExplore: "滑動探索並捏拉縮放",
                helpButton: "如何遊戲",
                copyrightNotice: "禁止未經授權的複製",
                playgroundMap: "遊樂場",
                playgroundDesc: "鞦韆和滑梯",
                concertMap: "商場",
                concertDesc: "見面舞台",
                playground2Map: "遊樂場2",
                playground2Desc: "更多樂趣等著你",
                comicMap: "漫畫故事",
                comicDesc: "哪些回憶",
                stageMap: "舞台",
                stageDesc: "現場表演",
                carnivalMap: "嘉年華",
                carnivalDesc: "遊樂園",
                marketMap: "書展",
                marketDesc: "繁忙的市場",
                restaurantMap: "咖啡廳",
                restaurantDesc: "應援體驗",
                concertHallMap: "表演",
                concertHallDesc: "最終挑戰",
                locked: "已鎖定",
                completed: "已完成",
                tryAgain: "再試一次",
                mainMenu: "主選單",
                victory: "勝利！",
                gameOver: "遊戲失敗！",
                congratulations: "恭喜！你找到了所有的Jaidee！",
                newMapUnlocked: "🔓 新地圖已解鎖！",
                allMapsCompleted: "🎉 恭喜！你已經完成了所有地圖！",
                betterLuck: "下次好運！你找到了",
                outOf: "個，共10個",
                continueBtn: "繼續",
                gotIt: "明白了！",
                howToPlayTitle: "如何遊玩",
                findHiddenTitle: "找到隱藏的Jaidee",
                findHiddenDesc: "在每張地圖上尋找10個隱藏的Jaidee。點擊來找到他們吧！",
                navigateTitle: "探索和縮放",
                navigateDesc: "滑動來探索地圖。捏拉縮放或使用縮放控制項。使用重設按鈕返回預設視比例圖。",
                livesTitle: "生命系統",
                livesDesc: "你有3條生命。點擊錯誤的地方會消耗一條生命。生命用完就結束此遊戲關卡！",
                hintsTitle: "可用提示",
                hintsDesc: "每張地圖最多使用3個提示。提示會高光顯示一個隱藏的吉祥物並標示他。",
                unlockTitle: "解鎖新地圖",
                unlockDesc: "完成地圖來解鎖新場景。找到所有Jaidee就勝出！"
            }
        };

        function updateLanguageDisplay() {
            const languageBtn = AppProtection.getElement('current-language');
            if (languageBtn) {
                languageBtn.textContent = currentLanguage === 'en' ? 'EN' : '中';
            }
        }

        function translatePage() {
            const t = translations[currentLanguage];
            
            // Update elements with data-translate attributes
            document.querySelectorAll('[data-translate]').forEach(element => {
                const key = element.getAttribute('data-translate');
                if (t[key]) {
                    AppProtection.safeSetContent(element, t[key]);
                }
            });

            // Update specific elements by content
            const gameTitle = document.querySelector('.swinging-title');
            if (gameTitle) AppProtection.safeSetContent(gameTitle, t.gameTitle);

            const gameSubtitle = document.querySelector('p.text-lg.md\\:text-xl.text-white.mb-4');
            if (gameSubtitle) AppProtection.safeSetContent(gameSubtitle, t.gameSubtitle);

            // Update instruction text
            const instructions = document.querySelectorAll('.text-white.text-sm.md\\:text-base.space-y-2.mb-6 p');
            if (instructions[0]) {
                instructions[0].innerHTML = `<span>🎯</span> ${t.findHidden}`;
            }
            if (instructions[1]) {
                instructions[1].innerHTML = `<span> 🤏🏻 </span> ${t.swipeExplore}`;
            }

            // Update map names and descriptions
            const mapData = [
                { id: 'map1-btn', title: t.playgroundMap, desc: t.playgroundDesc },
                { id: 'map2-btn', title: t.concertMap, desc: t.concertDesc },
                { id: 'map3-btn', title: t.playground2Map, desc: t.playground2Desc },
                { id: 'map4-btn', title: t.comicMap, desc: t.comicDesc },
                { id: 'map5-btn', title: t.stageMap, desc: t.stageDesc },
                { id: 'map6-btn', title: t.carnivalMap, desc: t.carnivalDesc },
                { id: 'map7-btn', title: t.marketMap, desc: t.marketDesc },
                { id: 'map8-btn', title: t.restaurantMap, desc: t.restaurantDesc },
                { id: 'map9-btn', title: t.concertHallMap, desc: t.concertHallDesc }
            ];

            mapData.forEach(map => {
                const mapBtn = AppProtection.getElement(map.id, false);
                if (mapBtn) {
                    const titleElement = mapBtn.querySelector('h3');
                    const descElement = mapBtn.querySelector('p');
                    if (titleElement) AppProtection.safeSetContent(titleElement, map.title);
                    if (descElement) {
                        // Check if map is completed or locked
                        if (descElement.textContent === 'Completed' || descElement.textContent === '已完成') {
                            AppProtection.safeSetContent(descElement, t.completed);
                        } else if (descElement.textContent === 'Locked' || descElement.textContent === '已锁定') {
                            AppProtection.safeSetContent(descElement, t.locked);
                        } else {
                            AppProtection.safeSetContent(descElement, map.desc);
                        }
                    }
                }
            });

            // Update victory modal
            const victoryTitle = document.querySelector('#victory-modal h3');
            if (victoryTitle) AppProtection.safeSetContent(victoryTitle, t.victory);
            
            const victoryMessage = document.querySelector('#victory-modal p');
            if (victoryMessage) AppProtection.safeSetContent(victoryMessage, t.congratulations);
            
            const victoryContinueBtn = AppProtection.getElement('victory-continue');
            if (victoryContinueBtn) AppProtection.safeSetContent(victoryContinueBtn, t.continueBtn);

            // Update game over modal
            const gameOverTitle = document.querySelector('#gameover-modal h3');
            if (gameOverTitle) AppProtection.safeSetContent(gameOverTitle, t.gameOver);
            
            // Update game over message (preserve the span with count)
            const gameOverMessage = document.querySelector('#gameover-modal p');
            if (gameOverMessage) {
                const finalCount = document.getElementById('final-count');
                const countValue = finalCount ? finalCount.textContent : '0';
                gameOverMessage.innerHTML = `${t.betterLuck} <span id="final-count">${countValue}</span> ${t.outOf}`;
            }
            
            const tryAgainBtn = AppProtection.getElement('gameover-retry');
            if (tryAgainBtn) AppProtection.safeSetContent(tryAgainBtn, t.tryAgain);
            
            const mainMenuBtn = AppProtection.getElement('gameover-menu');
            if (mainMenuBtn) AppProtection.safeSetContent(mainMenuBtn, t.mainMenu);

            // Update help modal
            const helpTitle = document.querySelector('#help-modal h3');
            if (helpTitle) AppProtection.safeSetContent(helpTitle, t.howToPlayTitle);

            const helpSections = [
                { title: t.findHiddenTitle, desc: t.findHiddenDesc },
                { title: t.navigateTitle, desc: t.navigateDesc },
                { title: t.livesTitle, desc: t.livesDesc },
                { title: t.hintsTitle, desc: t.hintsDesc },
                { title: t.unlockTitle, desc: t.unlockDesc }
            ];

            const helpItems = document.querySelectorAll('#help-modal .space-y-4 > div');
            helpItems.forEach((item, index) => {
                if (helpSections[index]) {
                    const titleEl = item.querySelector('h4');
                    const descEl = item.querySelector('p');
                    if (titleEl) AppProtection.safeSetContent(titleEl, helpSections[index].title);
                    if (descEl) AppProtection.safeSetContent(descEl, helpSections[index].desc);
                }
            });

            const helpCloseBtn = AppProtection.getElement('help-close');
            if (helpCloseBtn) AppProtection.safeSetContent(helpCloseBtn, t.gotIt);

            // Update copyright notice
            const copyrightNotice = AppProtection.getElement('copyright-notice');
            if (copyrightNotice) AppProtection.safeSetContent(copyrightNotice, t.copyrightNotice);

            updateLanguageDisplay();
        }

        function toggleLanguage() {
            currentLanguage = currentLanguage === 'en' ? 'zh' : 'en';
            translatePage();
            AppProtection.log(`Language switched to: ${currentLanguage}`, 'info');
        }

        // Language button event listener
        document.getElementById('language-btn').addEventListener('click', toggleLanguage);

        // Preload images
        Object.values(images).forEach(src => {
            const img = new Image();
            img.src = src;
        });



        // Help modal event listeners
        document.getElementById('help-btn').addEventListener('click', () => {
            document.getElementById('help-modal').classList.remove('hidden');
        });

        document.getElementById('help-close').addEventListener('click', () => {
            document.getElementById('help-modal').classList.add('hidden');
        });

        // Close help modal when clicking outside
        document.getElementById('help-modal').addEventListener('click', (e) => {
            if (e.target === e.currentTarget) {
                document.getElementById('help-modal').classList.add('hidden');
            }
        });

        // Start floating mascot animation when page loads
        document.addEventListener('DOMContentLoaded', () => {
            startFloatingMascotAnimation();
            
            // Initialize security system
            SecurityManager.init();
        });
    </script>

    <!-- Persistent Copyright Footer -->
    <footer class="fixed bottom-0 left-0 right-0 bg-gray-900 dark:bg-black text-white py-2 px-4 z-40 shadow-lg border-t border-gray-700 dark:border-gray-600">
        <div class="max-w-6xl mx-auto text-center">
            <p class="text-xs md:text-sm font-medium">
                <span id="copyright-notice" data-translate="copyrightNotice">Unauthorised copying is prohibited</span>
            </p>
        </div>
    </footer>
</body>
</html>
