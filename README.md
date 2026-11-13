<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EDUNAUTAS - Transformación Digital Educativa</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Chart.js for interactive survey charts -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Google Fonts: Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            500: '#0284c7',
                            600: '#0369a1',
                            700: '#075985',
                            900: '#0c4a6e',
                        },
                        space: {
                            800: '#0f172a',
                            900: '#020617',
                        },
                        accent: {
                            teal: '#14b8a6',
                            purple: '#8b5cf6',
                            amber: '#f59e0b',
                            emerald: '#10b981'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body { font-family: 'Inter', sans-serif; }
        .gradient-bg {
            background: linear-gradient(135deg, #020617 0%, #0c4a6e 50%, #0f172a 100%);
        }
        .glass-card {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(226, 232, 240, 0.8);
        }
        .glass-dark {
            background: rgba(15, 23, 42, 0.75);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(51, 65, 85, 0.5);
        }
        .custom-scrollbar::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 4px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 antialiased selection:bg-brand-500 selection:text-white">

    <!-- HEADER / NAVIGATION -->
    <header class="sticky top-0 z-50 bg-white/90 backdrop-filter backdrop-blur-md border-b border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <div class="flex items-center space-x-3">
                <!-- Mascot & Logo -->
                <div class="w-14 h-14 relative flex items-center justify-center">
                    <svg viewBox="0 0 200 200" class="w-full h-full drop-shadow-md">
                        <!-- Orbit -->
                        <path d="M 25 130 C 25 180, 175 180, 185 110 C 190 70, 130 50, 90 70" fill="none" stroke="#00b4d8" stroke-width="8" stroke-linecap="round"/>
                        <!-- Deep space circle background -->
                        <circle cx="100" cy="90" r="75" fill="#0b132b"/>
                        <!-- Stars in background -->
                        <circle cx="145" cy="50" r="4" fill="#38bdf8"/>
                        <circle cx="65" cy="45" r="3" fill="#a855f7"/>
                        <circle cx="155" cy="110" r="3.5" fill="#38bdf8"/>
                        <!-- Floating Blocks: Plus, Equals, Book -->
                        <rect x="35" y="100" width="22" height="22" rx="5" fill="#f59e0b" transform="rotate(-10 46 111)"/>
                        <text x="46" y="116" font-family="sans-serif" font-weight="900" font-size="16" fill="#ffffff" text-anchor="middle">+</text>

                        <rect x="45" y="125" width="22" height="22" rx="5" fill="#10b981" transform="rotate(5 56 136)"/>
                        <text x="56" y="141" font-family="sans-serif" font-weight="900" font-size="16" fill="#ffffff" text-anchor="middle">=</text>

                        <rect x="70" y="140" width="22" height="22" rx="5" fill="#3b82f6" transform="rotate(-15 81 151)"/>
                        <path d="M 76 148 Q 81 153 86 148 M 76 154 Q 81 159 86 154" stroke="#ffffff" stroke-width="2" fill="none"/>

                        <!-- Astronaut Body & Helmet -->
                        <circle cx="105" cy="80" r="38" fill="#ffffff"/>
                        <!-- Visor -->
                        <path d="M 85 78 C 85 62, 125 62, 125 78 C 125 94, 85 94, 85 78 Z" fill="#0f172a"/>
                        <!-- Happy Eyes in Visor -->
                        <path d="M 93 76 Q 98 70 103 76" fill="none" stroke="#38bdf8" stroke-width="3" stroke-linecap="round"/>
                        <path d="M 107 76 Q 112 70 117 76" fill="none" stroke="#38bdf8" stroke-width="3" stroke-linecap="round"/>
                        <!-- Ears / Antenna -->
                        <circle cx="66" cy="70" r="5" fill="#00b4d8"/>
                        <line x1="71" y1="72" x2="80" y2="76" stroke="#ffffff" stroke-width="3"/>
                        <!-- Gamepad in Astronaut Hands -->
                        <rect x="90" y="100" width="36" height="22" rx="8" fill="#1e293b"/>
                        <circle cx="98" cy="111" r="3" fill="#f59e0b"/>
                        <circle cx="118" cy="108" r="2" fill="#ef4444"/>
                        <circle cx="122" cy="113" r="2" fill="#3b82f6"/>
                    </svg>
                </div>
                <div>
                    <span class="text-2xl font-black tracking-tight bg-gradient-to-r from-cyan-600 via-brand-600 to-indigo-900 bg-clip-text text-transparent">EDUNAUTAS</span>
                    <span class="block text-[10px] font-extrabold uppercase tracking-widest text-slate-500">Videojuegos Educativos | CABA</span>
                </div>
            </div>
            
            <nav class="hidden md:flex items-center space-x-6 text-sm font-medium text-slate-600">
                <a href="#pitch" class="hover:text-brand-600 transition-colors">Propuesta</a>
                <a href="#juego-demo" class="hover:text-brand-600 transition-colors text-cyan-600 font-bold"><i class="fa-solid fa-gamepad mr-1"></i> Camino Edunauta</a>
                <a href="#supervision" class="hover:text-brand-600 transition-colors">Tablero IA (Fase II)</a>
                <a href="#arquitectura" class="hover:text-brand-600 transition-colors">Arquitectura</a>
                <a href="#roadmap" class="hover:text-brand-600 transition-colors">Roadmap</a>
                <a href="#encuesta" class="hover:text-brand-600 transition-colors">Datos Relevamiento</a>
            </nav>

            <div class="flex items-center space-x-3">
                <a href="#juego-demo" class="bg-gradient-to-r from-cyan-500 to-brand-600 hover:from-cyan-600 hover:to-brand-700 text-white font-bold text-xs px-4 py-2.5 rounded-xl shadow-md shadow-cyan-500/20 transition-all flex items-center space-x-2">
                    <i class="fa-solid fa-play"></i>
                    <span>Jugar Demo</span>
                </a>
            </div>
        </div>
    </header>

<!-- ... existing code ...">

    <!-- SECTION 1: PITCH & EXECUTIVE SUMMARY -->
    <section id="pitch" class="py-16 bg-white border-b border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-xs font-extrabold tracking-widest text-brand-600 uppercase">Resumen Ejecutivo</h2>
                <p class="mt-2 text-3xl font-extrabold text-slate-900 sm:text-4xl">El Desafío de la Transformación Digital</p>
                <p class="mt-4 text-slate-600">Un servicio institucional para potenciar el trabajo docente en el sector público sin delegar el criterio pedagógico.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Problema -->
                <div class="bg-slate-50 rounded-2xl p-6 border border-slate-200 shadow-sm hover:shadow-md transition-all">
                    <div class="w-12 h-12 bg-red-100 rounded-xl flex items-center justify-center text-red-600 text-xl font-bold mb-4">
                        <i class="fa-solid fa-triangle-exclamation"></i>
                    </div>
                    <h3 class="text-xl font-bold text-slate-900 mb-2">Situación Actual & Problema</h3>
                    <p class="text-sm text-slate-600 leading-relaxed mb-4">
                        En las secundarias estatales de CABA, la creación de actividades lúdicas es artesanal e individual, insumiendo entre 3 a 8 horas semanales. Las plataformas de mercado solo ofrecen trivias rígidas y capturan datos de estudiantes fuera de miEscuela.
                    </p>
                    <ul class="text-xs text-slate-500 space-y-2 border-t border-slate-200 pt-3">
                        <li class="flex items-start"><i class="fa-solid fa-xmark text-red-500 mr-2 mt-0.5"></i> 77,5% docentes no recibe feedback de uso.</li>
                        <li class="flex items-start"><i class="fa-solid fa-xmark text-red-500 mr-2 mt-0.5"></i> Riesgo de privacidad con datos de menores.</li>
                    </ul>
                </div>

                <!-- Solución -->
                <div class="bg-slate-50 rounded-2xl p-6 border border-brand-200 shadow-sm hover:shadow-md transition-all relative overflow-hidden">
                    <div class="w-12 h-12 bg-brand-100 rounded-xl flex items-center justify-center text-brand-600 text-xl font-bold mb-4">
                        <i class="fa-solid fa-wand-magic-sparkles"></i>
                    </div>
                    <h3 class="text-xl font-bold text-slate-900 mb-2">La Propuesta EDUNAUTAS</h3>
                    <p class="text-sm text-slate-600 leading-relaxed mb-4">
                        Servicio institucional integrado con cuentas <code class="bg-slate-200 px-1 py-0.5 rounded text-xs">@bue.edu.ar</code>. Combina 4 agentes con RAG para generar videojuegos estructurados desde el material fuente del docente, manteniendo siempre la aprobación humana explícita.
                    </p>
                    <ul class="text-xs text-slate-500 space-y-2 border-t border-slate-200 pt-3">
                        <li class="flex items-start"><i class="fa-solid fa-check text-emerald-500 mr-2 mt-0.5"></i> Reducción a &lt;30 min por experiencia.</li>
                        <li class="flex items-start"><i class="fa-solid fa-check text-emerald-500 mr-2 mt-0.5"></i> 100% privacidad de datos en el Ministerio.</li>
                    </ul>
                </div>

                <!-- Impacto & Fase II -->
                <div class="bg-slate-50 rounded-2xl p-6 border border-purple-200 shadow-sm hover:shadow-md transition-all">
                    <div class="w-12 h-12 bg-purple-100 rounded-xl flex items-center justify-center text-purple-600 text-xl font-bold mb-4">
                        <i class="fa-solid fa-chart-line"></i>
                    </div>
                    <h3 class="text-xl font-bold text-slate-900 mb-2">Impacto & Tablero Distrital</h3>
                    <p class="text-sm text-slate-600 leading-relaxed mb-4">
                        Los datos agregados alimentan un sistema de decisión para supervisores distritales (Fase II), sugiriendo asignación eficiente de facilitadores digitales y detección oportuna de puntos de dificultad curricular.
                    </p>
                    <ul class="text-xs text-slate-500 space-y-2 border-t border-slate-200 pt-3">
                        <li class="flex items-start"><i class="fa-solid fa-check text-purple-500 mr-2 mt-0.5"></i> Información agregada por escuela/distrito.</li>
                        <li class="flex items-start"><i class="fa-solid fa-check text-purple-500 mr-2 mt-0.5"></i> Human-in-the-loop en la supervisión.</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- NEW SECTION: INTERACTIVE MINIMALIST GAME "EL CAMINO EDUNAUTA" -->
    <section id="juego-demo" class="py-16 bg-slate-950 text-white relative overflow-hidden border-b border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-10">
                <div class="inline-flex items-center space-x-2 bg-cyan-500/10 text-cyan-400 text-xs font-semibold px-3 py-1 rounded-full border border-cyan-500/20 mb-3">
                    <i class="fa-solid fa-gamepad"></i>
                    <span>Experiencia Jugable Generada</span>
                </div>
                <h2 class="text-3xl font-extrabold text-white">El Camino Matemático del Edunauta</h2>
                <p class="text-slate-400 text-sm mt-2">
                    Ejemplo interactivo de una experiencia jugable minimalista: ayuda al Edunauta a avanzar respondiendo los cálculos para llegar a la meta.
                </p>
            </div>

            <div class="bg-slate-900 border border-slate-800 rounded-3xl p-6 lg:p-8 shadow-2xl relative">
                <!-- Game Canvas / Path Interface -->
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                    
                    <!-- Left: Path Visualization -->
                    <div class="lg:col-span-7 space-y-4">
                        <div class="flex items-center justify-between bg-slate-800/80 p-3 rounded-2xl border border-slate-700 text-xs">
                            <div class="flex items-center space-x-2">
                                <span class="w-3 h-3 rounded-full bg-cyan-400 animate-pulse"></span>
                                <span class="font-bold text-slate-200">Misión 1: ÁLGEBRA Y CÁLCULO RÁPIDO</span>
                            </div>
                            <span id="game-score-badge" class="font-mono bg-cyan-950 text-cyan-300 font-bold px-3 py-1 rounded-lg border border-cyan-500/30">Puntos: 0 / 500</span>
                        </div>

                        <!-- Track container -->
                        <div class="relative bg-slate-950 rounded-2xl p-6 border border-slate-800 h-64 flex items-center justify-between overflow-hidden">
                            <!-- Curved Track SVG Line -->
                            <svg class="absolute inset-0 w-full h-full stroke-slate-800" stroke-width="8" fill="none">
                                <path d="M 40 130 C 150 40, 280 220, 400 130 C 520 40, 650 200, 750 130" stroke-dasharray="8 8"/>
                            </svg>

                            <!-- Nodes / Checkpoints along the path -->
                            <div class="relative z-10 w-full flex justify-between items-center px-4">
                                <!-- Node 1 (Start) -->
                                <div id="node-0" class="w-12 h-12 rounded-2xl bg-cyan-500 text-slate-950 flex items-center justify-center font-bold text-sm shadow-lg shadow-cyan-500/50 transition-all">
                                    <i class="fa-solid fa-flag-checkered"></i>
                                </div>
                                <!-- Node 2 -->
                                <div id="node-1" class="w-10 h-10 rounded-2xl bg-slate-800 text-slate-400 flex items-center justify-center font-bold text-xs border border-slate-700 transition-all">
                                    1
                                </div>
                                <!-- Node 3 -->
                                <div id="node-2" class="w-10 h-10 rounded-2xl bg-slate-800 text-slate-400 flex items-center justify-center font-bold text-xs border border-slate-700 transition-all">
                                    2
                                </div>
                                <!-- Node 4 -->
                                <div id="node-3" class="w-10 h-10 rounded-2xl bg-slate-800 text-slate-400 flex items-center justify-center font-bold text-xs border border-slate-700 transition-all">
                                    3
                                </div>
                                <!-- Node 5 (Goal) -->
                                <div id="node-4" class="w-12 h-12 rounded-2xl bg-amber-500/20 text-amber-400 border border-amber-500/40 flex items-center justify-center font-bold text-sm transition-all">
                                    <i class="fa-solid fa-trophy"></i>
                                </div>
                            </div>

                            <!-- Animated Edunauta Avatar on Track -->
                            <div id="edunauta-player" class="absolute z-20 transition-all duration-700 ease-out flex flex-col items-center" style="left: 20px; top: 100px;">
                                <div class="w-12 h-12 bg-cyan-400 rounded-full p-1 shadow-lg shadow-cyan-400/50 animate-bounce">
                                    <svg viewBox="0 0 200 200" class="w-full h-full">
                                        <circle cx="100" cy="90" r="75" fill="#0b132b"/>
                                        <circle cx="105" cy="80" r="38" fill="#ffffff"/>
                                        <path d="M 85 78 C 85 62, 125 62, 125 78 C 125 94, 85 94, 85 78 Z" fill="#0f172a"/>
                                        <path d="M 93 76 Q 98 70 103 76" fill="none" stroke="#38bdf8" stroke-width="5"/>
                                        <path d="M 107 76 Q 112 70 117 76" fill="none" stroke="#38bdf8" stroke-width="5"/>
                                    </svg>
                                </div>
                                <span class="text-[9px] font-bold uppercase tracking-wider bg-cyan-950 text-cyan-300 px-2 py-0.5 rounded-full border border-cyan-500/40 mt-1">Edunauta</span>
                            </div>
                        </div>

                        <!-- Progress Bar -->
                        <div class="w-full bg-slate-800 h-2.5 rounded-full overflow-hidden">
                            <div id="game-progress-bar" class="bg-gradient-to-r from-cyan-400 to-teal-400 h-full w-0 transition-all duration-500"></div>
                        </div>
                    </div>

                    <!-- Right: Interactive Calculation Challenge Panel -->
                    <div class="lg:col-span-5">
                        <div class="bg-slate-950 border border-slate-800 rounded-2xl p-6 space-y-5">
                            <div class="flex items-center justify-between border-b border-slate-800 pb-3">
                                <span class="text-xs font-bold text-slate-400 uppercase tracking-wider">Desafío del Camino</span>
                                <span id="challenge-step-title" class="text-xs font-bold text-cyan-400">Paso 1 de 4</span>
                            </div>

                            <!-- Question Box -->
                            <div id="game-question-box" class="space-y-3">
                                <h3 id="game-question-text" class="text-lg font-bold text-white">¿Cuál es el resultado de 12 + 15?</h3>
                                <p class="text-xs text-slate-400">Resuelve la cuenta correctamente para avanzar la nave del Edunauta hacia la meta.</p>

                                <!-- Answer Options -->
                                <div id="game-options-container" class="grid grid-cols-2 gap-3 pt-2">
                                    <!-- Options generated dynamically -->
                                </div>
                            </div>

                            <!-- Feedback Alert -->
                            <div id="game-feedback" class="hidden p-3 rounded-xl text-xs font-semibold"></div>

                            <!-- Game Complete Box -->
                            <div id="game-complete-box" class="hidden text-center space-y-4 py-4">
                                <div class="w-16 h-16 bg-amber-500/20 text-amber-400 rounded-2xl mx-auto flex items-center justify-center text-3xl shadow-lg shadow-amber-500/20">
                                    <i class="fa-solid fa-crown"></i>
                                </div>
                                <div>
                                    <h3 class="text-xl font-extrabold text-white">¡Meta Alcanzada!</h3>
                                    <p class="text-xs text-slate-400 mt-1">El Edunauta ha completado todo el recorrido pedagógico con éxito.</p>
                                </div>
                                <button onclick="restartEdunautaGame()" class="bg-cyan-500 hover:bg-cyan-400 text-slate-950 font-bold text-xs px-6 py-2.5 rounded-xl transition-all shadow-md">
                                    Volver a Jugar
                                </button>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </section>

    <!-- SECTION 2: INTERACTIVE SUPERVISOR DASHBOARD (FASE II DEMO) -->
    <section id="supervision" class="py-16 bg-slate-900 text-white relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-8">
                <div>
                    <div class="inline-flex items-center space-x-2 bg-purple-500/20 text-purple-300 text-xs font-semibold px-3 py-1 rounded-full border border-purple-500/30 mb-3">
                        <i class="fa-solid fa-microchip"></i>
                        <span>Fase II - Herramienta de Innovación para Líderes</span>
                    </div>
                    <h2 class="text-3xl font-extrabold">Tablero de Supervisión Distrital con IA</h2>
                    <p class="text-slate-400 text-sm mt-1">Simulación interactiva con modelos de lenguaje y analítica agregada por escuelas.</p>
                </div>
                <div class="mt-4 md:mt-0 flex items-center space-x-2">
                    <span class="text-xs text-slate-400">Distrito Escolar Seleccionado:</span>
                    <select id="district-select" class="bg-slate-800 border border-slate-700 text-cyan-300 text-xs rounded-lg px-3 py-2 font-semibold focus:outline-none focus:border-cyan-500">
                        <option value="DE1">Distrito Escolar N° 01 (Piloto)</option>
                        <option value="DE4">Distrito Escolar N° 04</option>
                        <option value="DE7">Distrito Escolar N° 07</option>
                    </select>
                </div>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                <!-- Left: School Metrics Table & Allocation Controls -->
                <div class="lg:col-span-7 space-y-6">
                    <!-- Metrics Table Card -->
                    <div class="bg-slate-800/90 rounded-2xl p-6 border border-slate-700 shadow-xl">
                        <div class="flex items-center justify-between mb-4">
                            <h3 class="font-bold text-sm text-slate-200 uppercase tracking-wider">Métricas de Adopción y Dificultad Escolar</h3>
                            <span class="text-xs text-slate-400"><i class="fa-solid fa-lock text-emerald-400 mr-1"></i> Sin datos personales</span>
                        </div>
                        <div class="overflow-x-auto custom-scrollbar">
                            <table class="w-full text-left text-xs">
                                <thead>
                                    <tr class="text-slate-400 border-b border-slate-700">
                                        <th class="pb-3 font-semibold">Escuela</th>
                                        <th class="pb-3 font-semibold">Adopción Docente</th>
                                        <th class="pb-3 font-semibold">Punto Dificultad Detectado</th>
                                        <th class="pb-3 font-semibold text-right">Horas Asignadas</th>
                                    </tr>
                                </thead>
                                <tbody id="schools-tbody" class="divide-y divide-slate-700/50">
                                    <!-- Dynamic Rows populated by JS -->
                                </tbody>
                            </table>
                        </div>
                    </div>

                    <!-- Facilitator Hours Allocation Simulator -->
                    <div class="bg-slate-800/90 rounded-2xl p-6 border border-slate-700 shadow-xl space-y-4">
                        <div class="flex items-center justify-between">
                            <div>
                                <h3 class="font-bold text-sm text-slate-200">Simulador de Asignación de Horas de Acompañamiento</h3>
                                <p class="text-xs text-slate-400">Distribuye el presupuesto semanal de Horas de Facilitadores Pedagógicos Digitales (FPD).</p>
                            </div>
                            <div class="text-right">
                                <span id="hours-remaining" class="text-xl font-black text-cyan-400">12</span>
                                <span class="text-xs text-slate-400 block">Horas Disponibles</span>
                            </div>
                        </div>

                        <div id="allocator-controls" class="space-y-3">
                            <!-- Sliders populated dynamically -->
                        </div>
                    </div>
                </div>

                <!-- Right: AI Recommendation Engine Output -->
                <div class="lg:col-span-5 space-y-6">
                    <div class="bg-gradient-to-b from-slate-800 to-slate-850 rounded-2xl p-6 border border-purple-500/30 shadow-2xl relative overflow-hidden">
                        <div class="flex items-center justify-between pb-4 border-b border-slate-700">
                            <div class="flex items-center space-x-2">
                                <div class="w-8 h-8 rounded-lg bg-purple-600/30 text-purple-400 flex items-center justify-center font-bold">
                                    <i class="fa-solid fa-robot"></i>
                                </div>
                                <div>
                                    <h3 class="font-bold text-sm text-white">Agente Recomendador IA</h3>
                                    <span class="text-[10px] text-purple-300">Modelo Explicable + Human in the loop</span>
                                </div>
                            </div>
                            <button id="btn-generate-ai" onclick="generateAIRecommendations()" class="bg-purple-600 hover:bg-purple-500 text-white font-semibold text-xs px-3 py-1.5 rounded-lg transition-all flex items-center space-x-1 shadow-md shadow-purple-600/30">
                                <i class="fa-solid fa-sparkles"></i>
                                <span>Generar Recomendaciones</span>
                            </button>
                        </div>

                        <!-- Generated Content Box -->
                        <div id="ai-output-container" class="mt-4 space-y-4 text-xs">
                            <div id="ai-placeholder" class="py-12 text-center text-slate-500 space-y-2">
                                <i class="fa-solid fa-brain text-3xl opacity-30"></i>
                                <p>Haz clic en "Generar Recomendaciones" para activar la inferencia basada en los datos actuales del distrito.</p>
                            </div>

                            <div id="ai-results" class="hidden space-y-4">
                                <div class="p-3 bg-purple-950/40 border border-purple-500/20 rounded-xl text-purple-200 leading-relaxed" id="ai-summary">
                                    <!-- Summary text -->
                                </div>

                                <div class="space-y-3" id="ai-recommendations-list">
                                    <!-- Action cards generated by JS -->
                                </div>
                            </div>
                        </div>

                        <!-- Feedback Decisions Log -->
                        <div class="mt-6 border-t border-slate-700 pt-4">
                            <div class="flex items-center justify-between text-[11px] text-slate-400 mb-2">
                                <span>Registro de Decisiones del Supervisor:</span>
                                <span id="decisions-count" class="font-mono text-cyan-400">0 aprobadas / 0 descartadas</span>
                            </div>
                            <div id="decisions-log" class="text-[10px] font-mono text-slate-400 bg-slate-900/60 p-2 rounded-lg max-h-24 overflow-y-auto space-y-1">
                                <em>Esperando intervenciones del supervisor...</em>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION 3: ARCHITECTURE & ROADMAP -->
    <section id="arquitectura" class="py-16 bg-slate-100 border-b border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-12">
                <h2 class="text-xs font-extrabold tracking-widest text-brand-600 uppercase">Diseño Técnico y Planificación</h2>
                <p class="mt-2 text-3xl font-extrabold text-slate-900">Arquitectura Digital y Roadmap</p>
                <p class="mt-3 text-slate-600 text-sm">Transición de la situación actual (As-Is) hacia la arquitectura de dos velocidades (To-Be) y fases de avance por hitos (Gates).</p>
            </div>

            <!-- Tabs Navigation -->
            <div class="flex justify-center mb-8">
                <div class="bg-slate-200 p-1 rounded-xl inline-flex space-x-1 text-xs font-bold">
                    <button id="tab-btn-asis" onclick="switchTechView('asis')" class="px-5 py-2.5 rounded-lg transition-all bg-white text-slate-900 shadow-sm">Arquitectura Actual (As-Is)</button>
                    <button id="tab-btn-tobe" onclick="switchTechView('tobe')" class="px-5 py-2.5 rounded-lg transition-all text-slate-600 hover:text-slate-900">Arquitectura Deseada (To-Be)</button>
                </div>
            </div>

            <!-- View 1: As-Is Architecture -->
            <div id="view-asis" class="bg-white rounded-2xl p-8 border border-slate-200 shadow-sm space-y-6">
                <div class="flex items-center justify-between pb-4 border-b border-slate-200">
                    <div>
                        <h3 class="font-bold text-lg text-slate-900">Estado Actual: Fragmentación y Brechas Tecnológicas</h3>
                        <p class="text-xs text-slate-500">Datos desconectados, uso personal de plataformas y falta de analítica agregada.</p>
                    </div>
                    <span class="bg-red-100 text-red-700 font-bold px-3 py-1 rounded-full text-xs">Brechas B1 a B6</span>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 text-xs">
                    <div class="p-4 bg-slate-50 border border-slate-200 rounded-xl space-y-2">
                        <div class="font-bold text-slate-800 text-sm flex items-center justify-between">
                            <span>Sistemas CABA</span>
                            <i class="fa-solid fa-building-columns text-slate-400"></i>
                        </div>
                        <ul class="space-y-2 text-slate-600">
                            <li class="p-2 bg-white rounded border border-slate-200"><strong>miEscuela:</strong> Solo datos administrativos y asistencia. Sin registro lúdico.</li>
                            <li class="p-2 bg-white rounded border border-slate-200"><strong>Cuentas @bue.edu.ar:</strong> Subutilizadas para SSO en herramientas didácticas.</li>
                            <li class="p-2 bg-white rounded border border-slate-200"><strong>Plan Sarmiento:</strong> Netbooks y conectividad escolar heterogénea.</li>
                        </ul>
                    </div>

                    <div class="p-4 bg-red-50/50 border border-red-200 rounded-xl space-y-2">
                        <div class="font-bold text-red-900 text-sm flex items-center justify-between">
                            <span>Herramientas Externas</span>
                            <i class="fa-solid fa-cloud-arrow-up text-red-400"></i>
                        </div>
                        <ul class="space-y-2 text-red-800">
                            <li class="p-2 bg-white rounded border border-red-200"><strong>Plantillas Pagas:</strong> Kahoot / Wordwall con cuentas personales y bajo vuelo pedagógico.</li>
                            <li class="p-2 bg-white rounded border border-red-200"><strong>IA no normada:</strong> Consultas directas en ChatGPT sin verificación contra material propio.</li>
                        </ul>
                    </div>

                    <div class="p-4 bg-amber-50/50 border border-amber-200 rounded-xl space-y-2">
                        <div class="font-bold text-amber-900 text-sm flex items-center justify-between">
                            <span>Consecuencia Directa</span>
                            <i class="fa-solid fa-circle-exclamation text-amber-500"></i>
                        </div>
                        <p class="text-amber-800 leading-relaxed">
                            Los datos de los estudiantes quedan atrapados en servidores de terceros sin custodia del Ministerio. Ni las escuelas ni la supervisión reciben información sobre la efectividad de las actividades.
                        </p>
                    </div>
                </div>
            </div>

            <!-- View 2: To-Be Architecture -->
            <div id="view-tobe" class="hidden bg-slate-900 text-white rounded-2xl p-8 border border-slate-800 shadow-xl space-y-6">
                <div class="flex items-center justify-between pb-4 border-b border-slate-800">
                    <div>
                        <h3 class="font-bold text-lg text-cyan-400">Estado Deseado: Arquitectura de Dos Velocidades</h3>
                        <p class="text-xs text-slate-400">Capa de experiencia ágil con orquestación de agentes sobre infraestructura segura del Ministerio.</p>
                    </div>
                    <span class="bg-cyan-500/20 text-cyan-300 font-bold px-3 py-1 rounded-full text-xs border border-cyan-500/30">EDUNAUTAS To-Be</span>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-4 gap-4 text-xs">
                    <!-- Layer 1 -->
                    <div class="p-4 bg-slate-800 rounded-xl border border-slate-700 space-y-3">
                        <div class="font-bold text-cyan-300 uppercase tracking-wider text-[11px]">1. Capa Experiencia</div>
                        <div class="p-2.5 bg-slate-900 rounded border border-slate-700">Editor Docente (Revisar/Aprobar)</div>
                        <div class="p-2.5 bg-slate-900 rounded border border-slate-700">Reproductor Alumno (QR/Web)</div>
                        <div class="p-2.5 bg-slate-900 rounded border border-purple-500/40">Tablero Supervisión IA</div>
                    </div>

                    <!-- Layer 2 -->
                    <div class="p-4 bg-slate-800 rounded-xl border border-slate-700 space-y-3">
                        <div class="font-bold text-blue-300 uppercase tracking-wider text-[11px]">2. Orquestador Agéntico</div>
                        <div class="p-2 bg-blue-950/50 rounded border border-blue-500/30">Agente Pedagógico (RAG)</div>
                        <div class="p-2 bg-blue-950/50 rounded border border-blue-500/30">Agente Diseño Lúdico</div>
                        <div class="p-2 bg-blue-950/50 rounded border border-blue-500/30">Agente de Validación Fuente</div>
                        <div class="p-1.5 bg-amber-500/10 rounded border border-amber-500/30 text-[10px] text-amber-300">Filtro Anonimización Previas API</div>
                    </div>

                    <!-- Layer 3 -->
                    <div class="p-4 bg-slate-800 rounded-xl border border-slate-700 space-y-3">
                        <div class="font-bold text-teal-300 uppercase tracking-wider text-[11px]">3. Motor de Juego</div>
                        <div class="p-2.5 bg-slate-900 rounded border border-slate-700">Runtime Web Liviano</div>
                        <div class="p-2.5 bg-slate-900 rounded border border-slate-700">Biblioteca Controlada de Mecánicas</div>
                    </div>

                    <!-- Layer 4 -->
                    <div class="p-4 bg-slate-800 rounded-xl border border-slate-700 space-y-3">
                        <div class="font-bold text-slate-300 uppercase tracking-wider text-[11px]">4. Datos & Integración</div>
                        <div class="p-2 bg-slate-900 rounded border border-slate-700">Repositorio Material Docente</div>
                        <div class="p-2 bg-slate-900 rounded border border-slate-700">Almacén Analítica Agregada</div>
                        <div class="p-2 bg-slate-900 rounded border border-slate-700">SSO Cuentas @bue.edu.ar</div>
                    </div>
                </div>
            </div>

            <!-- ROADMAP SECTION -->
            <div id="roadmap" class="mt-12 bg-white rounded-2xl p-8 border border-slate-200 shadow-sm space-y-6">
                <div class="flex flex-col md:flex-row md:items-center justify-between pb-4 border-b border-slate-200">
                    <div>
                        <h3 class="font-bold text-lg text-slate-900">Roadmap de Implementación y Decisiones de Avance (Gates)</h3>
                        <p class="text-xs text-slate-500">Planificación en 3 Horizontes (24 meses) condicionados por evidencia empírica.</p>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <!-- H1 -->
                    <div class="border border-slate-200 rounded-xl p-5 bg-slate-50 relative">
                        <div class="flex items-center justify-between mb-3">
                            <span class="text-xs font-bold uppercase tracking-wider text-brand-600">Horizonte 1 (Meses 0 - 6)</span>
                            <span class="bg-brand-100 text-brand-700 text-[10px] font-bold px-2 py-0.5 rounded">Construir MVP</span>
                        </div>
                        <h4 class="font-bold text-sm text-slate-900 mb-2">P0 - P4: Núcleo e Integración</h4>
                        <ul class="text-xs text-slate-600 space-y-2 mb-4">
                            <li class="flex items-center"><i class="fa-solid fa-chevron-right text-brand-500 text-[10px] mr-2"></i> P1: Biblioteca Pedagógica (2 géneros).</li>
                            <li class="flex items-center"><i class="fa-solid fa-chevron-right text-brand-500 text-[10px] mr-2"></i> P2: MVP Carga, Orquestación y Editor.</li>
                            <li class="flex items-center"><i class="fa-solid fa-chevron-right text-brand-500 text-[10px] mr-2"></i> P3/P4: Integración SSO CABA & Analítica.</li>
                        </ul>
                        <div class="bg-amber-50 border border-amber-200 rounded-lg p-2.5 text-[11px] text-amber-900">
                            <strong>Gate G1 (Usabilidad - M6):</strong> Docentes sin conocimientos técnicos publican en &lt;1 hora.
                        </div>
                    </div>

                    <!-- H2 -->
                    <div class="border border-purple-200 rounded-xl p-5 bg-purple-50/40 relative">
                        <div class="flex items-center justify-between mb-3">
                            <span class="text-xs font-bold uppercase tracking-wider text-purple-600">Horizonte 2 (Meses 6 - 14)</span>
                            <span class="bg-purple-100 text-purple-700 text-[10px] font-bold px-2 py-0.5 rounded">Pilotear & Evaluar</span>
                        </div>
                        <h4 class="font-bold text-sm text-slate-900 mb-2">P5 & P4b: Piloto Distrital + Tablero</h4>
                        <ul class="text-xs text-slate-600 space-y-2 mb-4">
                            <li class="flex items-center"><i class="fa-solid fa-chevron-right text-purple-500 text-[10px] mr-2"></i> P5: Piloto en Distrito con Escuela de Maestros.</li>
                            <li class="flex items-center"><i class="fa-solid fa-chevron-right text-purple-500 text-[10px] mr-2"></i> P4b: Tablero IA para Supervisión (Fase II).</li>
                            <li class="flex items-center"><i class="fa-solid fa-chevron-right text-purple-500 text-[10px] mr-2"></i> P6: Evaluación rigurosa de impacto.</li>
                        </ul>
                        <div class="bg-purple-100 border border-purple-200 rounded-lg p-2.5 text-[11px] text-purple-900">
                            <strong>Gates G2/G3/G4:</strong> 40% adopción docente y costo inferior a USD 1 por experiencia.
                        </div>
                    </div>

                    <!-- H3 -->
                    <div class="border border-teal-200 rounded-xl p-5 bg-teal-50/40 relative">
                        <div class="flex items-center justify-between mb-3">
                            <span class="text-xs font-bold uppercase tracking-wider text-teal-600">Horizonte 3 (Meses 14 - 24)</span>
                            <span class="bg-teal-100 text-teal-700 text-[10px] font-bold px-2 py-0.5 rounded">Escalar</span>
                        </div>
                        <h4 class="font-bold text-sm text-slate-900 mb-2">P7 & P8: Escalamiento e Intercambio</h4>
                        <ul class="text-xs text-slate-600 space-y-2 mb-4">
                            <li class="flex items-center"><i class="fa-solid fa-chevron-right text-teal-500 text-[10px] mr-2"></i> P7: Despliegue gradual a los 21 distritos.</li>
                            <li class="flex items-center"><i class="fa-solid fa-chevron-right text-teal-500 text-[10px] mr-2"></i> P8: Biblioteca compartida con curaduría docente.</li>
                        </ul>
                        <div class="bg-teal-100 border border-teal-200 rounded-lg p-2.5 text-[11px] text-teal-900">
                            <strong>Gate G5 (Mes 18):</strong> Réplica eficiente en múltiples distritos estatales.
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION 4: SURVEY DATA INSIGHTS -->
    <section id="encuesta" class="py-16 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-12">
                <h2 class="text-xs font-extrabold tracking-widest text-brand-600 uppercase">Evidencia Empírica</h2>
                <p class="mt-2 text-3xl font-extrabold text-slate-900">Resultados del Relevamiento Docente</p>
                <p class="mt-3 text-slate-600 text-sm">Línea de base construida con encuesta a 40 docentes (subgrupo foco: nivel secundario estatal).</p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
                <!-- Chart 1: Time Preparation vs Barriers -->
                <div class="bg-slate-50 p-6 rounded-2xl border border-slate-200 shadow-sm">
                    <h3 class="font-bold text-sm text-slate-800 mb-4 text-center">Horas Semanales Dedicadas a Preparar Materiales</h3>
                    <div class="h-64 relative">
                        <canvas id="chart-hours"></canvas>
                    </div>
                    <p class="text-[11px] text-slate-500 mt-3 text-center">El 63.6% de docentes de secundaria dedica más de 5 horas semanales a la adaptación de clases.</p>
                </div>

                <!-- Chart 2: AI Use & Conditions -->
                <div class="bg-slate-50 p-6 rounded-2xl border border-slate-200 shadow-sm">
                    <h3 class="font-bold text-sm text-slate-800 mb-4 text-center">Condiciones Imprescindibles para Adoptar la IA</h3>
                    <div class="h-64 relative">
                        <canvas id="chart-conditions"></canvas>
                    </div>
                    <p class="text-[11px] text-slate-500 mt-3 text-center">Respalda el diseño: la gratuidad, el control de aprobación y la privacidad son requisitos no negociables.</p>
                </div>
            </div>

            <!-- Key Survey Takeaways Grid -->
            <div class="mt-8 grid grid-cols-2 md:grid-cols-4 gap-4 text-center">
                <div class="p-4 bg-brand-50 rounded-xl border border-brand-100">
                    <span class="block text-2xl font-black text-brand-600">81.8%</span>
                    <span class="text-xs text-slate-600 font-medium">Señala la Falta de Tiempo como barrera principal</span>
                </div>
                <div class="p-4 bg-purple-50 rounded-xl border border-purple-100">
                    <span class="block text-2xl font-black text-purple-600">77.5%</span>
                    <span class="text-xs text-slate-600 font-medium">Nunca o rara vez recibe feedback institucional</span>
                </div>
                <div class="p-4 bg-teal-50 rounded-xl border border-teal-100">
                    <span class="block text-2xl font-black text-teal-600">81.8%</span>
                    <span class="text-xs text-slate-600 font-medium">Interés (puntaje 4 o 5) en usar EDUNAUTAS</span>
                </div>
                <div class="p-4 bg-amber-50 rounded-xl border border-amber-100">
                    <span class="block text-2xl font-black text-amber-600">55.0%</span>
                    <span class="text-xs text-slate-600 font-medium">Dispuesto a invertir hasta 30 min por juego</span>
                </div>
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer class="bg-slate-950 text-slate-400 py-12 border-t border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-4">
            <div class="flex items-center justify-center space-x-2">
                <div class="w-8 h-8 rounded-lg bg-brand-600 flex items-center justify-center text-white">
                    <i class="fa-solid fa-gamepad text-sm"></i>
                </div>
                <span class="text-lg font-bold text-white tracking-wider">EDUNAUTAS</span>
            </div>
            <p class="text-xs max-w-xl mx-auto leading-relaxed">
                Trabajo Final de Grado - Licenciatura en Tecnologías Digitales (CCC) | Universidad de la Ciudad de Buenos Aires.<br>
                Asignatura: Transformación Digital en las Organizaciones. Autores: José Hiebaum & José Quinteros (2026).
            </p>
            <p class="text-[10px] text-slate-600">
                Ministerio de Educación de la Ciudad Autónoma de Buenos Aires. Documentación técnica y maquetación interactiva.
            </p>
        </div>
    </footer>

    <!-- INTERACTIVE JAVASCRIPT LOGIC -->
    <script>
        // Data for District Schools (Fase II Simulation)
        const schoolData = {
            DE1: [
                { name: "EEM N° 1 D.E. 1", adoption: 65, difficulty: "Ecuaciones Cuadráticas (Matemática 3°)", activeGames: 12, hours: 3 },
                { name: "Colegio N° 3 D.E. 1", adoption: 28, difficulty: "Comprensión Lectora / Mitología (Lengua 1°)", activeGames: 4, hours: 5 },
                { name: "Escuela Técnica N° 4 D.E. 1", adoption: 82, difficulty: "Leyes de Newton (Física 4°)", activeGames: 18, hours: 1 },
                { name: "Liceo N° 1 D.E. 1", adoption: 40, difficulty: "Revolución de Mayo (Historia 2°)", activeGames: 7, hours: 3 }
            ],
            DE4: [
                { name: "EEM N° 2 D.E. 4", adoption: 22, difficulty: "Ecosistemas y Cadenas Tróficas (Biología 2°)", activeGames: 3, hours: 4 },
                { name: "Colegio N° 8 D.E. 4", adoption: 55, difficulty: "Fracciones y Proporciones (Matemática 1°)", activeGames: 9, hours: 4 },
                { name: "Escuela Técnica N° 1 D.E. 4", adoption: 74, difficulty: "Circuitos Eléctricos (Tecnología 3°)", activeGames: 15, hours: 4 }
            ],
            DE7: [
                { name: "Liceo N° 3 D.E. 7", adoption: 35, difficulty: "Sintaxis y Oraciones Compuestas (Lengua 4°)", activeGames: 5, hours: 6 },
                { name: "EEM N° 5 D.E. 7", adoption: 70, difficulty: "Tabla Periódica / Enlaces (Química 3°)", activeGames: 14, hours: 3 },
                { name: "Colegio N° 12 D.E. 7", adoption: 48, difficulty: "Geografía Física de Argentina (Geografía 2°)", activeGames: 8, hours: 3 }
            ]
        };

        // --- GAME LOGIC FOR "EL CAMINO EDUNAUTA" ---
        const gameQuestions = [
            { q: "¿Cuál es el resultado de 14 + 18?", options: ["28", "32", "34", "30"], correct: 1 },
            { q: "Si 3x = 27, ¿cuál es el valor de x?", options: ["6", "9", "8", "7"], correct: 1 },
            { q: "¿Cuánto es el 25% de 200?", options: ["50", "40", "25", "60"], correct: 0 },
            { q: "¿Resultado de (8 × 5) - 12?", options: ["24", "26", "28", "32"], correct: 2 }
        ];

        let currentGameStep = 0;
        let gameScore = 0;

        function renderGameStep() {
            const stepTitle = document.getElementById("challenge-step-title");
            const questionText = document.getElementById("game-question-text");
            const optionsContainer = document.getElementById("game-options-container");
            const feedbackBox = document.getElementById("game-feedback");

            feedbackBox.classList.add("hidden");

            if (currentGameStep >= gameQuestions.length) {
                // Game Finished
                document.getElementById("game-question-box").classList.add("hidden");
                document.getElementById("game-complete-box").classList.remove("hidden");
                document.getElementById("edunauta-player").style.left = "82%";
                document.getElementById("game-progress-bar").style.width = "100%";
                return;
            }

            const current = gameQuestions[currentGameStep];
            stepTitle.innerText = `Paso ${currentGameStep + 1} de ${gameQuestions.length}`;
            questionText.innerText = current.q;
            optionsContainer.innerHTML = "";

            current.options.forEach((opt, idx) => {
                const btn = document.createElement("button");
                btn.className = "p-3 bg-slate-900 border border-slate-700 hover:border-cyan-500 hover:bg-cyan-950/40 text-slate-200 font-bold rounded-xl transition-all text-sm";
                btn.innerText = opt;
                btn.onclick = () => checkGameAnswer(idx);
                optionsContainer.appendChild(btn);
            });

            // Position character dynamically across 4 steps
            const leftPercents = ["5%", "25%", "45%", "65%"];
            document.getElementById("edunauta-player").style.left = leftPercents[currentGameStep];
            document.getElementById("game-progress-bar").style.width = `${(currentGameStep / gameQuestions.length) * 100}%`;
        }

        function checkGameAnswer(selectedIndex) {
            const current = gameQuestions[currentGameStep];
            const feedbackBox = document.getElementById("game-feedback");
            feedbackBox.classList.remove("hidden");

            if (selectedIndex === current.correct) {
                gameScore += 125;
                document.getElementById("game-score-badge").innerText = `Puntos: ${gameScore} / 500`;
                feedbackBox.className = "p-3 rounded-xl text-xs font-semibold bg-emerald-500/20 border border-emerald-500/40 text-emerald-300";
                feedbackBox.innerText = "¡Correcto! El Edunauta avanza en el camino.";

                // Highlight nodes
                const node = document.getElementById(`node-${currentGameStep + 1}`);
                if (node) {
                    node.className = "w-10 h-10 rounded-2xl bg-cyan-500 text-slate-950 font-bold text-xs flex items-center justify-center shadow-lg shadow-cyan-500/50";
                }

                currentGameStep++;
                setTimeout(renderGameStep, 1000);
            } else {
                feedbackBox.className = "p-3 rounded-xl text-xs font-semibold bg-red-500/20 border border-red-500/40 text-red-300";
                feedbackBox.innerText = "Respuesta incorrecta. Inténtalo de nuevo para avanzar.";
            }
        }

        function restartEdunautaGame() {
            currentGameStep = 0;
            gameScore = 0;
            document.getElementById("game-score-badge").innerText = `Puntos: 0 / 500`;
            document.getElementById("game-question-box").classList.remove("hidden");
            document.getElementById("game-complete-box").classList.add("hidden");

            for (let i = 1; i <= 3; i++) {
                const node = document.getElementById(`node-${i}`);
                if (node) {
                    node.className = "w-10 h-10 rounded-2xl bg-slate-800 text-slate-400 flex items-center justify-center font-bold text-xs border border-slate-700 transition-all";
                }
            }

            renderGameStep();
        }

        // --- EXISTING DASHBOARD & CHART LOGIC ---
        let currentDistrict = "DE1";
        let availableHoursTotal = 12;
        let decisionsCounter = { approved: 0, discarded: 0 };

        function renderDistrictData() {
            const tbody = document.getElementById("schools-tbody");
            const allocatorContainer = document.getElementById("allocator-controls");
            const currentSchools = schoolData[currentDistrict];

            tbody.innerHTML = "";
            allocatorContainer.innerHTML = "";

            let assignedSum = 0;

            currentSchools.forEach((school, index) => {
                assignedSum += school.hours;
                
                let adoptionBadge = school.adoption >= 60 
                    ? `<span class="bg-emerald-500/20 text-emerald-300 px-2 py-0.5 rounded text-[10px] font-bold">${school.adoption}% (Alto)</span>`
                    : school.adoption >= 35 
                    ? `<span class="bg-amber-500/20 text-amber-300 px-2 py-0.5 rounded text-[10px] font-bold">${school.adoption}% (Medio)</span>`
                    : `<span class="bg-red-500/20 text-red-300 px-2 py-0.5 rounded text-[10px] font-bold">${school.adoption}% (Crítico)</span>`;

                const tr = document.createElement("tr");
                tr.className = "hover:bg-slate-700/30 transition-colors";
                tr.innerHTML = `
                    <td class="py-3 font-medium text-slate-200">${school.name}</td>
                    <td class="py-3">${adoptionBadge}</td>
                    <td class="py-3 text-slate-300"><i class="fa-solid fa-book-open text-cyan-400 mr-1"></i> ${school.difficulty}</td>
                    <td class="py-3 text-right font-mono font-bold text-cyan-300" id="hours-display-${index}">${school.hours} hs</td>
                `;
                tbody.appendChild(tr);

                const ctrlDiv = document.createElement("div");
                ctrlDiv.className = "flex items-center justify-between bg-slate-900/60 p-2.5 rounded-xl border border-slate-700/60";
                ctrlDiv.innerHTML = `
                    <div class="w-1/2">
                        <span class="text-xs text-slate-300 font-medium block truncate">${school.name}</span>
                        <span class="text-[10px] text-slate-500">Adopción: ${school.adoption}%</span>
                    </div>
                    <div class="flex items-center space-x-3 w-1/2 justify-end">
                        <input type="range" min="0" max="10" value="${school.hours}" 
                            oninput="updateHours(${index}, this.value)"
                            class="w-24 accent-cyan-400 cursor-pointer">
                        <span class="font-mono text-xs font-bold text-cyan-300 w-8 text-right" id="slider-val-${index}">${school.hours}h</span>
                    </div>
                `;
                allocatorContainer.appendChild(ctrlDiv);
            });

            updateHoursCounter();
        }

        function updateHours(schoolIndex, val) {
            val = parseInt(val);
            schoolData[currentDistrict][schoolIndex].hours = val;
            document.getElementById(`slider-val-${schoolIndex}`).innerText = `${val}h`;
            document.getElementById(`hours-display-${schoolIndex}`).innerText = `${val} hs`;
            updateHoursCounter();
        }

        function updateHoursCounter() {
            const currentSchools = schoolData[currentDistrict];
            const used = currentSchools.reduce((acc, s) => acc + s.hours, 0);
            const remaining = Math.max(0, 20 - used);
            document.getElementById("hours-remaining").innerText = remaining;
        }

        function generateAIRecommendations() {
            const placeholder = document.getElementById("ai-placeholder");
            const results = document.getElementById("ai-results");
            const summaryBox = document.getElementById("ai-summary");
            const recsList = document.getElementById("ai-recommendations-list");

            placeholder.classList.add("hidden");
            results.classList.remove("hidden");

            const currentSchools = schoolData[currentDistrict];
            const criticalSchool = currentSchools.reduce((prev, curr) => (prev.adoption < curr.adoption) ? prev : curr);

            summaryBox.innerHTML = `
                <i class="fa-solid fa-sparkles text-purple-400 mr-1"></i>
                <strong>Diagnóstico IA para ${currentDistrict}:</strong> Se detecta una disparidad de adopción. La institución 
                <span class="underline font-bold text-white">${criticalSchool.name}</span> registra la menor tasa (${criticalSchool.adoption}%), requiriendo intervención prioritaria de facilitadores pedagógicos.
            `;

            recsList.innerHTML = `
                <div id="rec-card-1" class="p-3 bg-slate-900 border border-slate-700 rounded-xl space-y-2">
                    <div class="flex items-center justify-between">
                        <span class="font-bold text-slate-200">Recomendación 1: Asignación FPD</span>
                        <span class="text-[10px] bg-red-500/20 text-red-300 px-2 py-0.5 rounded">Prioridad Alta</span>
                    </div>
                    <p class="text-slate-400 text-[11px]">Asignar +3 hs/semana de acompañamiento técnico a <strong>${criticalSchool.name}</strong> para talleres de diseño de juegos.</p>
                    <div class="flex space-x-2 pt-1">
                        <button onclick="handleDecision(1, 'Aprobar', '${criticalSchool.name}: +3hs FPD')" class="bg-emerald-600 hover:bg-emerald-500 text-white px-2.5 py-1 rounded text-[10px] font-bold">Aceptar</button>
                        <button onclick="handleDecision(1, 'Descartar', '${criticalSchool.name}: +3hs FPD')" class="bg-slate-700 hover:bg-slate-600 text-slate-300 px-2.5 py-1 rounded text-[10px]">Descartar</button>
                    </div>
                </div>

                <div id="rec-card-2" class="p-3 bg-slate-900 border border-slate-700 rounded-xl space-y-2">
                    <div class="flex items-center justify-between">
                        <span class="font-bold text-slate-200">Recomendación 2: Refuerzo Curricular</span>
                        <span class="text-[10px] bg-amber-500/20 text-amber-300 px-2 py-0.5 rounded">Pedagógico</span>
                    </div>
                    <p class="text-slate-400 text-[11px]">Crear plantilla de mecánica "Investigación por Pistas" enfocada en <strong>${criticalSchool.difficulty}</strong>.</p>
                    <div class="flex space-x-2 pt-1">
                        <button onclick="handleDecision(2, 'Aprobar', 'Plantilla Curricular Específica')" class="bg-emerald-600 hover:bg-emerald-500 text-white px-2.5 py-1 rounded text-[10px] font-bold">Aceptar</button>
                        <button onclick="handleDecision(2, 'Descartar', 'Plantilla Curricular Específica')" class="bg-slate-700 hover:bg-slate-600 text-slate-300 px-2.5 py-1 rounded text-[10px]">Descartar</button>
                    </div>
                </div>
            `;
        }

        function handleDecision(cardId, action, detail) {
            const card = document.getElementById(`rec-card-${cardId}`);
            if (card) {
                card.style.opacity = "0.5";
                card.style.pointerEvents = "none";
            }

            if (action === 'Aprobar') decisionsCounter.approved++;
            if (action === 'Descartar') decisionsCounter.discarded++;

            document.getElementById("decisions-count").innerText = `${decisionsCounter.approved} aprobadas / ${decisionsCounter.discarded} descartadas`;

            const log = document.getElementById("decisions-log");
            const entry = document.createElement("div");
            entry.className = action === 'Aprobar' ? "text-emerald-400" : "text-red-400";
            entry.innerText = `[${new Date().toLocaleTimeString()}] ${action.toUpperCase()}: ${detail}`;
            log.prepend(entry);
        }

        function switchTechView(view) {
            const btnAsis = document.getElementById("tab-btn-asis");
            const btnTobe = document.getElementById("tab-btn-tobe");
            const viewAsis = document.getElementById("view-asis");
            const viewTobe = document.getElementById("view-tobe");

            if (view === 'asis') {
                btnAsis.className = "px-5 py-2.5 rounded-lg transition-all bg-white text-slate-900 shadow-sm font-bold";
                btnTobe.className = "px-5 py-2.5 rounded-lg transition-all text-slate-600 hover:text-slate-900 font-bold";
                viewAsis.classList.remove("hidden");
                viewTobe.classList.add("hidden");
            } else {
                btnTobe.className = "px-5 py-2.5 rounded-lg transition-all bg-slate-900 text-cyan-400 shadow-sm font-bold";
                btnAsis.className = "px-5 py-2.5 rounded-lg transition-all text-slate-600 hover:text-slate-900 font-bold";
                viewTobe.classList.remove("hidden");
                viewAsis.classList.add("hidden");
            }
        }

        document.getElementById("district-select").addEventListener("change", (e) => {
            currentDistrict = e.target.value;
            renderDistrictData();
            document.getElementById("ai-placeholder").classList.remove("hidden");
            document.getElementById("ai-results").classList.add("hidden");
        });

        window.addEventListener("load", () => {
            renderDistrictData();
            renderGameStep();

            const ctxHours = document.getElementById('chart-hours').getContext('2d');
            new Chart(ctxHours, {
                type: 'bar',
                data: {
                    labels: ['< 1h', '1 - 3h', '3 - 5h', '5 - 8h', '> 8h'],
                    datasets: [{
                        label: 'Secundario Estatal (%)',
                        data: [0, 9.1, 27.3, 45.4, 18.2],
                        backgroundColor: '#0284c7',
                        borderRadius: 8
                    }, {
                        label: 'Total Muestra (%)',
                        data: [5.0, 20.0, 30.0, 32.5, 12.5],
                        backgroundColor: '#94a3b8',
                        borderRadius: 8
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: { legend: { position: 'bottom', labels: { boxWidth: 12, font: { size: 10 } } } },
                    scales: { y: { beginAtZero: true, ticks: { font: { size: 10 } } }, x: { ticks: { font: { size: 10 } } } }
                }
            });

            const ctxCond = document.getElementById('chart-conditions').getContext('2d');
            new Chart(ctxCond, {
                type: 'doughnut',
                data: {
                    labels: ['Gratuita', 'Aprobación previa obligatoria', 'Sin datos de alumnos', 'Capacitación inicial'],
                    datasets: [{
                        data: [72.7, 72.7, 45.5, 36.4],
                        backgroundColor: ['#14b8a6', '#0284c7', '#8b5cf6', '#f59e0b']
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: { legend: { position: 'bottom', labels: { boxWidth: 10, font: { size: 10 } } } }
                }
            });
        });
    </script>
</body>
</html>
