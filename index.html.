<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cartão de Visita Digital</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Inter & Outfit -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Outfit:wght@400;600;700&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: 'var(--brand-color, #6366f1)',
                        'brand-hover': 'var(--brand-hover-color, #4f46e5)',
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Outfit', 'sans-serif'],
                    },
                    animation: {
                        'pulse-slow': 'pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                        'float': 'float 6s ease-in-out infinite',
                    },
                    keyframes: {
                        float: {
                            '0%, 100%': { transform: 'translateY(0px)' },
                            '50%': { transform: 'translateY(-10px)' },
                        }
                    }
                }
            }
        }
    </script>

    <style>
        :root {
            --brand-color: #6366f1;
            --brand-hover-color: #4f46e5;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: #0f172a;
            color: #f8fafc;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
        }

        .glass-card {
            background: rgba(30, 41, 59, 0.7);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5);
        }

        .glass-input {
            background: rgba(15, 23, 42, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.1);
            color: #f8fafc;
        }

        .glass-input:focus {
            border-color: var(--brand-color);
            outline: none;
            box-shadow: 0 0 0 2px rgba(99, 102, 241, 0.25);
        }

        .custom-scrollbar::-webkit-scrollbar {
            width: 6px;
        }

        .custom-scrollbar::-webkit-scrollbar-track {
            background: rgba(15, 23, 42, 0.5);
        }

        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: rgba(255, 255, 255, 0.2);
            border-radius: 3px;
        }

        .custom-scrollbar::-webkit-scrollbar-thumb:hover {
            background: rgba(255, 255, 255, 0.3);
        }
    </style>
