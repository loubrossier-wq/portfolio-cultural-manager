<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio | Chargée de Projets Culturels</title>
    <!-- Bibliothèques UI -->
    <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Icônes Lucide -->
    <script src="https://unpkg.com/lucide@0.344.0/dist/umd/lucide.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Archivo+Black&family=Space+Mono:wght@400;700&display=swap');
        
        body { font-family: 'Space Mono', monospace; }
        h1, h2, h3 { font-family: 'Archivo Black', sans-serif; }

        @keyframes marquee {
          0% { transform: translateX(0%); }
          100% { transform: translateX(-100%); }
        }
        .animate-marquee {
          animation: marquee 30s linear infinite;
        }
        @keyframes dash {
          to { stroke-dashoffset: 0; }
        }
        .animate-dash {
          stroke-dasharray: 1000;
          stroke-dashoffset: 1000;
          animation: dash 8s linear infinite;
        }
    </style>
</head>
<body class="bg-neutral-900">
    <div id="root"></div>

    <script type="text/babel">
        const { useState } = React;

        // Extraction sécurisée des icônes Lucide pour le format UMD
        const Music = (props) => <i data-lucide="music" {...props}></i>;
        const Film = (props) => <i data-lucide="film" {...props}></i>;
        const Layers = (props) => <i data-lucide="layers" {...props}></i>;
        const Menu = (props) => <i data-lucide="menu" {...props}></i>;
        const MoveRight = (props) => <i data-lucide="move-right" {...props}></i>;
        const Mail = (props) => <i data-lucide="mail" {...props}></i>;
        const Linkedin = (props) => <i data-lucide="linkedin" {...props}></i>;

        const App = () => {
            const countries = ["GUATEMALA", "ÉTHIOPIE", "SOUDAN", "KENYA", "DJIBOUTI"];

            // Initialisation des icônes après le rendu
            React.useEffect(() => {
                if (window.lucide) {
                    window.lucide.createIcons();
                }
            }, []);
            
            return (
                <div className="flex flex-col min-h-screen bg-[#1a1a1a] selection:bg-[#FFD700] selection:text-black">
                    
                    {/* LE CONTENEUR PRINCIPAL */}
                    <div className="w-full max-w-6xl mx-auto my-0 md:my-12 bg-white text-black border-4 border-black shadow-[20px_20px_0px_0px_rgba(255,215,0,1)] overflow-hidden relative">
                        
                        {/* NAVIGATION */}
                        <nav className="border-b-4 border-black p-6 flex justify-between items-center bg-[#FFD700] sticky top-0 z-50">
                            <span className="font-black text-xl md:text-2xl tracking-tighter uppercase">Portfolio_Culturel</span>
                            <div className="flex gap-4 items-center">
                                <div className="hidden md:flex gap-4 mr-6 text-[10px] font-bold uppercase">
                                    <a href="#" className="hover:underline">Projets</a>
                                    <a href="#" className="hover:underline">Expérience</a>
                                    <a href="#" className="hover:underline">Contact</a>
                                </div>
                                <div className="w-10 h-10 bg-black text-white flex items-center justify-center cursor-pointer hover:rotate-90 transition-transform">
                                    <Menu />
                                </div>
                            </div>
                        </nav>

                        {/* HERO SECTION */}
                        <div className="p-8 md:p-16 border-b-4 border-black grid grid-cols-1 md:grid-cols-2 gap-12 items-center bg-[url('https://www.transparenttextures.com/patterns/asfalt-dark.png')]">
                            <div className="z-10">
                                <div className="inline-block bg-[#FFD700] text-black font-black px-3 py-1 text-xs mb-6 border-2 border-black shadow-[4px_4px_0px_0px_rgba(0,0,0,1)]">
                                    STRATÉGIE & COORDINATION
                                </div>
                                <h1 className="text-5xl md:text-8xl font-black leading-[0.85] mb-8 tracking-tighter uppercase">
                                    300<br/><span className="text-[#FFD700] bg-black px-2">EVENTS</span><br/>CULTURELS
                                </h1>
                                <div className="space-y-4 max-w-md">
                                    <p className="text-lg font-bold leading-tight">
                                        "Ingénierie de projets artistiques pour le réseau des Alliances et Instituts Français."
                                    </p>
                                    <div className="flex flex-wrap gap-2 pt-4">
                                        {countries.map(c => (
                                            <span key={c} className="text-[10px] bg-gray-100 border-2 border-black px-2 py-1 uppercase font-black hover:bg-black hover:text-white transition-colors">
                                                {c}
                                            </span>
                                        ))}
                                    </div>
                                </div>
                            </div>
                            
                            {/* ÉLÉMENT VISUEL */}
                            <div className="relative group flex justify-center">
                                <div className="w-full max-w-[400px] aspect-square border-4 border-black bg-[#FFD700] flex items-center justify-center relative overflow-hidden transition-transform duration-500 group-hover:scale-[1.02]">
                                    <div className="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/cubes.png')] opacity-20"></div>
                                    <span className="z-10 font-black text-[10rem] md:text-[14rem] text-black/15 select-none leading-none">5Y</span>
                                    
                                    <svg className="absolute inset-0 w-full h-full pointer-events-none z-20">
                                        <path d="M 10% 10% Q 50% 50% 90% 90%" stroke="black" strokeWidth="2" fill="none" strokeDasharray="8,8" className="animate-dash" />
                                    </svg>

                                    <div className="absolute top-8 right-4 bg-white p-3 border-2 border-black text-[10px] font-black shadow-[6px_6px_0px_0px_rgba(0,0,0,1)] group-hover:-translate-y-1 transition-transform">
                                        RÉSEAU IF / AF
                                    </div>
                                </div>
                            </div>
                        </div>

                        {/* SECTION DISCIPLINES */}
                        <div className="grid grid-cols-1 md:grid-cols-3">
                            <div className="p-10 border-r-0 md:border-r-4 border-b-4 md:border-b-0 border-black bg-black text-white group cursor-pointer relative overflow-hidden">
                                <div className="relative z-10">
                                    <div className="mb-6 text-[#FFD700]"><Music size={40} /></div>
                                    <h3 className="font-black text-3xl uppercase mb-4 tracking-tighter">Musique</h3>
                                    <p className="text-sm font-bold opacity-70 leading-relaxed mb-6">FESTIVAL JAZZ À ADDIS : Coordination de 4 scènes, 20 artistes internationaux.</p>
                                    <div className="flex items-center gap-2 font-black text-xs uppercase underline decoration-2 underline-offset-4">
                                        DÉTAILS PROJET <MoveRight />
                                    </div>
                                </div>
                            </div>
                            
                            <div className="p-10 border-r-0 md:border-r-4 border-b-4 md:border-b-0 border-black bg-white text-black group cursor-pointer relative overflow-hidden">
                                <div className="relative z-10">
                                    <div className="mb-6"><Film size={40} /></div>
                                    <h3 className="font-black text-3xl uppercase mb-4 tracking-tighter">Cinéma</h3>
                                    <p className="text-sm font-bold opacity-70 leading-relaxed mb-6">MOIS DU DOCUMENTAIRE : Programmation itinérante au Soudan.</p>
                                    <div className="flex items-center gap-2 font-black text-xs uppercase underline decoration-2 underline-offset-4">
                                        DÉTAILS PROJET <MoveRight />
                                    </div>
                                </div>
                            </div>

                            <div className="p-10 border-black bg-[#FFD700] text-black group cursor-pointer relative overflow-hidden">
                                <div className="relative z-10">
                                    <div className="mb-6"><Layers size={40} /></div>
                                    <h3 className="font-black text-3xl uppercase mb-4 tracking-tighter">Hybride</h3>
                                    <p className="text-sm font-bold opacity-80 leading-relaxed mb-6">BIENNALE D'ART : Exposition transmédia et artisanat local.</p>
                                    <div className="flex items-center gap-2 font-black text-xs uppercase underline decoration-2 underline-offset-4">
                                        DÉTAILS PROJET <MoveRight />
                                    </div>
                                </div>
                            </div>
                        </div>

                        {/* INDEX DES PROJETS */}
                        <div className="p-8 md:p-12 border-t-4 border-black bg-gray-50">
                            <h2 className="text-2xl font-black mb-8 uppercase flex items-center gap-3">
                                <span className="w-4 h-4 bg-black inline-block"></span>
                                Index des Projets (30)
                            </h2>
                            <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-x-12 gap-y-2">
                                {Array.from({length: 30}).map((_, i) => (
                                    <div key={i} className="group flex justify-between items-center border-b border-black/10 py-2 hover:bg-black hover:text-[#FFD700] px-2 transition-colors cursor-default">
                                        <span className="text-[10px] font-bold">#{100+i}</span>
                                        <span className="text-xs font-black uppercase flex-grow px-4">Event_{countries[i%5]}</span>
                                        <span className="text-[10px] opacity-40 group-hover:opacity-100">2019-24</span>
                                    </div>
                                ))}
                            </div>
                        </div>

                        {/* FOOTER */}
                        <div className="p-12 bg-black text-white flex flex-col md:flex-row justify-between items-center gap-8">
                            <div>
                                <h3 className="text-3xl font-black uppercase mb-2 leading-none">Prête pour le<br/>défi culturel.</h3>
                                <p className="opacity-50 text-[10px] uppercase font-bold mt-4">Basée entre Paris et l'international</p>
                            </div>
                            <div className="flex gap-4">
                                <a href="#" className="w-12 h-12 bg-[#FFD700] text-black flex items-center justify-center border-2 border-white hover:-translate-y-2 transition-transform">
                                    <Mail />
                                </a>
                                <a href="#" className="w-12 h-12 bg-white text-black flex items-center justify-center border-2 border-white hover:-translate-y-2 transition-transform">
                                    <Linkedin />
                                </a>
                            </div>
                        </div>
                    </div>

                    {/* MARQUEE */}
                    <div className="fixed bottom-0 left-0 w-full bg-[#FFD700] border-t-4 border-black py-2 z-50 overflow-hidden whitespace-nowrap">
                        <div className="animate-marquee inline-block font-black uppercase text-sm">
                            COORDONNATRICE DE PROJETS • 300 ÉVÉNEMENTS • AFRIQUE • AMÉRIQUE LATINE • INSTITUT FRANÇAIS • ALLIANCE FRANÇAISE • MUSIQUE • ARTS VISUELS • CINÉMA • LITTÉRATURE • DANSE • THÉÂTRE • 
                        </div>
                    </div>
                </div>
            );
        };

        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<App />);
    </script>
</body>
</html>
