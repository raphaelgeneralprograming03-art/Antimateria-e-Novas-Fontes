
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SISTEMA DE ENERGIA DE ANTIMATÉRIA - USINA QUANTUM MK-V</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Fonts Sci-Fi do Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Rajdhani:wght@500;600;700&family=Share+Tech+Mono&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-dark: #030611;
            --panel-bg: rgba(6, 12, 28, 0.82);
            --neon-magenta: #ff007f;
            --neon-fuchsia: #d946ef;
            --neon-cyan: #00f0ff;
            --neon-amber: #ffaa00;
            --neon-green: #00ff88;
            --neon-red: #ff2a2a;
            --glass-border: rgba(0, 240, 255, 0.22);
        }

        body {
            background-color: var(--bg-dark);
            color: #e2e8f0;
            font-family: 'Rajdhani', sans-serif;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 50% 30%, rgba(255, 0, 127, 0.05) 0%, transparent 70%),
                radial-gradient(circle at 80% 80%, rgba(0, 240, 255, 0.04) 0%, transparent 60%),
                linear-gradient(to bottom, rgba(3, 6, 17, 0.92), rgba(3, 6, 17, 0.98));
        }

        .font-orbitron { font-family: 'Orbitron', sans-serif; }
        .font-mono-tech { font-family: 'Share Tech Mono', monospace; }

        /* Estilo Painel Glassmorphism */
        .glass-panel {
            background: var(--panel-bg);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--glass-border);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.7), inset 0 0 15px rgba(255, 0, 127, 0.04);
            border-radius: 12px;
        }

        /* Efeitos Glow Neon */
        .glow-magenta { text-shadow: 0 0 10px rgba(255, 0, 127, 0.8); }
        .glow-cyan { text-shadow: 0 0 10px rgba(0, 240, 255, 0.8); }
        .glow-amber { text-shadow: 0 0 10px rgba(255, 170, 0, 0.8); }
        .glow-green { text-shadow: 0 0 10px rgba(0, 255, 136, 0.8); }
        .glow-red { text-shadow: 0 0 10px rgba(255, 42, 42, 0.9); }

        /* Custom Range Sliders */
        input[type=range] {
            -webkit-appearance: none;
            background: rgba(15, 23, 42, 0.85);
            border: 1px solid rgba(0, 240, 255, 0.3);
            height: 6px;
            border-radius: 3px;
            outline: none;
        }

        input[type=range]::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            background: var(--neon-cyan);
            cursor: pointer;
            box-shadow: 0 0 10px var(--neon-cyan);
            border: 2px solid #ffffff;
            transition: transform 0.15s ease, background 0.15s ease;
        }

        input[type=range].magenta-slider::-webkit-slider-thumb {
            background: var(--neon-magenta);
            box-shadow: 0 0 10px var(--neon-magenta);
        }

        input[type=range]::-webkit-slider-thumb:hover {
            transform: scale(1.25);
        }

        /* Botões Sci-Fi */
        .btn-sci-fi {
            position: relative;
            background: linear-gradient(135deg, rgba(0, 240, 255, 0.12) 0%, rgba(255, 0, 127, 0.15) 100%);
            border: 1px solid var(--neon-cyan);
            color: #ffffff;
            transition: all 0.2s ease;
            clip-path: polygon(10px 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%, 0 10px);
        }

        .btn-sci-fi:hover {
            background: linear-gradient(135deg, rgba(0, 240, 255, 0.3) 0%, rgba(255, 0, 127, 0.35) 100%);
            box-shadow: 0 0 18px rgba(0, 240, 255, 0.5);
            transform: translateY(-1px);
        }

        .btn-magenta {
            border-color: var(--neon-magenta);
            background: linear-gradient(135deg, rgba(255, 0, 127, 0.2) 0%, rgba(120, 0, 80, 0.3) 100%);
        }

        .btn-magenta:hover {
            background: linear-gradient(135deg, rgba(255, 0, 127, 0.45) 0%, rgba(180, 0, 100, 0.5) 100%);
            box-shadow: 0 0 20px rgba(255, 0, 127, 0.7);
        }

        .btn-danger {
            background: linear-gradient(135deg, rgba(255, 42, 42, 0.25) 0%, rgba(140, 0, 0, 0.4) 100%);
            border-color: var(--neon-red);
            color: #ffffff;
        }

        .btn-danger:hover {
            background: linear-gradient(135deg, rgba(255, 42, 42, 0.55) 0%, rgba(200, 0, 0, 0.6) 100%);
            box-shadow: 0 0 22px rgba(255, 42, 42, 0.8);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: rgba(3, 6, 17, 0.9); }
        ::-webkit-scrollbar-thumb { background: rgba(255, 0, 127, 0.4); border-radius: 3px; }
        ::-webkit-scrollbar-thumb:hover { background: var(--neon-magenta); }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between p-3 lg:p-5 text-sm select-none">

    <!-- CABEÇALHO DA INTERFACE -->
    <header class="glass-panel p-4 mb-4 flex flex-col md:flex-row justify-between items-center gap-4 relative overflow-hidden">
        <div class="absolute -top-10 -left-10 w-36 h-36 bg-fuchsia-600/10 rounded-full blur-3xl pointer-events-none"></div>
        <div class="flex items-center gap-3 z-10">
            <div class="w-11 h-11 rounded-lg bg-fuchsia-950/80 border border-fuchsia-500/50 flex items-center justify-center shadow-lg shadow-fuchsia-500/20">
                <svg class="w-7 h-7 text-fuchsia-400 animate-pulse" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <circle cx="12" cy="12" r="3" stroke-width="2"></circle>
                    <path stroke-linecap="round" stroke-dasharray="2 2" stroke-width="1.5" d="M12 2a10 10 0 1 0 10 10 A10 10 0 0 0 12 2 z"></path>
                    <path stroke-linecap="round" stroke-width="1.5" d="M4.93 4.93l14.14 14.14M4.93 19.07L19.07 4.93"></path>
                </svg>
            </div>
            <div>
                <h1 class="font-orbitron font-extrabold text-xl md:text-2xl tracking-wider text-white flex items-center gap-2">
                    REATOR DE ANTIMATÉRIA <span class="text-xs px-2.5 py-0.5 rounded bg-fuchsia-900/60 border border-fuchsia-400/50 text-fuchsia-300 font-mono-tech">SINCROTRON & CONVERSOR MHD</span>
                </h1>
                <p class="text-xs text-fuchsia-200/70 font-mono-tech">PRODUÇÃO RELATIVÍSTICA, ARMADILHA PENNING-MALMBERG E ANIQUILAÇÃO $E = \Delta m \cdot c^2$</p>
            </div>
        </div>

        <!-- BADGES DE STATUS -->
        <div class="flex items-center gap-3 z-10">
            <div id="statusBadge" class="flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-emerald-950/70 border border-emerald-500/50 text-emerald-400 font-orbitron text-xs tracking-wide shadow-md shadow-emerald-500/10">
                <span class="w-2.5 h-2.5 rounded-full bg-emerald-400 animate-ping"></span>
                <span id="statusText">CONFINAMENTO ESTÁVEL</span>
            </div>
            <div class="flex flex-col items-end px-3 py-1 rounded bg-slate-900/90 border border-fuchsia-500/30">
                <span class="text-[10px] text-fuchsia-400/80 uppercase tracking-widest font-mono-tech">Potência Líquida</span>
                <span id="netPowerHeader" class="font-orbitron font-bold text-lg text-fuchsia-300 glow-magenta">0.00 GW</span>
            </div>
        </div>
    </header>

    <!-- CONTAINER PRINCIPAL (GRID DASHBOARD) -->
    <main class="grid grid-cols-1 lg:grid-cols-12 gap-4 flex-1">

        <!-- COLUNA ESQUERDA: CANVAS HUD VISUALIZADOR (8 COLS) -->
        <section class="lg:col-span-8 flex flex-col gap-4">
            <!-- CANVAS CONTAINER -->
            <div class="glass-panel p-2 relative flex-1 min-h-[440px] lg:min-h-[540px] flex items-center justify-center overflow-hidden">
                <canvas id="simCanvas" class="w-full h-full block rounded-lg cursor-crosshair"></canvas>
                
                <!-- HUD OVERLAY NO CANVAS -->
                <div class="absolute top-4 left-4 pointer-events-none flex flex-col gap-1.5 text-xs font-mono-tech">
                    <div class="bg-slate-950/80 backdrop-blur-md border border-fuchsia-500/30 px-3 py-1 rounded text-fuchsia-300 flex items-center gap-2 shadow-lg">
                        <span class="w-2 h-2 rounded-full bg-fuchsia-400"></span>
                        ARMADILHA PENNING: <span id="hudPenningB" class="font-bold text-white">12.0 T</span>
                    </div>
                    <div class="bg-slate-950/80 backdrop-blur-md border border-cyan-500/30 px-3 py-1 rounded text-cyan-300 flex items-center gap-2 shadow-lg">
                        <span class="w-2 h-2 rounded-full bg-cyan-400"></span>
                        ACELERADOR SINCROTRON: <span id="hudAccelPower" class="font-bold text-white">45% (0.98c)</span>
                    </div>
                </div>

                <div class="absolute top-4 right-4 pointer-events-none flex flex-col gap-1.5 text-xs font-mono-tech items-end">
                    <div class="bg-slate-950/80 backdrop-blur-md border border-amber-500/30 px-3 py-1 rounded text-amber-300 shadow-lg">
                        EQUAÇÃO ANIQUILAÇÃO: <span class="text-white font-bold">p⁻ + p⁺ ➔ 2γ + π± (180 TJ/g)</span>
                    </div>
                </div>

                <!-- ALERTA DE VIOLAÇÃO DE CONFINAMENTO (OVERLAY RED BREACH) -->
                <div id="breachOverlay" class="absolute inset-0 bg-red-950/85 backdrop-blur-md flex flex-col items-center justify-center text-center p-6 gap-4 hidden z-20">
                    <div class="w-20 h-20 rounded-full bg-red-600/30 border-2 border-red-500 flex items-center justify-center animate-bounce shadow-2xl shadow-red-500/50">
                        <svg class="w-12 h-12 text-red-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path></svg>
                    </div>
                    <div>
                        <h2 class="font-orbitron font-extrabold text-3xl text-red-400 glow-red mb-2">ALERTA: CRITICAL CONTAINMENT BREACH!</h2>
                        <p class="text-sm text-red-200 max-w-lg">A nuvem de antimatéria colidiu com a parede do container devido à instabilidade do campo Penning ou superaquecimento da armadilha. Aniquilação não-controlada iminente!</p>
                    </div>
                    <button id="btnResetBreach" class="btn-sci-fi btn-danger px-8 py-3 rounded-lg font-orbitron font-bold tracking-wider text-sm flex items-center gap-2">
                        RECONSTRUIR CAMPO MAGNÉTICO E PURGAR
                    </button>
                </div>
            </div>

            <!-- LEGENDA VISUAL DO SISTEMA DE ANTIMATÉRIA -->
            <div class="glass-panel p-3 grid grid-cols-2 sm:grid-cols-4 gap-2 text-xs font-mono-tech">
                <div class="flex items-center gap-2 bg-slate-900/60 p-2 rounded border border-fuchsia-500/20">
                    <span class="w-3 h-3 rounded-full bg-fuchsia-500 shadow-sm shadow-fuchsia-500"></span>
                    <span class="text-slate-200">Antipróton / Pósitron</span>
                </div>
                <div class="flex items-center gap-2 bg-slate-900/60 p-2 rounded border border-cyan-500/20">
                    <span class="w-3 h-3 rounded-full bg-cyan-400 shadow-sm shadow-cyan-400"></span>
                    <span class="text-slate-200">Próton Relativístico</span>
                </div>
                <div class="flex items-center gap-2 bg-slate-900/60 p-2 rounded border border-amber-500/20">
                    <span class="w-3 h-3 rounded-full bg-amber-400 shadow-sm shadow-amber-400"></span>
                    <span class="text-slate-200">Raios Gama / Píons</span>
                </div>
                <div class="flex items-center gap-2 bg-slate-900/60 p-2 rounded border border-emerald-500/20">
                    <span class="w-3 h-3 rounded-full bg-emerald-400 shadow-sm shadow-emerald-400"></span>
                    <span class="text-slate-200">Pulso MHD Energético</span>
                </div>
            </div>
        </section>

        <!-- COLUNA DIREITA: PAINEL DE CONTROLE E TELEMETRIA (4 COLS) -->
        <section class="lg:col-span-4 flex flex-col gap-4">
            
            <!-- MÉTRICAS PRINCIPAIS EM TEMPO REAL -->
            <div class="glass-panel p-4 flex flex-col gap-3">
                <h2 class="font-orbitron font-bold text-sm text-fuchsia-400 tracking-wider flex items-center justify-between border-b border-fuchsia-500/20 pb-2">
                    TELEMETRIA DA ANTIMATÉRIA
                    <span class="text-[10px] text-slate-400 font-mono-tech">QUALIDADE VÁCUO: 10⁻¹⁴ Torr</span>
                </h2>

                <div class="grid grid-cols-2 gap-3">
                    <!-- Antimatéria Armazenada -->
                    <div class="bg-slate-950/70 p-2.5 rounded border border-slate-800">
                        <span class="text-[10px] text-slate-400 uppercase font-mono-tech block mb-1">Massa Armazenada</span>
                        <div class="flex items-baseline gap-1">
                            <span id="metricStoredMass" class="font-orbitron font-extrabold text-xl text-fuchsia-400 glow-magenta">12.4</span>
                            <span id="metricMassUnit" class="text-xs text-fuchsia-300 font-mono-tech">ng</span>
                        </div>
                    </div>

                    <!-- Potência Aniquilação (Bruta) -->
                    <div class="bg-slate-950/70 p-2.5 rounded border border-slate-800">
                        <span class="text-[10px] text-slate-400 uppercase font-mono-tech block mb-1">Potência Aniquilação</span>
                        <div class="flex items-baseline gap-1">
                            <span id="metricGrossPower" class="font-orbitron font-extrabold text-xl text-amber-400 glow-amber">1.80</span>
                            <span class="text-xs text-amber-300 font-mono-tech">TW</span>
                        </div>
                    </div>

                    <!-- Estabilidade da Armadilha -->
                    <div class="bg-slate-950/70 p-2.5 rounded border border-slate-800">
                        <span class="text-[10px] text-slate-400 uppercase font-mono-tech block mb-1">Estabilidade Penning</span>
                        <div class="flex items-baseline gap-1">
                            <span id="metricStability" class="font-orbitron font-bold text-base text-emerald-400">98.5</span>
                            <span class="text-xs text-emerald-300 font-mono-tech">%</span>
                        </div>
                    </div>

                    <!-- Eficiência Conversor MHD -->
                    <div class="bg-slate-950/70 p-2.5 rounded border border-slate-800">
                        <span class="text-[10px] text-slate-400 uppercase font-mono-tech block mb-1">Eficiência Captura MHD</span>
                        <div class="flex items-baseline gap-1">
                            <span id="metricMhdEff" class="font-orbitron font-bold text-base text-cyan-400">84.0</span>
                            <span class="text-xs text-cyan-300 font-mono-tech">%</span>
                        </div>
                    </div>
                </div>

                <!-- PAINEL DE EQUIVALÊNCIA ENERGÉTICA SEGUNDO E = mc^2 -->
                <div class="bg-slate-950/90 p-3 rounded border border-fuchsia-500/30 flex flex-col gap-1.5">
                    <div class="flex justify-between items-center text-xs font-mono-tech">
                        <span class="text-fuchsia-300">Aproveitamento Energético Relativístico</span>
                        <span id="energyEquivText" class="text-amber-400 font-bold">180 TJ / grama</span>
                    </div>
                    <div class="w-full bg-slate-900 h-2 rounded-full overflow-hidden border border-slate-800">
                        <div id="energyEquivBar" class="bg-gradient-to-r from-fuchsia-500 via-amber-400 to-cyan-400 h-full transition-all duration-300" style="width: 45%;"></div>
                    </div>
                    <p id="equivDescription" class="text-[10px] text-slate-300 font-mono-tech">Capaz de propelir 12 naves estelares ou abastecer metrópoles globais.</p>
                </div>
            </div>

            <!-- PAINEL DE CONTROLE DE PARÂMETROS (SLIDERS) -->
            <div class="glass-panel p-4 flex flex-col gap-3.5">
                <h2 class="font-orbitron font-bold text-sm text-fuchsia-400 tracking-wider border-b border-fuchsia-500/20 pb-2">
                    CONTROLES DE OPERAÇÃO
                </h2>

                <!-- Slider 1: Potência do Sincrotron -->
                <div class="flex flex-col gap-1">
                    <div class="flex justify-between text-xs font-mono-tech">
                        <label for="inputAccelPower" class="text-slate-300">Acelerador Sincrotron (Produção)</label>
                        <span id="valAccelPower" class="text-cyan-400 font-bold">45%</span>
                    </div>
                    <input type="range" id="inputAccelPower" min="0" max="100" value="45" step="1">
                </div>

                <!-- Slider 2: Campo Magnético da Armadilha Penning -->
                <div class="flex flex-col gap-1">
                    <div class="flex justify-between text-xs font-mono-tech">
                        <label for="inputPenningB" class="text-slate-300">Campo Magnético Penning (Confinamento)</label>
                        <span id="valPenningB" class="text-fuchsia-400 font-bold">12.0 Tesla</span>
                    </div>
                    <input type="range" id="inputPenningB" class="magenta-slider" min="2.0" max="25.0" value="12.0" step="0.5">
                </div>

                <!-- Slider 3: Taxa de Injeção para Aniquilação -->
                <div class="flex flex-col gap-1">
                    <div class="flex justify-between text-xs font-mono-tech">
                        <label for="inputAnnihilRate" class="text-slate-300">Injeção de Aniquilação Matéria-Antimatéria</label>
                        <span id="valAnnihilRate" class="text-amber-400 font-bold">10 ng/s</span>
                    </div>
                    <input type="range" id="inputAnnihilRate" min="0" max="100" value="10" step="1">
                </div>

                <!-- Slider 4: Resfriamento a Laser da Nuvem -->
                <div class="flex flex-col gap-1">
                    <div class="flex justify-between text-xs font-mono-tech">
                        <label for="inputLaserCooling" class="text-slate-300">Resfriamento Laser da Nuvem (Doppler)</label>
                        <span id="valLaserCooling" class="text-emerald-400 font-bold">80%</span>
                    </div>
                    <input type="range" id="inputLaserCooling" min="10" max="100" value="80" step="1">
                </div>

                <!-- BOTÕES DE AÇÃO RÁPIDA -->
                <div class="grid grid-cols-2 gap-2 mt-1">
                    <button id="btnPulseInjection" class="btn-sci-fi btn-magenta py-2.5 rounded font-orbitron font-bold text-xs tracking-wider flex items-center justify-center gap-1.5">
                        <svg class="w-4 h-4 text-fuchsia-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
                        INJETAR PULSO
                    </button>
                    <button id="btnPurgeTrap" class="btn-sci-fi btn-danger py-2.5 rounded font-orbitron font-bold text-xs tracking-wider flex items-center justify-center gap-1.5">
                        <svg class="w-4 h-4 text-red-300" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16"></path></svg>
                        PURGA MAGNÉTICA
                    </button>
                </div>
            </div>

            <!-- PRESETS DE CONFIGURAÇÃO -->
            <div class="glass-panel p-4 flex flex-col gap-2">
                <h2 class="font-orbitron font-bold text-xs text-slate-400 uppercase tracking-wider mb-1">
                    MODOS DE OPERAÇÃO PRÉ-DEFINIDOS
                </h2>
                <div class="grid grid-cols-2 gap-2 font-orbitron text-[11px]">
                    <button id="presetStandby" class="btn-sci-fi py-2 px-2 rounded text-slate-200">
                        1. ACUMULAÇÃO DE ESTOQUE
                    </button>
                    <button id="presetStandardPower" class="btn-sci-fi py-2 px-2 rounded text-amber-300">
                        2. GERADORES REDE (10 TW)
                    </button>
                    <button id="presetSpaceLaunch" class="btn-sci-fi py-2 px-2 rounded text-fuchsia-300 border-fuchsia-400/80">
                        3. IMPULSO ESPACIAL (50 TW)
                    </button>
                    <button id="presetOverloadTest" class="btn-sci-fi py-2 px-2 rounded text-rose-400 border-rose-500/50">
                        4. TESTE MÁXIMO ESTRESSE
                    </button>
                </div>
            </div>

        </section>
    </main>

    <!-- RODAPÉ DA REDE DE DISTRIBUIÇÃO GLOBAL E PROPULSÃO -->
    <footer class="glass-panel p-3 mt-4 flex flex-col sm:flex-row items-center justify-between gap-3 font-mono-tech text-xs">
        <div class="flex items-center gap-3">
            <div class="w-8 h-8 rounded bg-fuchsia-950 border border-fuchsia-500/40 flex items-center justify-center">
                <svg class="w-5 h-5 text-fuchsia-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
            </div>
            <div>
                <span class="text-slate-400 uppercase block text-[10px]">Distribuição Planetária de Energia Quantum</span>
                <span id="gridEquivVal" class="font-orbitron font-bold text-sm text-fuchsia-300 glow-magenta">0 Megacidades Alimentadas</span>
            </div>
        </div>

        <!-- BARRA DE VÁCUO DA ARMADILHA PENNING -->
        <div class="flex-1 max-w-md w-full bg-slate-950/80 p-2 rounded border border-slate-800 flex items-center gap-2">
            <span class="text-[10px] text-slate-400 shrink-0">TEMPERATURA NUVEM ANTIMATÉRIA</span>
            <div class="flex-1 h-2 bg-slate-900 rounded-full overflow-hidden border border-slate-800 relative">
                <div id="trapTempBar" class="h-full bg-gradient-to-r from-cyan-400 via-fuchsia-500 to-red-500 transition-all duration-300" style="width: 15%;"></div>
            </div>
            <span id="trapTempText" class="text-[11px] font-bold text-cyan-300 shrink-0">0.4 Kelvin</span>
        </div>

        <div class="text-slate-500 text-[11px] text-right">
            SIMULAÇÃO ANTIMATERIA v5.0<br>
            <span class="text-fuchsia-400/80">LABORATÓRIO DE ENERGIA RELATIVÍSTICA</span>
        </div>
    </footer>

    <script>
        /* MOTOR PRINCIPAL DA SIMULAÇÃO DE ANTIMATÉRIA E CONVERSÃO MHD */
        (function() {
            // Referências DOM
            const canvas = document.getElementById('simCanvas');
            const ctx = canvas.getContext('2d');

            // Sliders UI
            const inputAccelPower = document.getElementById('inputAccelPower');
            const inputPenningB = document.getElementById('inputPenningB');
            const inputAnnihilRate = document.getElementById('inputAnnihilRate');
            const inputLaserCooling = document.getElementById('inputLaserCooling');

            const valAccelPower = document.getElementById('valAccelPower');
            const valPenningB = document.getElementById('valPenningB');
            const valAnnihilRate = document.getElementById('valAnnihilRate');
            const valLaserCooling = document.getElementById('valLaserCooling');

            // Metrics Telemetry DOM
            const metricStoredMass = document.getElementById('metricStoredMass');
            const metricMassUnit = document.getElementById('metricMassUnit');
            const metricGrossPower = document.getElementById('metricGrossPower');
            const metricStability = document.getElementById('metricStability');
            const metricMhdEff = document.getElementById('metricMhdEff');
            const netPowerHeader = document.getElementById('netPowerHeader');
            const energyEquivBar = document.getElementById('energyEquivBar');
            const energyEquivText = document.getElementById('energyEquivText');
            const equivDescription = document.getElementById('equivDescription');
            const statusBadge = document.getElementById('statusBadge');
            const statusText = document.getElementById('statusText');
            const hudPenningB = document.getElementById('hudPenningB');
            const hudAccelPower = document.getElementById('hudAccelPower');
            const gridEquivVal = document.getElementById('gridEquivVal');
            const trapTempBar = document.getElementById('trapTempBar');
            const trapTempText = document.getElementById('trapTempText');
            const breachOverlay = document.getElementById('breachOverlay');

            // Action Buttons DOM
            const btnPulseInjection = document.getElementById('btnPulseInjection');
            const btnPurgeTrap = document.getElementById('btnPurgeTrap');
            const btnResetBreach = document.getElementById('btnResetBreach');
            const presetStandby = document.getElementById('presetStandby');
            const presetStandardPower = document.getElementById('presetStandardPower');
            const presetSpaceLaunch = document.getElementById('presetSpaceLaunch');
            const presetOverloadTest = document.getElementById('presetOverloadTest');

            // ESTADO DE SIMULAÇÃO FÍSICA
            const simState = {
                // Parâmetros Ajustáveis do Usuário
                accelPowerPct: 45,        // 0 a 100%
                penningBFieldTesla: 12.0, // 2.0 a 25.0 Tesla
                annihilationRateNgSec: 10,// 0 a 100 ng/s
                laserCoolingPct: 80,      // 10 a 100%

                // Parâmetros Físicos Calculados
                storedAntimatterNg: 12.4, // Nanogramas de antiprótons/pósitrons
                maxStorageCapacityNg: 200.0,
                trapTempKelvin: 0.4,
                grossPowerTW: 0.0,
                mhdEfficiencyPct: 84.0,
                netPowerTW: 0.0,
                stabilityPct: 98.5,
                isBreached: false,

                // Lista de Partículas para renderização gráfica
                synchrotronParticles: [],
                antimatterCloudParticles: [],
                matterParticles: [],
                annihilationPhotons: [],
                mhdPulseRings: [],
                energyArcs: [],
                time: 0
            };

            // Responsive Canvas Resolution Scaling
            function resizeCanvas() {
                const rect = canvas.getBoundingClientRect();
                canvas.width = rect.width * window.devicePixelRatio;
                canvas.height = rect.height * window.devicePixelRatio;
                ctx.scale(window.devicePixelRatio, window.devicePixelRatio);
            }
            window.addEventListener('resize', resizeCanvas);
            resizeCanvas();

            // CLASSE: Partículas do Sincrotron (Acelerador Relativístico)
            class SynchrotronParticle {
                constructor(angle, direction) {
                    this.angle = angle;
                    this.direction = direction; // 1 = horário (prótons), -1 = anti-horário
                    this.speed = 0.03 + Math.random() * 0.02;
                }

                update(powerRatio) {
                    this.angle += this.direction * this.speed * (0.2 + powerRatio * 1.8);
                    if (this.angle > Math.PI * 2) this.angle -= Math.PI * 2;
                    if (this.angle < 0) this.angle += Math.PI * 2;
                }
            }

            // CLASSE: Partículas de Antimatéria Retidas na Armadilha Penning
            class AntimatterParticle {
                constructor() {
                    this.reset();
                }

                reset() {
                    this.r = Math.random() * 28;
                    this.theta = Math.random() * Math.PI * 2;
                    this.z = (Math.random() - 0.5) * 45;
                    this.speedTheta = (0.02 + Math.random() * 0.04);
                    this.speedZ = (Math.random() - 0.5) * 1.5;
                }

                update(tempKelvin, stabilityRatio) {
                    // Movimento de Precessão Magnetron & Ação Axial Penning
                    const jitter = (tempKelvin / 10.0) + (1.0 - stabilityRatio) * 3.0;
                    this.theta += this.speedTheta;
                    this.z += Math.sin(simState.time * 2 + this.r) * 0.8 + (Math.random() - 0.5) * jitter;
                    
                    // Oscilação harmônica central do poço potencial
                    if (Math.abs(this.z) > 35) this.z *= -0.9;
                    if (this.r > 40) this.r *= 0.95;
                }
            }

            // CLASSE: Partículas de Aniquilação (Fótons de Raios Gama e Píons)
            class AnnihilationPhoton {
                constructor(x, y) {
                    this.x = x;
                    this.y = y;
                    const angle = Math.random() * Math.PI * 2;
                    const speed = 3 + Math.random() * 5;
                    this.vx = Math.cos(angle) * speed;
                    this.vy = Math.sin(angle) * speed;
                    this.life = 1.0;
                    this.decay = 0.02 + Math.random() * 0.03;
                    this.color = Math.random() < 0.5 ? '#ff007f' : (Math.random() < 0.5 ? '#ffaa00' : '#ffffff');
                }

                update() {
                    this.x += this.vx;
                    this.y += this.vy;
                    this.life -= this.decay;
                }
            }

            // CLASSE: Anéis de Pulso Eletromagnético Capturados pelo MHD
            class MHDRing {
                constructor(x, y) {
                    this.x = x;
                    this.y = y;
                    this.radius = 5;
                    this.maxRadius = 110 + Math.random() * 30;
                    this.alpha = 1.0;
                }

                update() {
                    this.radius += 3.5;
                    this.alpha = 1.0 - (this.radius / this.maxRadius);
                }
            }

            // Inicializar partículas estáticas e dinâmicas
            function initParticles() {
                simState.synchrotronParticles = [];
                for (let i = 0; i < 24; i++) {
                    simState.synchrotronParticles.push(new SynchrotronParticle((i / 24) * Math.PI * 2, 1));
                    simState.synchrotronParticles.push(new SynchrotronParticle((i / 24) * Math.PI * 2, -1));
                }

                simState.antimatterCloudParticles = [];
                for (let i = 0; i < 80; i++) {
                    simState.antimatterCloudParticles.push(new AntimatterParticle());
                }
            }
            initParticles();

            // CÁLCULO DAS EQUAÇÕES DE FÍSICA QUANTUM RELATIVÍSTICA
            function updatePhysics() {
                if (simState.isBreached) return;

                // 1. Taxa de Produção de Antimatéria pelo Sincrotron (E = mc^2)
                const accelRatio = simState.accelPowerPct / 100.0;
                const productionRateNgSec = Math.pow(accelRatio, 2.2) * 2.5; // Até 2.5 ng/s no máximo
                simState.storedAntimatterNg += productionRateNgSec * 0.016; // Incrementar no estoque

                // 2. Taxa de Aniquilação em Massa (Injeção Doser)
                const actualInjectionNgSec = Math.min(simState.storedAntimatterNg * 5.0, simState.annihilationRateNgSec);
                simState.storedAntimatterNg -= actualInjectionNgSec * 0.016;
                if (simState.storedAntimatterNg < 0) simState.storedAntimatterNg = 0;

                // 3. Conversão E = delta_m * c^2: 1 ng aniquilado com 1 ng de matéria -> 180 MJ = 0.18 TW-s por ng
                // Potência Bruta Liberada em Terawatts (TW)
                simState.grossPowerTW = actualInjectionNgSec * 0.18;

                // 4. Temperatura do Vácuo na Armadilha Penning (Kelvin)
                // Aquecimento por densidade + agitação vs Resfriamento Laser Doppler
                const particleAgitation = (simState.storedAntimatterNg / 30.0) * (1.0 + simState.grossPowerTW * 0.1);
                const coolingPower = (simState.laserCoolingPct / 100.0) * 4.0;
                simState.trapTempKelvin = Math.max(0.05, 0.2 + particleAgitation - coolingPower * 0.25);

                // 5. Estabilidade do Campo Magnético Penning
                // Estabilidade depende do equilíbrio de pressão magnética B^2 / (2µ0) e temperatura da nuvem
                const requiredB = (simState.storedAntimatterNg / 15.0) + (simState.trapTempKelvin * 1.2);
                const currentB = simState.penningBFieldTesla;

                let stabilityDelta = 0;
                if (currentB < requiredB) {
                    stabilityDelta = -(requiredB - currentB) * 2.5;
                } else {
                    stabilityDelta = (100.0 - simState.stabilityPct) * 0.05;
                }

                // Desestabilização por excesso de estresse se a taxa de aniquilação for extrema
                if (simState.annihilationRateNgSec > 85) stabilityDelta -= 0.8;

                simState.stabilityPct += stabilityDelta;
                simState.stabilityPct = Math.max(0.0, Math.min(100.0, simState.stabilityPct));

                // 6. Eficiência da Captura Magnetohidrodinâmica (MHD)
                // A eficiência cresce com o campo magnético Penning até o limite térmico de 92%
                simState.mhdEfficiencyPct = Math.min(92.0, 50.0 + (simState.penningBFieldTesla / 25.0) * 40.0);

                // 7. Potência Líquida Gerada
                const electricalPowerTW = simState.grossPowerTW * (simState.mhdEfficiencyPct / 100.0);
                const consumedPowerTW = (Math.pow(accelRatio, 2) * 0.8) + (Math.pow(currentB / 25.0, 1.5) * 0.3) + ((simState.laserCoolingPct / 100.0) * 0.1);
                simState.netPowerTW = electricalPowerTW - consumedPowerTW;

                // Teste de Violação de Confinamento (Breach Trigger)
                if ((simState.stabilityPct <= 0 || simState.storedAntimatterNg >= simState.maxStorageCapacityNg) && !simState.isBreached) {
                    triggerBreach();
                }

                // Gerar Partículas de Aniquilação se houver reação ativa
                if (actualInjectionNgSec > 0.5) {
                    const rect = canvas.getBoundingClientRect();
                    const cx = rect.width / 2;
                    const cy = rect.height * 0.58;

                    for (let p = 0; p < Math.floor(actualInjectionNgSec / 10) + 2; p++) {
                        simState.annihilationPhotons.push(new AnnihilationPhoton(cx, cy));
                    }

                    if (Math.random() < 0.4) {
                        simState.mhdPulseRings.push(new MHDRing(cx, cy));
                    }
                }
            }

            function triggerBreach() {
                simState.isBreached = true;
                simState.storedAntimatterNg = 0;
                simState.grossPowerTW = 0;
                simState.netPowerTW = -0.5;
                breachOverlay.classList.remove('hidden');
            }

            // RENDERIZAÇÃO GRÁFICA NO CANVAS 2D
            function renderCanvas() {
                const width = canvas.width / window.devicePixelRatio;
                const height = canvas.height / window.devicePixelRatio;

                // Fundo com leve rastro de luz para movimento fluído
                ctx.fillStyle = 'rgba(3, 6, 17, 0.35)';
                ctx.fillRect(0, 0, width, height);

                const cx = width / 2;
                const cy = height / 2;

                simState.time += 0.02;

                // 1. DESENHAR ACELERADOR SINCROTRON CIRCULAR (PARTE SUPERIOR)
                const syncCx = cx;
                const syncCy = height * 0.24;
                const syncRadius = Math.min(width, height) * 0.20;

                ctx.save();
                // Tubo de Vácuo do Sincrotron
                ctx.beginPath();
                ctx.arc(syncCx, syncCy, syncRadius, 0, Math.PI * 2);
                ctx.strokeStyle = 'rgba(0, 240, 255, 0.25)';
                ctx.lineWidth = 14;
                ctx.stroke();

                ctx.strokeStyle = 'rgba(255, 0, 127, 0.15)';
                ctx.lineWidth = 4;
                ctx.stroke();

                // Imãs Deflectores Relativísticos
                const magnetCount = 12;
                for (let i = 0; i < magnetCount; i++) {
                    const angle = (i / magnetCount) * Math.PI * 2;
                    const mx = syncCx + Math.cos(angle) * syncRadius;
                    const my = syncCy + Math.sin(angle) * syncRadius;

                    ctx.fillStyle = '#06152d';
                    ctx.strokeStyle = 'rgba(0, 240, 255, 0.6)';
                    ctx.lineWidth = 1.5;
                    ctx.beginPath();
                    ctx.arc(mx, my, 6, 0, Math.PI * 2);
                    ctx.fill();
                    ctx.stroke();
                }

                // Renderizar Feixes de Prótons Relativísticos Colidindo
                const accelRatio = simState.accelPowerPct / 100.0;
                simState.synchrotronParticles.forEach(p => {
                    p.update(accelRatio);
                    const px = syncCx + Math.cos(p.angle) * syncRadius;
                    const py = syncCy + Math.sin(p.angle) * syncRadius;

                    ctx.beginPath();
                    ctx.arc(px, py, p.direction === 1 ? 3 : 2.5, 0, Math.PI * 2);
                    ctx.fillStyle = p.direction === 1 ? '#00f0ff' : '#d946ef';
                    ctx.shadowColor = p.direction === 1 ? '#00f0ff' : '#d946ef';
                    ctx.shadowBlur = 8;
                    ctx.fill();
                });

                // Ponto de Colisão com Injeção de Antimatéria para a Armadilha
                const colX = syncCx;
                const colY = syncCy + syncRadius;
                ctx.beginPath();
                ctx.arc(colX, colY, 5 + accelRatio * 6, 0, Math.PI * 2);
                ctx.fillStyle = '#ffffff';
                ctx.shadowColor = '#ff007f';
                ctx.shadowBlur = 15;
                ctx.fill();

                // Canal de Alimentação do Sincrotron para a Armadilha Penning
                const trapCy = height * 0.55;
                ctx.beginPath();
                ctx.moveTo(colX, colY);
                ctx.lineTo(cx, trapCy - 50);
                ctx.strokeStyle = `rgba(255, 0, 127, ${0.2 + accelRatio * 0.6})`;
                ctx.setLineDash([4, 6]);
                ctx.lineWidth = 2;
                ctx.stroke();
                ctx.setLineDash([]);
                ctx.restore();

                // 2. ARMADILHA DE CONFINAMENTO PENNING-MALMBERG (CENTRO)
                ctx.save();
                ctx.translate(cx, trapCy);

                const trapWidth = 90;
                const trapHeight = 110;

                // Container da Armadilha
                ctx.beginPath();
                ctx.roundRect(-trapWidth / 2, -trapHeight / 2, trapWidth, trapHeight, 12);
                ctx.fillStyle = 'rgba(6, 14, 30, 0.85)';
                ctx.fill();
                ctx.strokeStyle = `rgba(0, 240, 255, ${0.3 + (simState.penningBFieldTesla / 25.0) * 0.5})`;
                ctx.lineWidth = 2.5;
                ctx.stroke();

                // Bobinas Magnéticas de RF (Anéis Horizontais)
                for (let b = -40; b <= 40; b += 20) {
                    ctx.beginPath();
                    ctx.ellipse(0, b, trapWidth * 0.45, 8, 0, 0, Math.PI * 2);
                    ctx.strokeStyle = 'rgba(255, 0, 127, 0.6)';
                    ctx.shadowColor = '#ff007f';
                    ctx.shadowBlur = simState.penningBFieldTesla * 0.8;
                    ctx.lineWidth = 2;
                    ctx.stroke();
                }

                // Feixes do Resfriamento Laser Doppler (Linhas Diagonais Azuis)
                if (simState.laserCoolingPct > 10) {
                    ctx.save();
                    ctx.strokeStyle = `rgba(0, 240, 255, ${(simState.laserCoolingPct / 100) * 0.4})`;
                    ctx.lineWidth = 1.5;
                    ctx.beginPath();
                    ctx.moveTo(-trapWidth / 2, -trapHeight / 2); ctx.lineTo(trapWidth / 2, trapHeight / 2);
                    ctx.moveTo(trapWidth / 2, -trapHeight / 2); ctx.lineTo(-trapWidth / 2, trapHeight / 2);
                    ctx.stroke();
                    ctx.restore();
                }

                // Nuvem Vibrante de Antimatéria Retida (Pósitrons e Antiprótons)
                if (!simState.isBreached && simState.storedAntimatterNg > 0) {
                    const stabilityRatio = simState.stabilityPct / 100.0;
                    simState.antimatterCloudParticles.forEach(p => {
                        p.update(simState.trapTempKelvin, stabilityRatio);

                        const px = Math.cos(p.theta) * p.r;
                        const py = p.z;

                        ctx.beginPath();
                        ctx.arc(px, py, 2.2, 0, Math.PI * 2);
                        ctx.fillStyle = '#ff007f';
                        ctx.shadowColor = '#ff007f';
                        ctx.shadowBlur = 10;
                        ctx.fill();
                    });

                    // Brilho Incandescente da Nuvem Central
                    const cloudGlow = Math.min(1.0, simState.storedAntimatterNg / 50.0);
                    const cloudGrad = ctx.createRadialGradient(0, 0, 2, 0, 0, 35);
                    cloudGrad.addColorStop(0, `rgba(255, 255, 255, ${cloudGlow * 0.9})`);
                    cloudGrad.addColorStop(0.4, `rgba(255, 0, 127, ${cloudGlow * 0.7})`);
                    cloudGrad.addColorStop(1, 'transparent');

                    ctx.beginPath();
                    ctx.ellipse(0, 0, 32, 42, 0, 0, Math.PI * 2);
                    ctx.fillStyle = cloudGrad;
                    ctx.fill();
                }
                ctx.restore();

                // 3. CÂMARA DE ANIQUILAÇÃO CONTROLADA & CONVERÇÃO MHD (INFERIOR)
                const mhdCy = height * 0.80;

                ctx.save();
                // Canal de Alimentação Inferior da Antimatéria
                ctx.beginPath();
                ctx.moveTo(cx, trapCy + trapHeight / 2);
                ctx.lineTo(cx, mhdCy);
                ctx.strokeStyle = 'rgba(255, 170, 0, 0.5)';
                ctx.lineWidth = 3;
                ctx.stroke();

                // Anéis Conversores Magnetohidrodinâmicos (MHD)
                for (let r = 25; r <= 85; r += 20) {
                    ctx.beginPath();
                    ctx.arc(cx, mhdCy, r, 0, Math.PI * 2);
                    ctx.strokeStyle = `rgba(0, 255, 136, ${0.15 + (simState.grossPowerTW / 10.0) * 0.4})`;
                    ctx.lineWidth = 3;
                    ctx.stroke();
                }

                // Núcleo Focal de Aniquilação
                if (simState.grossPowerTW > 0) {
                    const flashSize = 10 + Math.min(40, simState.grossPowerTW * 5);
                    ctx.beginPath();
                    ctx.arc(cx, mhdCy, flashSize, 0, Math.PI * 2);
                    const coreGrad = ctx.createRadialGradient(cx, mhdCy, 2, cx, mhdCy, flashSize);
                    coreGrad.addColorStop(0, '#ffffff');
                    coreGrad.addColorStop(0.3, '#ffaa00');
                    coreGrad.addColorStop(0.7, '#ff007f');
                    coreGrad.addColorStop(1, 'transparent');
                    ctx.fillStyle = coreGrad;
                    ctx.shadowColor = '#ffaa00';
                    ctx.shadowBlur = 30;
                    ctx.fill();
                }
                ctx.restore();

                // Renderizar Partículas de Explosão Fotônica (Raios Gama)
                for (let i = simState.annihilationPhotons.length - 1; i >= 0; i--) {
                    const p = simState.annihilationPhotons[i];
                    p.update();

                    ctx.save();
                    ctx.beginPath();
                    ctx.arc(p.x, p.y, 2, 0, Math.PI * 2);
                    ctx.fillStyle = p.color;
                    ctx.shadowColor = p.color;
                    ctx.shadowBlur = 6;
                    ctx.globalAlpha = p.life;
                    ctx.fill();
                    ctx.restore();

                    if (p.life <= 0) simState.annihilationPhotons.splice(i, 1);
                }

                // Renderizar Anéis de Ondas Eletromagnéticas MHD
                for (let i = simState.mhdPulseRings.length - 1; i >= 0; i--) {
                    const ring = simState.mhdPulseRings[i];
                    ring.update();

                    ctx.save();
                    ctx.beginPath();
                    ctx.arc(ring.x, ring.y, ring.radius, 0, Math.PI * 2);
                    ctx.strokeStyle = '#00ff88';
                    ctx.shadowColor = '#00ff88';
                    ctx.shadowBlur = 12;
                    ctx.lineWidth = 2;
                    ctx.globalAlpha = Math.max(0, ring.alpha);
                    ctx.stroke();
                    ctx.restore();

                    if (ring.alpha <= 0) simState.mhdPulseRings.splice(i, 1);
                }

                // 4. ARCOS ELÉTRICOS DE TRANSMISSÃO PARA A REDE GLOBAL
                if (simState.netPowerTW > 0) {
                    ctx.save();
                    ctx.strokeStyle = '#00f0ff';
                    ctx.shadowColor = '#00f0ff';
                    ctx.shadowBlur = 10;
                    ctx.lineWidth = 1.5;

                    const nodes = [
                        { x: width * 0.1, y: height * 0.85 },
                        { x: width * 0.9, y: height * 0.85 },
                        { x: width * 0.15, y: height * 0.5 },
                        { x: width * 0.85, y: height * 0.5 }
                    ];

                    nodes.forEach(node => {
                        ctx.beginPath();
                        ctx.moveTo(cx, mhdCy);
                        
                        // Desenhar raio plasma em ziguezague
                        let currX = cx;
                        let currY = mhdCy;
                        const steps = 6;
                        for (let s = 1; s <= steps; s++) {
                            const targetX = cx + (node.x - cx) * (s / steps);
                            const targetY = mhdCy + (node.y - mhdCy) * (s / steps);
                            const jitterX = (Math.random() - 0.5) * 16;
                            const jitterY = (Math.random() - 0.5) * 16;
                            ctx.lineTo(targetX + jitterX, targetY + jitterY);
                        }
                        ctx.stroke();
                    });
                    ctx.restore();
                }
            }

            // ATUALIZAÇÃO DA INTERFACE DE USUÁRIO (TELEMETRIA E GRÁFICOS)
            function updateUI() {
                // Formatação da Massa Armazenada
                if (simState.storedAntimatterNg >= 1000) {
                    metricStoredMass.innerText = (simState.storedAntimatterNg / 1000).toFixed(2);
                    metricMassUnit.innerText = 'µg';
                } else {
                    metricStoredMass.innerText = simState.storedAntimatterNg.toFixed(1);
                    metricMassUnit.innerText = 'ng';
                }

                // Potência Bruta e Eficiência
                metricGrossPower.innerText = simState.grossPowerTW.toFixed(2);
                metricMhdEff.innerText = simState.mhdEfficiencyPct.toFixed(1);
                metricStability.innerText = simState.stabilityPct.toFixed(1);

                // Cabeçalho Potência Líquida
                if (Math.abs(simState.netPowerTW) >= 1.0) {
                    netPowerHeader.innerText = `${simState.netPowerTW.toFixed(2)} TW`;
                } else {
                    netPowerHeader.innerText = `${(simState.netPowerTW * 1000).toFixed(0)} GW`;
                }

                // Estilização do Indicador de Estabilidade
                if (simState.stabilityPct < 35) {
                    metricStability.className = 'font-orbitron font-bold text-base text-rose-500 animate-pulse';
                } else if (simState.stabilityPct < 75) {
                    metricStability.className = 'font-orbitron font-bold text-base text-amber-400';
                } else {
                    metricStability.className = 'font-orbitron font-bold text-base text-emerald-400';
                }

                // Barra e Descrição de Equivalência Energética
                const equivPct = Math.min(100, (simState.grossPowerTW / 20.0) * 100);
                energyEquivBar.style.width = `${equivPct}%`;

                if (simState.grossPowerTW > 15.0) {
                    energyEquivText.innerText = 'PROPULSÃO ESPACIAL PROFUNDA';
                    equivDescription.innerText = 'Energia suficiente para dobra espacial e lançamento de frota estelar.';
                } else if (simState.grossPowerTW > 2.0) {
                    energyEquivText.innerText = 'REDE PLANETÁRIA CONTINENTAL';
                    equivDescription.innerText = 'Abastece múltiplos continentes sem qualquer emissão de carbono.';
                } else {
                    energyEquivText.innerText = 'ACUMULAÇÃO DE ESTOQUE';
                    equivDescription.innerText = 'Modo de segurança e recarga dos estoques da armadilha Penning.';
                }

                // Status Badge Geral
                if (simState.isBreached) {
                    statusBadge.className = 'flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-red-950/80 border border-red-500/50 text-red-400 font-orbitron text-xs';
                    statusText.innerText = 'CONTAINMENT BREACH!';
                } else if (simState.grossPowerTW > 10.0) {
                    statusBadge.className = 'flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-fuchsia-950/80 border border-fuchsia-400/60 text-fuchsia-300 font-orbitron text-xs glow-magenta';
                    statusText.innerText = 'ANIQUILAÇÃO EM ALTA POTÊNCIA';
                } else if (simState.grossPowerTW > 0.5) {
                    statusBadge.className = 'flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-amber-950/80 border border-amber-500/50 text-amber-300 font-orbitron text-xs';
                    statusText.innerText = 'GERAÇÃO MHD ATIVA';
                } else {
                    statusBadge.className = 'flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-emerald-950/70 border border-emerald-500/50 text-emerald-400 font-orbitron text-xs';
                    statusText.innerText = 'CONFINAMENTO ESTÁVEL';
                }

                // HUD Canvas
                hudPenningB.innerText = `${simState.penningBFieldTesla.toFixed(1)} T`;
                hudAccelPower.innerText = `${simState.accelPowerPct}% (${(0.9 + (simState.accelPowerPct / 100) * 0.099).toFixed(3)}c)`;

                // Rede Elétrica e Temperatura da Armadilha
                if (simState.netPowerTW > 0) {
                    const megaCities = Math.floor(simState.netPowerTW * 50); // ~20GW por megacidade
                    gridEquivVal.innerText = `${megaCities.toLocaleString('pt-BR')} Megacidades Alimentadas`;
                    gridEquivVal.className = 'font-orbitron font-bold text-sm text-fuchsia-300 glow-magenta';
                } else {
                    gridEquivVal.innerText = '0 Megacidades (Consumo Interno do Acelerador)';
                    gridEquivVal.className = 'font-orbitron font-bold text-sm text-rose-400';
                }

                const tempBarPct = Math.min(100, (simState.trapTempKelvin / 5.0) * 100);
                trapTempBar.style.width = `${tempBarPct}%`;
                trapTempText.innerText = `${simState.trapTempKelvin.toFixed(2)} Kelvin`;
            }

            // EVENT LISTENERS & CONTROLES DOS SLIDERS
            inputAccelPower.addEventListener('input', (e) => {
                simState.accelPowerPct = parseInt(e.target.value);
                valAccelPower.innerText = `${simState.accelPowerPct}%`;
            });

            inputPenningB.addEventListener('input', (e) => {
                simState.penningBFieldTesla = parseFloat(e.target.value);
                valPenningB.innerText = `${simState.penningBFieldTesla.toFixed(1)} Tesla`;
            });

            inputAnnihilRate.addEventListener('input', (e) => {
                simState.annihilationRateNgSec = parseInt(e.target.value);
                valAnnihilRate.innerText = `${simState.annihilationRateNgSec} ng/s`;
            });

            inputLaserCooling.addEventListener('input', (e) => {
                simState.laserCoolingPct = parseInt(e.target.value);
                valLaserCooling.innerText = `${simState.laserCoolingPct}%`;
            });

            // Pulso Instantâneo de Injeção
            btnPulseInjection.addEventListener('click', () => {
                if (simState.isBreached) return;
                simState.annihilationRateNgSec = 100;
                inputAnnihilRate.value = 100;
                valAnnihilRate.innerText = '100 ng/s';
                setTimeout(() => {
                    simState.annihilationRateNgSec = 15;
                    inputAnnihilRate.value = 15;
                    valAnnihilRate.innerText = '15 ng/s';
                }, 1500);
            });

            // Purga Magnética de Emergência (Descarte seguro)
            btnPurgeTrap.addEventListener('click', () => {
                simState.storedAntimatterNg = 0;
                simState.annihilationRateNgSec = 0;
                inputAnnihilRate.value = 0;
                valAnnihilRate.innerText = '0 ng/s';
                simState.stabilityPct = 100.0;
                simState.isBreached = false;
                breachOverlay.classList.add('hidden');
            });

            // Reiniciar Pós-Breach
            btnResetBreach.addEventListener('click', () => {
                simState.isBreached = false;
                simState.stabilityPct = 100.0;
                simState.penningBFieldTesla = 18.0;
                inputPenningB.value = 18.0;
                valPenningB.innerText = '18.0 Tesla';
                simState.storedAntimatterNg = 5.0;
                breachOverlay.classList.add('hidden');
            });

            // MODOS DE OPERAÇÃO PRÉ-DEFINIDOS
            function applyPreset(accel, b, inject, cooling) {
                if (simState.isBreached) {
                    simState.isBreached = false;
                    breachOverlay.classList.add('hidden');
                }
                simState.accelPowerPct = accel;
                inputAccelPower.value = accel;
                valAccelPower.innerText = `${accel}%`;

                simState.penningBFieldTesla = b;
                inputPenningB.value = b;
                valPenningB.innerText = `${b.toFixed(1)} Tesla`;

                simState.annihilationRateNgSec = inject;
                inputAnnihilRate.value = inject;
                valAnnihilRate.innerText = `${inject} ng/s`;

                simState.laserCoolingPct = cooling;
                inputLaserCooling.value = cooling;
                valLaserCooling.innerText = `${cooling}%`;

                simState.stabilityPct = 100.0;
            }

            presetStandby.addEventListener('click', () => applyPreset(80, 15.0, 0, 90));
            presetStandardPower.addEventListener('click', () => applyPreset(30, 12.0, 20, 80));
            presetSpaceLaunch.addEventListener('click', () => applyPreset(10, 22.0, 75, 95));
            presetOverloadTest.addEventListener('click', () => applyPreset(100, 4.0, 95, 20));

            // LOOP DE ANIMAÇÃO A 60 FPS
            function loop() {
                updatePhysics();
                renderCanvas();
                updateUI();
                requestAnimationFrame(loop);
            }

            // Inicialização ao carregar a página
            window.onload = function() {
                loop();
            };
        })();
    </script>
</body>
</html>