</head>
<body class="relative flex items-center justify-center min-h-screen p-3 md:p-6 bg-slate-950 selection:bg-indigo-500 selection:text-white">

    <!-- Ambient Glowing Background Orbs -->
    <div class="fixed top-1/4 left-1/2 -translate-x-1/2 -translate-y-1/2 w-80 h-80 md:w-96 md:h-96 bg-indigo-600/20 rounded-full blur-3xl pointer-events-none animation-float"></div>
    <div class="fixed bottom-1/4 left-1/3 w-64 h-64 bg-purple-600/15 rounded-full blur-3xl pointer-events-none"></div>

    <!-- MAIN CARD CONTAINER -->
    <main class="w-full max-w-md mx-auto my-auto relative z-10">

        <!-- Business Card Card -->
        <div id="cardView" class="glass-card rounded-3xl overflow-hidden relative transition-all duration-300">

            <!-- Card Header / Banner -->
            <div id="cardHeader" class="h-32 md:h-36 w-full relative bg-gradient-to-r from-indigo-600 via-purple-600 to-pink-600">
                <div class="absolute inset-0 bg-black/20"></div>
                <!-- Subtle Admin Trigger Button (Hidden in plain sight, protected by PIN) -->
                <button id="openAuthBtn" title="Painel de Edição" class="absolute top-4 right-4 text-white/70 hover:text-white bg-black/30 hover:bg-black/50 p-2.5 rounded-full backdrop-blur-md transition-all duration-200">
                    <i class="fa-solid fa-gear text-sm"></i>
                </button>
            </div>

            <!-- Profile Content -->
            <div class="px-6 pb-8 relative text-center">

                <!-- Profile Avatar -->
                <div class="relative -mt-16 mb-4 inline-block">
                    <img id="displayAvatar" src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&q=80&w=400" alt="Foto de Perfil" class="w-28 h-28 md:w-32 md:h-32 rounded-full object-cover border-4 border-slate-900 shadow-2xl mx-auto bg-slate-800">
                    <div id="onlineBadge" class="absolute bottom-2 right-2 w-4 h-4 bg-emerald-500 border-2 border-slate-900 rounded-full"></div>
                </div>

                <!-- Identity Information -->
                <h1 id="displayName" class="font-display text-2xl md:text-3xl font-bold text-white tracking-tight">Ana Silva</h1>
                <p id="displayTitle" class="text-indigo-400 font-medium text-sm md:text-base mt-0.5">Designer UX/UI & Desenvolvedora</p>
                <p id="displayBio" class="text-slate-300 text-xs md:text-sm mt-3 line-clamp-3 leading-relaxed px-2">Criando experiências digitais incríveis e interfaces intuitivas para produtos do futuro.</p>

                <!-- Primary Call To Action Buttons -->
                <div class="grid grid-cols-2 gap-3 mt-6">
                    <button id="saveVCardBtn" class="flex items-center justify-center gap-2 bg-brand hover:bg-brand-hover text-white font-semibold py-3 px-4 rounded-xl shadow-lg transition-all transform active:scale-95 text-sm">
                        <i class="fa-solid fa-user-plus"></i>
                        <span>Salvar Contato</span>
                    </button>
                    <button id="shareCardBtn" class="flex items-center justify-center gap-2 bg-slate-800 hover:bg-slate-700 text-white font-semibold py-3 px-4 rounded-xl border border-white/10 shadow-lg transition-all transform active:scale-95 text-sm">
                        <i class="fa-solid fa-share-nodes"></i>
                        <span>Compartilhar</span>
                    </button>
                </div>

                <!-- Quick Contact Direct Links -->
                <div class="flex justify-center items-center gap-3 mt-5">
                    <a id="btnCall" href="tel:+5511999999999" class="w-11 h-11 rounded-xl bg-slate-800/80 hover:bg-brand/20 hover:text-indigo-400 border border-white/10 flex items-center justify-center text-slate-300 transition-all">
                        <i class="fa-solid fa-phone"></i>
                    </a>
                    <a id="btnWhatsapp" href="https://wa.me/5511999999999" target="_blank" class="w-11 h-11 rounded-xl bg-slate-800/80 hover:bg-emerald-500/20 hover:text-emerald-400 border border-white/10 flex items-center justify-center text-slate-300 transition-all">
                        <i class="fa-brands fa-whatsapp text-lg"></i>
                    </a>
                    <a id="btnEmail" href="mailto:ana.silva@exemplo.com" class="w-11 h-11 rounded-xl bg-slate-800/80 hover:bg-blue-500/20 hover:text-blue-400 border border-white/10 flex items-center justify-center text-slate-300 transition-all">
                        <i class="fa-solid fa-envelope"></i>
                    </a>
                    <a id="btnWebsite" href="https://exemplo.com" target="_blank" class="w-11 h-11 rounded-xl bg-slate-800/80 hover:bg-purple-500/20 hover:text-purple-400 border border-white/10 flex items-center justify-center text-slate-300 transition-all">
                        <i class="fa-solid fa-globe"></i>
                    </a>
                </div>

                <hr class="border-white/10 my-6">

                <!-- Social Media & Links Grid -->
                <div class="space-y-2.5" id="socialLinksContainer">
                    <!-- Links populated dynamically -->
                </div>

            </div>

            <!-- Footer NFC info -->
            <div class="bg-slate-900/80 px-6 py-3 border-t border-white/5 text-center flex items-center justify-between text-xs text-slate-400">
                <span class="flex items-center gap-1.5"><i class="fa-solid fa-wifi text-indigo-400"></i> NFC Toque Ativo</span>
                <span>Cartão Digital &copy; 2026</span>
            </div>
        </div>

    </main>

    <!-- AUTHENTICATION MODAL (PIN ACCESS) -->
    <div id="authModal" class="fixed inset-0 z-50 bg-black/80 backdrop-blur-md flex items-center justify-center p-4 hidden">
        <div class="glass-card w-full max-w-sm rounded-2xl p-6 relative">
            <button id="closeAuthBtn" class="absolute top-4 right-4 text-slate-400 hover:text-white">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            <div class="text-center mb-6">
                <div class="w-12 h-12 bg-indigo-600/20 text-indigo-400 rounded-full flex items-center justify-center mx-auto mb-3 text-xl border border-indigo-500/30">
                    <i class="fa-solid fa-lock"></i>
                </div>
                <h2 class="text-xl font-bold text-white">Área de Edição</h2>
                <p class="text-xs text-slate-400 mt-1">Digite a senha/PIN para editar seus dados</p>
            </div>
            <form id="authForm" class="space-y-4">
                <div>
                    <input type="password" id="pinInput" placeholder="Senha (Padrão: 1234)" class="w-full glass-input rounded-xl px-4 py-3 text-center text-lg tracking-widest focus:ring-2 focus:ring-indigo-500" required>
                </div>
                <p id="authError" class="text-rose-400 text-xs text-center hidden">PIN incorreto. Tente novamente.</p>
                <button type="submit" class="w-full bg-brand hover:bg-brand-hover text-white font-semibold py-3 rounded-xl transition-all">
                    Acessar
                </button>
            </form>
        </div>
    </div>

    <!-- ADMIN EDIT MODAL / DRAWER -->
    <div id="adminDrawer" class="fixed inset-0 z-50 bg-slate-950/90 backdrop-blur-lg overflow-y-auto hidden custom-scrollbar">
        <div class="min-h-screen max-w-2xl mx-auto p-4 md:p-8">
            
            <!-- Admin Top Bar -->
            <div class="flex items-center justify-between pb-6 border-b border-white/10 mb-6 sticky top-0 bg-slate-950/80 backdrop-blur-md z-10 py-2">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 bg-brand/20 text-brand rounded-xl flex items-center justify-center">
                        <i class="fa-solid fa-pen-to-square"></i>
                    </div>
                    <div>
                        <h2 class="text-lg font-bold text-white">Painel do Cartão</h2>
                        <p class="text-xs text-slate-400">Modo de Edição Ativo</p>
                    </div>
                </div>
                <div class="flex items-center gap-2">
                    <button id="closeAdminBtn" class="bg-slate-800 hover:bg-slate-700 text-slate-300 hover:text-white px-4 py-2 rounded-xl text-sm transition-all">
                        Sair sem Salvar
                    </button>
                    <button id="saveAdminBtn" class="bg-brand hover:bg-brand-hover text-white px-5 py-2 rounded-xl text-sm font-semibold transition-all shadow-lg">
                        Salvar
                    </button>
                </div>
            </div>

            <!-- Form Content -->
            <form id="editForm" class="space-y-6 pb-12">

                <!-- Profile Info Section -->
                <div class="glass-card p-5 rounded-2xl space-y-4">
                    <h3 class="text-sm font-semibold text-indigo-400 uppercase tracking-wider flex items-center gap-2">
                        <i class="fa-solid fa-user"></i> Informações Pessoais
                    </h3>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-medium text-slate-300 mb-1">Nome Completo</label>
                            <input type="text" id="editName" class="w-full glass-input rounded-xl px-3 py-2 text-sm">
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-slate-300 mb-1">Cargo / Profissão</label>
                            <input type="text" id="editTitle" class="w-full glass-input rounded-xl px-3 py-2 text-sm">
                        </div>
                    </div>

                    <div>
                        <label class="block text-xs font-medium text-slate-300 mb-1">Biografia Curta</label>
                        <textarea id="editBio" rows="3" class="w-full glass-input rounded-xl px-3 py-2 text-sm custom-scrollbar"></textarea>
                    </div>

                    <!-- Profile Photo Selection -->
                    <div>
                        <label class="block text-xs font-medium text-slate-300 mb-1">Foto de Perfil (URL ou Arquivo)</label>
                        <div class="flex gap-2">
                            <input type="text" id="editAvatarUrl" placeholder="https://..." class="w-full glass-input rounded-xl px-3 py-2 text-sm">
                            <label class="bg-slate-800 hover:bg-slate-700 text-slate-300 border border-white/10 px-4 py-2 rounded-xl text-xs font-medium flex items-center cursor-pointer shrink-0">
                                <i class="fa-solid fa-upload mr-1.5"></i> Arquivo
                                <input type="file" id="editAvatarFile" accept="image/*" class="hidden">
                            </label>
                        </div>
                    </div>
                </div>

                <!-- Contact Direct Buttons Section -->
                <div class="glass-card p-5 rounded-2xl space-y-4">
                    <h3 class="text-sm font-semibold text-indigo-400 uppercase tracking-wider flex items-center gap-2">
                        <i class="fa-solid fa-address-book"></i> Contatos Diretos
                    </h3>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-medium text-slate-300 mb-1">Telefone (Chamadas)</label>
                            <input type="text" id="editPhone" placeholder="+5511999999999" class="w-full glass-input rounded-xl px-3 py-2 text-sm">
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-slate-300 mb-1">WhatsApp (número com DDD)</label>
                            <input type="text" id="editWhatsapp" placeholder="5511999999999" class="w-full glass-input rounded-xl px-3 py-2 text-sm">
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-slate-300 mb-1">E-mail</label>
                            <input type="email" id="editEmail" class="w-full glass-input rounded-xl px-3 py-2 text-sm">
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-slate-300 mb-1">Website Oficial</label>
                            <input type="url" id="editWebsite" placeholder="https://..." class="w-full glass-input rounded-xl px-3 py-2 text-sm">
                        </div>
                    </div>
                </div>

                <!-- Social Media Links Builder -->
                <div class="glass-card p-5 rounded-2xl space-y-4">
                    <div class="flex items-center justify-between">
                        <h3 class="text-sm font-semibold text-indigo-400 uppercase tracking-wider flex items-center gap-2">
                            <i class="fa-solid fa-hashtag"></i> Redes Sociais & Links
                        </h3>
                        <button type="button" id="addSocialBtn" class="text-xs bg-indigo-600/30 hover:bg-indigo-600/50 text-indigo-300 border border-indigo-500/30 px-3 py-1.5 rounded-lg transition-all flex items-center gap-1">
                            <i class="fa-solid fa-plus"></i> Adicionar
                        </button>
                    </div>

                    <div id="socialInputsList" class="space-y-3">
                        <!-- Dynamic social inputs rendered here -->
                    </div>
                </div>

                <!-- Security & Customization -->
                <div class="glass-card p-5 rounded-2xl space-y-4">
                    <h3 class="text-sm font-semibold text-indigo-400 uppercase tracking-wider flex items-center gap-2">
                        <i class="fa-solid fa-shield-halved"></i> Aparência & Segurança
                    </h3>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-medium text-slate-300 mb-1">Cor Principal de Destaque</label>
                            <div class="flex items-center gap-3">
                                <input type="color" id="editBrandColor" class="w-10 h-10 rounded-lg bg-transparent cursor-pointer border-0">
                                <span id="colorHexText" class="text-xs text-slate-400 font-mono">#6366f1</span>
                            </div>
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-slate-300 mb-1">Alterar PIN de Edição</label>
                            <input type="password" id="editPin" placeholder="Nova Senha PIN" class="w-full glass-input rounded-xl px-3 py-2 text-sm">
                        </div>
                    </div>
                </div>

            </form>
        </div>
    </div>

    <!-- TOAST NOTIFICATION -->
    <div id="toast" class="fixed bottom-6 left-1/2 -translate-x-1/2 bg-slate-900/90 border border-white/20 text-white text-xs px-5 py-3 rounded-full shadow-2xl backdrop-blur-md opacity-0 pointer-events-none transition-all duration-300 flex items-center gap-2 z-50">
        <i id="toastIcon" class="fa-solid fa-circle-check text-emerald-400"></i>
        <span id="toastMessage">Ação realizada com sucesso!</span>
    </div>

    <!-- JAVASCRIPT APP LOGIC -->
    <script>
        // Default initial profile state
        const DEFAULT_DATA = {
            pin: '1234',
            name: 'Ana Silva',
            title: 'Designer UX/UI & Desenvolvedora',
            bio: 'Criando experiências digitais incríveis e interfaces intuitivas para produtos do futuro.',
            avatar: 'https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&q=80&w=400',
            phone: '+5511999999999',
            whatsapp: '5511999999999',
            email: 'ana.silva@exemplo.com',
            website: 'https://exemplo.com',
            brandColor: '#6366f1',
            socials: [
                { platform: 'instagram', label: 'Instagram', url: 'https://instagram.com', icon: 'fa-brands fa-instagram' },
                { platform: 'linkedin', label: 'LinkedIn', url: 'https://linkedin.com', icon: 'fa-brands fa-linkedin-in' },
                { platform: 'github', label: 'GitHub', url: 'https://github.com', icon: 'fa-brands fa-github' },
                { platform: 'spotify', label: 'Soundcloud / Playlist', url: 'https://soundcloud.com', icon: 'fa-brands fa-soundcloud' }
            ]
        };

        // State Management
        let appData = { ...DEFAULT_DATA };

        // DOM Elements
        const authModal = document.getElementById('authModal');
        const adminDrawer = document.getElementById('adminDrawer');
        const openAuthBtn = document.getElementById('openAuthBtn');
        const closeAuthBtn = document.getElementById('closeAuthBtn');
        const closeAdminBtn = document.getElementById('closeAdminBtn');
        const saveAdminBtn = document.getElementById('saveAdminBtn');
        const authForm = document.getElementById('authForm');
        const pinInput = document.getElementById('pinInput');
        const authError = document.getElementById('authError');

        // Initialize App
        function initApp() {
            loadStoredData();
            renderCardView();
            setupEventListeners();
        }

        // Load data from localStorage
        function loadStoredData() {
            const stored = localStorage.getItem('nfc_card_data');
            if (stored) {
                try {
                    appData = { ...DEFAULT_DATA, ...JSON.parse(stored) };
                } catch (e) {
                    console.error("Erro ao carregar dados do LocalStorage", e);
                }
            }
        }

        // Save data to localStorage
        function saveData() {
            localStorage.setItem('nfc_card_data', JSON.stringify(appData));
            renderCardView();
            showToast('Dados salvos com sucesso!');
        }

        // Apply Theme Color dynamically
        function applyBrandColor(color) {
            document.documentElement.style.setProperty('--brand-color', color);
            // Calculate hover color (slightly darker)
            document.documentElement.style.setProperty('--brand-hover-color', adjustColor(color, -20));
        }

        // Helper to darken hex color for hover effect
        function adjustColor(col, amt) {
            let usePound = false;
            if (col[0] == "#") {
                col = col.slice(1);
                usePound = true;
            }
            let num = parseInt(col, 16);
            let r = (num >> 16) + amt;
            if (r > 255) r = 255; else if (r < 0) r = 0;
            let b = ((num >> 8) & 0x00FF) + amt;
            if (b > 255) b = 255; else if (b < 0) b = 0;
            let g = (num & 0x0000FF) + amt;
            if (g > 255) g = 255; else if (g < 0) g = 0;
            return (usePound ? "#" : "") + (g | (b << 8) | (r << 16)).toString(16).padStart(6, '0');
        }

        // Render Public View
        function renderCardView() {
            applyBrandColor(appData.brandColor || '#6366f1');

            document.getElementById('displayName').textContent = appData.name;
            document.getElementById('displayTitle').textContent = appData.title;
            document.getElementById('displayBio').textContent = appData.bio;
            document.getElementById('displayAvatar').src = appData.avatar;

            // Direct Links
            document.getElementById('btnCall').href = appData.phone ? `tel:${appData.phone}` : '#';
            document.getElementById('btnWhatsapp').href = appData.whatsapp ? `https://wa.me/${appData.whatsapp.replace(/\D/g,'')}` : '#';
            document.getElementById('btnEmail').href = appData.email ? `mailto:${appData.email}` : '#';
            document.getElementById('btnWebsite').href = appData.website || '#';

            // Social Links List
            const socialContainer = document.getElementById('socialLinksContainer');
            socialContainer.innerHTML = '';

            appData.socials.forEach(social => {
                if (!social.url) return;
                
                const linkEl = document.createElement('a');
                linkEl.href = social.url;
                linkEl.target = '_blank';
                linkEl.className = 'flex items-center justify-between bg-slate-800/60 hover:bg-slate-800 border border-white/5 hover:border-white/20 px-4 py-3 rounded-xl transition-all group';
                
                linkEl.innerHTML = `
                    <div class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-lg bg-white/5 flex items-center justify-center text-indigo-400 group-hover:text-white transition-colors">
                            <i class="${social.icon || 'fa-solid fa-link'}"></i>
                        </div>
                        <span class="text-sm font-medium text-slate-200 group-hover:text-white">${social.label}</span>
                    </div>
                    <i class="fa-solid fa-chevron-right text-xs text-slate-500 group-hover:text-slate-300 transition-colors"></i>
                `;
                socialContainer.appendChild(linkEl);
            });
        }

        // Render Admin Inputs in Editor Panel
        function populateAdminForm() {
            document.getElementById('editName').value = appData.name || '';
            document.getElementById('editTitle').value = appData.title || '';
            document.getElementById('editBio').value = appData.bio || '';
            document.getElementById('editAvatarUrl').value = appData.avatar || '';
            document.getElementById('editPhone').value = appData.phone || '';
            document.getElementById('editWhatsapp').value = appData.whatsapp || '';
            document.getElementById('editEmail').value = appData.email || '';
            document.getElementById('editWebsite').value = appData.website || '';
            document.getElementById('editBrandColor').value = appData.brandColor || '#6366f1';
            document.getElementById('colorHexText').textContent = appData.brandColor || '#6366f1';
            document.getElementById('editPin').value = appData.pin || '1234';

            // Social Inputs
            renderSocialInputs();
        }

        // Render dynamic social link input rows
        function renderSocialInputs() {
            const container = document.getElementById('socialInputsList');
            container.innerHTML = '';

            appData.socials.forEach((social, index) => {
                const row = document.createElement('div');
                row.className = 'flex items-center gap-2 bg-slate-900/50 p-2.5 rounded-xl border border-white/5';
                row.innerHTML = `
                    <select onchange="updateSocialPlatform(${index}, this.value)" class="glass-input text-xs rounded-lg px-2 py-2 w-28">
                        <option value="instagram" ${social.platform === 'instagram' ? 'selected' : ''}>Instagram</option>
                        <option value="linkedin" ${social.platform === 'linkedin' ? 'selected' : ''}>LinkedIn</option>
                        <option value="github" ${social.platform === 'github' ? 'selected' : ''}>GitHub</option>
                        <option value="whatsapp" ${social.platform === 'whatsapp' ? 'selected' : ''}>WhatsApp</option>
                        <option value="youtube" ${social.platform === 'youtube' ? 'selected' : ''}>YouTube</option>
                        <option value="tiktok" ${social.platform === 'tiktok' ? 'selected' : ''}>TikTok</option>
                        <option value="spotify" ${social.platform === 'spotify' ? 'selected' : ''}>Soundcloud/Spotify</option>
                        <option value="custom" ${social.platform === 'custom' ? 'selected' : ''}>Outro Link</option>
                    </select>
                    <input type="text" value="${social.label}" onchange="updateSocialLabel(${index}, this.value)" placeholder="Rótulo" class="glass-input text-xs rounded-lg px-2 py-2 w-28">
                    <input type="url" value="${social.url}" onchange="updateSocialUrl(${index}, this.value)" placeholder="https://..." class="glass-input text-xs rounded-lg px-2 py-2 flex-1">
                    <button type="button" onclick="removeSocialLink(${index})" class="text-rose-400 hover:text-rose-300 p-2 text-xs">
                        <i class="fa-solid fa-trash"></i>
                    </button>
                `;
                container.appendChild(row);
            });
        }

        // Helper Social Row Updates
        window.updateSocialPlatform = function(index, val) {
            const iconMap = {
                instagram: 'fa-brands fa-instagram',
                linkedin: 'fa-brands fa-linkedin-in',
                github: 'fa-brands fa-github',
                whatsapp: 'fa-brands fa-whatsapp',
                youtube: 'fa-brands fa-youtube',
                tiktok: 'fa-brands fa-tiktok',
                spotify: 'fa-brands fa-spotify',
                custom: 'fa-solid fa-link'
            };
            appData.socials[index].platform = val;
            appData.socials[index].icon = iconMap[val] || 'fa-solid fa-link';
        };

        window.updateSocialLabel = function(index, val) {
            appData.socials[index].label = val;
        };

        window.updateSocialUrl = function(index, val) {
            appData.socials[index].url = val;
        };

        window.removeSocialLink = function(index) {
            appData.socials.splice(index, 1);
            renderSocialInputs();
        };

        // Event Listeners Setup
        function setupEventListeners() {
            // Open Auth Modal
            openAuthBtn.addEventListener('click', () => {
                pinInput.value = '';
                authError.classList.add('hidden');
                authModal.classList.remove('hidden');
                pinInput.focus();
            });

            // Close Auth Modal
            closeAuthBtn.addEventListener('click', () => {
                authModal.classList.add('hidden');
            });

            // Verify PIN
            authForm.addEventListener('submit', (e) => {
                e.preventDefault();
                if (pinInput.value === appData.pin) {
                    authModal.classList.add('hidden');
                    populateAdminForm();
                    adminDrawer.classList.remove('hidden');
                } else {
                    authError.classList.remove('hidden');
                }
            });

            // Close Admin Panel
            closeAdminBtn.addEventListener('click', () => {
                adminDrawer.classList.add('hidden');
            });

            // Add Social Link
            document.getElementById('addSocialBtn').addEventListener('click', () => {
                appData.socials.push({
                    platform: 'custom',
                    label: 'Novo Link',
                    url: '',
                    icon: 'fa-solid fa-link'
                });
                renderSocialInputs();
            });

            // Color Picker text reflection
            document.getElementById('editBrandColor').addEventListener('input', (e) => {
                document.getElementById('colorHexText').textContent = e.target.value;
            });

            // File Upload for Avatar
            document.getElementById('editAvatarFile').addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    const reader = new FileReader();
                    reader.onload = function(evt) {
                        document.getElementById('editAvatarUrl').value = evt.target.result;
                    };
                    reader.readAsDataURL(file);
                }
            });

            // Save Admin Form
            saveAdminBtn.addEventListener('click', () => {
                appData.name = document.getElementById('editName').value;
                appData.title = document.getElementById('editTitle').value;
                appData.bio = document.getElementById('editBio').value;
                appData.avatar = document.getElementById('editAvatarUrl').value || DEFAULT_DATA.avatar;
                appData.phone = document.getElementById('editPhone').value;
                appData.whatsapp = document.getElementById('editWhatsapp').value;
                appData.email = document.getElementById('editEmail').value;
                appData.website = document.getElementById('editWebsite').value;
                appData.brandColor = document.getElementById('editBrandColor').value;
                
                const newPin = document.getElementById('editPin').value;
                if (newPin && newPin.trim() !== '') {
                    appData.pin = newPin.trim();
                }

                saveData();
                adminDrawer.classList.add('hidden');
            });

            // Save vCard Action (.vcf contact export)
            document.getElementById('saveVCardBtn').addEventListener('click', generateVCard);

            // Share Card URL
            document.getElementById('shareCardBtn').addEventListener('click', shareCard);
        }

        // Generate & Download vCard (.vcf)
        function generateVCard() {
            const vcardData = `BEGIN:VCARD
VERSION:3.0
FN:${appData.name}
TITLE:${appData.title}
TEL;TYPE=CELL:${appData.phone}
EMAIL:${appData.email}
URL:${appData.website}
NOTE:${appData.bio}
END:VCARD`;

            const blob = new Blob([vcardData], { type: 'text/vcard;charset=utf-8;' });
            const url = URL.createObjectURL(blob);
            const link = document.createElement('a');
            link.href = url;
            link.setAttribute('download', `${appData.name.replace(/\s+/g, '_')}_contato.vcf`);
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);

            showToast('Download do contato iniciado!');
        }

        // Share Card Functionality
        function shareCard() {
            const currentUrl = window.location.href;
            if (navigator.share) {
                navigator.share({
                    title: appData.name,
                    text: `Confira o cartão de visita digital de ${appData.name}`,
                    url: currentUrl
                }).catch(() => {});
            } else {
                // Clipboard fallback
                const dummy = document.createElement('input');
                document.body.appendChild(dummy);
                dummy.value = currentUrl;
                dummy.select();
                document.execCommand('copy');
                document.body.removeChild(dummy);
                showToast('Link do cartão copiado!');
            }
        }

        // Toast Helper
        function showToast(msg) {
            const toast = document.getElementById('toast');
            const toastMessage = document.getElementById('toastMessage');
            toastMessage.textContent = msg;
            toast.classList.remove('opacity-0', 'pointer-events-none');
            
            setTimeout(() => {
                toast.classList.add('opacity-0', 'pointer-events-none');
            }, 3000);
        }

        // Start Application
        window.onload = initApp;
    </script>
</body>
</html>
