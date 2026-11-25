<!DOCTYPE html>
<html lang="pt-BR" class="scroll-smooth">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Achados e Perdidos | IFPE — Instituto Federal de Pernambuco</title>
  
  <!-- Tailwind CSS via CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Google Fonts: Plus Jakarta Sans (Títulos) & Inter (Corpo e UI) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@600;700;800&display=swap" rel="stylesheet">
  
  <!-- Lucide Icons via CDN -->
  <script src="https://unpkg.com/lucide@latest"></script>

  <!-- Configuração customizada do Tailwind com paleta institucional do IFPE -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            display: ['Plus Jakarta Sans', 'sans-serif'],
          },
          colors: {
            ifpe: {
              50: '#f0fdf4',
              100: '#dcfce7',
              200: '#bbf7d0',
              500: '#2f9e41', // Verde oficial da Rede Federal
              600: '#247f33',
              700: '#1b6327',
              800: '#144d1e',
              900: '#0d3614',
              950: '#071f0b',
              red: '#cd191e', // Detalhe oficial do círculo da marca IF
            }
          },
          boxShadow: {
            'soft': '0 4px 20px -2px rgba(13, 54, 20, 0.06)',
            'card-hover': '0 14px 28px -6px rgba(13, 54, 20, 0.14)',
          }
        }
      }
    }
  </script>

  <style>
    /* Microinterações e animações sutis */
    .card-item {
      transition: transform 0.25s cubic-bezier(0.22, 1, 0.36, 1), box-shadow 0.25s ease, border-color 0.25s ease;
    }
    .card-item:hover {
      transform: translateY(-4px);
    }
    .hero-pattern {
      background-color: #0d3614;
      background-image: 
        radial-gradient(at 85% 15%, rgba(47, 158, 65, 0.35) 0px, transparent 50%),
        radial-gradient(at 10% 90%, rgba(20, 77, 30, 0.6) 0px, transparent 55%),
        linear-gradient(135deg, #0d3614 0%, #144d1e 60%, #1b6327 100%);
    }
    .grid-overlay {
      background-size: 32px 32px;
      background-image: linear-gradient(to right, rgba(255, 255, 255, 0.04) 1px, transparent 1px),
                        linear-gradient(to bottom, rgba(255, 255, 255, 0.04) 1px, transparent 1px);
    }
  </style>
</head>
<body class="bg-slate-50 text-slate-800 antialiased flex flex-col min-h-screen selection:bg-ifpe-500 selection:text-white">

  <!-- Barra Superior de Acessibilidade / Identidade Institucional -->
  <div class="bg-ifpe-950 text-slate-300 text-xs py-1.5 border-b border-ifpe-900">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-wrap items-center justify-between gap-2">
      <div class="flex items-center gap-2">
        <span class="inline-block w-2 h-2 rounded-full bg-ifpe-500 animate-pulse"></span>
        <span>Portal Oficial de Utilidade Comunitária — <strong class="text-white font-medium">Instituto Federal de Pernambuco</strong></span>
      </div>
      <div class="flex items-center gap-4">
        <a href="#itens-perdidos" class="hover:text-white transition-colors">Ir para o conteúdo</a>
        <span class="text-ifpe-800">|</span>
        <span class="hidden sm:inline">Atendimento Coordenação: 08h às 21h</span>
      </div>
    </div>
  </div>

  <!-- CABEÇALHO (HEADER) -->
  <header class="sticky top-0 z-40 bg-white/95 backdrop-blur-md border-b border-slate-200/80 shadow-sm">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-20">
        
        <!-- Logotipo Oficial IFPE (SVG fiel à identidade da Rede Federal) + Nome da Plataforma -->
        <a href="#inicio" class="flex items-center gap-3.5 group focus:outline-none">
          <div class="p-1.5 rounded-xl bg-slate-50 border border-slate-200/80 group-hover:border-ifpe-500/40 transition-colors">
            <!-- Marca Modular do IFPE: 9 módulos verdes + 1 círculo vermelho no topo esquerdo -->
            <svg width="34" height="44" viewBox="0 0 34 44" fill="none" xmlns="http://www.w3.org/2000/svg" aria-label="Logotipo do Instituto Federal de Pernambuco">
              <!-- Linha 1: Círculo Vermelho + 2 Quadrados Verdes -->
              <circle cx="5" cy="5" r="4.5" fill="#cd191e"/>
              <rect x="12.5" y="0.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="24.5" y="0.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <!-- Linha 2: 2 Quadrados Verdes -->
              <rect x="0.5" y="12" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="12.5" y="12" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <!-- Linha 3: 3 Quadrados Verdes -->
              <rect x="0.5" y="23.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="12.5" y="23.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="24.5" y="23.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <!-- Linha 4: 2 Quadrados Verdes -->
              <rect x="0.5" y="35" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="12.5" y="35" width="9" height="9" rx="1.5" fill="#2f9e41"/>
            </svg>
          </div>
          <div class="flex flex-col">
            <span class="text-[11px] font-bold uppercase tracking-wider text-ifpe-600 leading-tight">
              IFPE • Pernambuco
            </span>
            <span class="font-display font-extrabold text-xl sm:text-2xl text-slate-900 tracking-tight leading-none mt-0.5">
              Achados e Perdidos
            </span>
          </div>
        </a>

        <!-- Menu de Navegação Desktop -->
        <nav class="hidden md:flex items-center gap-1 lg:gap-2" aria-label="Navegação Principal">
          <a href="#inicio" class="px-3.5 py-2 rounded-lg text-sm font-semibold text-ifpe-700 bg-ifpe-50 transition-colors">
            Página inicial
          </a>
          <a href="#itens-perdidos" class="px-3.5 py-2 rounded-lg text-sm font-medium text-slate-600 hover:text-ifpe-700 hover:bg-slate-100/80 transition-colors">
            Itens perdidos
          </a>
          <button onclick="openModal('modal-adicionar')" class="px-3.5 py-2 rounded-lg text-sm font-medium text-slate-600 hover:text-ifpe-700 hover:bg-slate-100/80 transition-colors flex items-center gap-1.5">
            <i data-lucide="plus-circle" class="w-4 h-4 text-ifpe-600"></i>
            Adicionar item
          </button>
        </nav>

        <!-- Ações de Cadastro e Login (Desktop) -->
        <div class="hidden md:flex items-center gap-2.5">
          <button onclick="openModal('modal-auth', 'login')" class="px-4 py-2 rounded-xl text-sm font-semibold text-slate-700 hover:text-ifpe-700 hover:bg-slate-100 transition-colors">
            Login
          </button>
          <button onclick="openModal('modal-auth', 'cadastro')" class="px-4 py-2.5 rounded-xl text-sm font-semibold text-white bg-ifpe-600 hover:bg-ifpe-700 shadow-sm hover:shadow transition-all flex items-center gap-1.5">
            <i data-lucide="user-plus" class="w-4 h-4"></i>
            Cadastro
          </button>
        </div>

        <!-- Botão Menu Mobile -->
        <button id="mobile-menu-btn" onclick="toggleMobileMenu()" class="md:hidden p-2.5 rounded-xl text-slate-600 hover:bg-slate-100 focus:outline-none" aria-label="Abrir menu">
          <i data-lucide="menu" class="w-6 h-6"></i>
        </button>
      </div>
    </div>

    <!-- Menu Mobile Expansível -->
    <div id="mobile-menu" class="hidden md:hidden bg-white border-t border-slate-100 px-4 pt-3 pb-5 space-y-2 shadow-lg">
      <a href="#inicio" onclick="toggleMobileMenu()" class="block px-4 py-2.5 rounded-xl text-sm font-semibold text-ifpe-700 bg-ifpe-50">
        Página inicial
      </a>
      <a href="#itens-perdidos" onclick="toggleMobileMenu()" class="block px-4 py-2.5 rounded-xl text-sm font-medium text-slate-700 hover:bg-slate-50">
        Itens perdidos
      </a>
      <button onclick="toggleMobileMenu(); openModal('modal-adicionar')" class="w-full text-left px-4 py-2.5 rounded-xl text-sm font-medium text-slate-700 hover:bg-slate-50 flex items-center gap-2">
        <i data-lucide="plus-circle" class="w-4 h-4 text-ifpe-600"></i>
        Adicionar item
      </button>
      <div class="pt-3 border-t border-slate-100 grid grid-cols-2 gap-2">
        <button onclick="toggleMobileMenu(); openModal('modal-auth', 'login')" class="w-full py-2.5 rounded-xl text-sm font-semibold text-slate-700 border border-slate-200 hover:bg-slate-50">
          Login
        </button>
        <button onclick="toggleMobileMenu(); openModal('modal-auth', 'cadastro')" class="w-full py-2.5 rounded-xl text-sm font-semibold text-white bg-ifpe-600 hover:bg-ifpe-700">
          Cadastro
        </button>
      </div>
    </div>
  </header>

  <!-- SEÇÃO PRINCIPAL (HERO SECTION) -->
  <section id="inicio" class="hero-pattern relative overflow-hidden text-white">
    <div class="grid-overlay absolute inset-0 pointer-events-none"></div>
    
    <!-- Elementos decorativos sutis -->
    <div class="absolute -top-24 -right-24 w-96 h-96 rounded-full bg-ifpe-500/20 blur-3xl pointer-events-none"></div>
    <div class="absolute -bottom-24 -left-24 w-80 h-80 rounded-full bg-emerald-400/10 blur-3xl pointer-events-none"></div>

    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-14 sm:py-20 lg:py-24">
      <div class="max-w-3xl mx-auto text-center">
        
        <!-- Badge institucional -->
        <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-white/10 border border-white/15 backdrop-blur-sm text-ifpe-100 text-xs sm:text-sm font-medium mb-6">
          <i data-lucide="shield-check" class="w-4 h-4 text-ifpe-200"></i>
          <span>Plataforma Integrada da Comunidade Acadêmica IFPE</span>
        </div>

        <!-- Título de Destaque -->
        <h1 class="font-display font-extrabold text-4xl sm:text-5xl lg:text-6xl tracking-tight text-white mb-5">
          Achados e Perdidos
        </h1>
        
        <!-- Subtítulo descritivo preservando a essência do site original -->
        <p class="text-base sm:text-lg text-ifpe-100/90 leading-relaxed mb-8 max-w-2xl mx-auto">
          Aqui você pode encontrar objetos perdidos no campus ou cadastrar itens que foram encontrados para devolução rápida e segura aos estudantes, professores e servidores.
        </p>

        <!-- Barra de Busca Integrada -->
        <div class="bg-white p-2 rounded-2xl shadow-xl max-w-2xl mx-auto flex flex-col sm:flex-row gap-2">
          <div class="relative flex-1 flex items-center">
            <i data-lucide="search" class="w-5 h-5 text-slate-400 ml-3.5 shrink-0"></i>
            <input 
              type="text" 
              id="search-input"
              oninput="filterItems()"
              placeholder="Buscar por caderno, guarda-chuva, livro, local..." 
              class="w-full px-3.5 py-3 text-slate-800 placeholder-slate-400 text-sm sm:text-base focus:outline-none bg-transparent"
              aria-label="Pesquisar objetos perdidos"
            >
          </div>
          <a href="#itens-perdidos" class="px-6 py-3 rounded-xl bg-ifpe-600 hover:bg-ifpe-700 text-white font-semibold text-sm sm:text-base transition-colors flex items-center justify-center gap-2 shrink-0">
            <span>Buscar Objeto</span>
            <i data-lucide="arrow-down" class="w-4 h-4"></i>
          </a>
        </div>

        <!-- Ações rápidas / Indicadores -->
        <div class="mt-8 flex flex-wrap items-center justify-center gap-4 sm:gap-8 text-xs sm:text-sm text-ifpe-100/80">
          <div class="flex items-center gap-2">
            <span class="w-2 h-2 rounded-full bg-emerald-400"></span>
            <span id="hero-counter">3 objetos aguardando retirada</span>
          </div>
          <button onclick="openModal('modal-adicionar')" class="inline-flex items-center gap-1.5 text-white font-semibold underline decoration-ifpe-400 underline-offset-4 hover:text-ifpe-200 transition-colors">
            <i data-lucide="plus" class="w-4 h-4"></i>
            Encontrou algo no campus? Cadastre agora
          </button>
        </div>

      </div>
    </div>
  </section>

  <!-- CONTEÚDO PRINCIPAL: VITRINE DE ITENS PERDIDOS -->
  <main id="itens-perdidos" class="flex-1 max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-12 sm:py-16">
    
    <!-- Cabeçalho da Seção + Filtros por Categoria -->
    <div class="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-8">
      <div>
        <span class="text-xs font-bold uppercase tracking-wider text-ifpe-600">Mural Atualizado</span>
        <h2 class="font-display font-bold text-2xl sm:text-3xl text-slate-900 mt-1">
          Itens Perdidos
        </h2>
        <p class="text-sm sm:text-base text-slate-600 mt-1">
          Confira os objetos registrados recentemente e clique em <strong class="font-medium text-slate-800">Mais detalhes</strong> para verificar o local de retirada.
        </p>
      </div>

      <!-- Botões de Filtro -->
      <div class="flex flex-wrap items-center gap-2" role="group" aria-label="Filtrar itens por categoria">
        <button onclick="setCategory('Todos')" data-cat="Todos" class="cat-btn active px-4 py-2 rounded-xl text-sm font-semibold bg-ifpe-700 text-white shadow-sm transition-all">
          Todos
        </button>
        <button onclick="setCategory('Material Escolar')" data-cat="Material Escolar" class="cat-btn px-4 py-2 rounded-xl text-sm font-medium bg-white text-slate-600 border border-slate-200 hover:border-ifpe-500 hover:text-ifpe-700 transition-all">
          Material Escolar
        </button>
        <button onclick="setCategory('Livros')" data-cat="Livros" class="cat-btn px-4 py-2 rounded-xl text-sm font-medium bg-white text-slate-600 border border-slate-200 hover:border-ifpe-500 hover:text-ifpe-700 transition-all">
          Livros
        </button>
        <button onclick="setCategory('Acessórios')" data-cat="Acessórios" class="cat-btn px-4 py-2 rounded-xl text-sm font-medium bg-white text-slate-600 border border-slate-200 hover:border-ifpe-500 hover:text-ifpe-700 transition-all">
          Acessórios
        </button>
      </div>
    </div>

    <!-- Grade Responsiva de Cartões (Cards) -->
    <div id="items-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-8">
      <!-- Os cartões são renderizados dinamicamente via JavaScript mantendo os 3 itens originais da imagem -->
    </div>

    <!-- Estado Vazio (caso a busca não encontre nada) -->
    <div id="empty-state" class="hidden text-center py-16 bg-white rounded-3xl border border-slate-200/80 shadow-soft">
      <div class="w-16 h-16 rounded-2xl bg-ifpe-50 text-ifpe-600 flex items-center justify-center mx-auto mb-4">
        <i data-lucide="search-x" class="w-8 h-8"></i>
      </div>
      <h3 class="font-display font-bold text-xl text-slate-900">Nenhum objeto encontrado</h3>
      <p class="text-slate-500 text-sm max-w-md mx-auto mt-1 mb-6">
        Não encontramos itens com esse termo de busca. Tente limpar os filtros ou cadastre um novo objeto encontrado.
      </p>
      <button onclick="resetFilters()" class="px-5 py-2.5 rounded-xl bg-ifpe-600 hover:bg-ifpe-700 text-white text-sm font-semibold transition-colors">
        Limpar filtros
      </button>
    </div>

    <!-- Seção de Orientações Rápidas (Credibilidade Institucional) -->
    <section class="mt-16 bg-white rounded-3xl border border-slate-200/80 p-6 sm:p-10 shadow-soft">
      <div class="flex flex-col lg:flex-row lg:items-center justify-between gap-8">
        <div class="max-w-xl">
          <span class="inline-flex items-center gap-1.5 text-xs font-bold uppercase tracking-wider text-ifpe-600 bg-ifpe-50 px-3 py-1 rounded-full">
            <i data-lucide="info" class="w-3.5 h-3.5"></i>
            Como funciona
          </span>
          <h3 class="font-display font-bold text-2xl text-slate-900 mt-3">
            Procedimento para devolução e retirada
          </h3>
          <p class="text-slate-600 text-sm sm:text-base mt-2 leading-relaxed">
            Para garantir a segurança dos pertences da comunidade acadêmica, todos os itens registrados ficam sob guarda da Coordenação de Apoio ao Ensino (CAE) ou Guarita Central do campus.
          </p>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 flex-1">
          <div class="p-4 rounded-2xl bg-slate-50 border border-slate-100">
            <div class="w-9 h-9 rounded-xl bg-ifpe-600 text-white font-display font-bold flex items-center justify-center text-sm mb-3">1</div>
            <h4 class="font-semibold text-slate-900 text-sm">Localize no Mural</h4>
            <p class="text-xs text-slate-500 mt-1">Verifique foto, descrição e bloco onde o objeto foi encontrado.</p>
          </div>
          <div class="p-4 rounded-2xl bg-slate-50 border border-slate-100">
            <div class="w-9 h-9 rounded-xl bg-ifpe-600 text-white font-display font-bold flex items-center justify-center text-sm mb-3">2</div>
            <h4 class="font-semibold text-slate-900 text-sm">Vá ao Setor</h4>
            <p class="text-xs text-slate-500 mt-1">Dirija-se à sala indicada nos detalhes do item dentro do horário letivo.</p>
          </div>
          <div class="p-4 rounded-2xl bg-slate-50 border border-slate-100">
            <div class="w-9 h-9 rounded-xl bg-ifpe-600 text-white font-display font-bold flex items-center justify-center text-sm mb-3">3</div>
            <h4 class="font-semibold text-slate-900 text-sm">Comprove a Posse</h4>
            <p class="text-xs text-slate-500 mt-1">Apresente crachá, carteira estudantil ou documento com foto.</p>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- RODAPÉ INSTITUCIONAL (FOOTER) -->
  <footer class="bg-ifpe-950 text-slate-300 border-t border-ifpe-900 mt-auto">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 pb-8 border-b border-ifpe-900/80">
        
        <!-- Coluna 1: Identidade IFPE -->
        <div>
          <div class="flex items-center gap-3 mb-3">
            <svg width="26" height="34" viewBox="0 0 34 44" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
              <circle cx="5" cy="5" r="4.5" fill="#cd191e"/>
              <rect x="12.5" y="0.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="24.5" y="0.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="0.5" y="12" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="12.5" y="12" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="0.5" y="23.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="12.5" y="23.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="24.5" y="23.5" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="0.5" y="35" width="9" height="9" rx="1.5" fill="#2f9e41"/>
              <rect x="12.5" y="35" width="9" height="9" rx="1.5" fill="#2f9e41"/>
            </svg>
            <div>
              <p class="font-display font-bold text-white text-base leading-tight">IFPE — Achados e Perdidos</p>
              <p class="text-xs text-ifpe-200/80">Instituto Federal de Pernambuco</p>
            </div>
          </div>
          <p class="text-xs text-slate-400 leading-relaxed max-w-sm">
            Sistema institucional desenvolvido para facilitar a localização e devolução de objetos perdidos nas dependências do campus.
          </p>
        </div>

        <!-- Coluna 2: Links Rápidos -->
        <div>
          <h4 class="font-display font-semibold text-white text-sm mb-3">Navegação</h4>
          <ul class="space-y-2 text-xs text-slate-400">
            <li><a href="#inicio" class="hover:text-white transition-colors">Página inicial</a></li>
            <li><a href="#itens-perdidos" class="hover:text-white transition-colors">Itens perdidos</a></li>
            <li><button onclick="openModal('modal-adicionar')" class="hover:text-white transition-colors">Adicionar item encontrado</button></li>
            <li><button onclick="openModal('modal-auth', 'cadastro')" class="hover:text-white transition-colors">Cadastro e Login</button></li>
          </ul>
        </div>

        <!-- Coluna 3: Contato Institucional -->
        <div>
          <h4 class="font-display font-semibold text-white text-sm mb-3">Atendimento no Campus</h4>
          <ul class="space-y-2 text-xs text-slate-400">
            <li class="flex items-center gap-2">
              <i data-lucide="map-pin" class="w-4 h-4 text-ifpe-500 shrink-0"></i>
              <span>Coordenação de Apoio ao Ensino (Bloco Administrativo)</span>
            </li>
            <li class="flex items-center gap-2">
              <i data-lucide="clock" class="w-4 h-4 text-ifpe-500 shrink-0"></i>
              <span>Segunda a Sexta, das 08h00 às 21h00</span>
            </li>
            <li class="flex items-center gap-2">
              <i data-lucide="mail" class="w-4 h-4 text-ifpe-500 shrink-0"></i>
              <span>achadoseperdidos@ifpe.edu.br</span>
            </li>
          </ul>
        </div>
      </div>

      <div class="pt-6 flex flex-col sm:flex-row items-center justify-between gap-4 text-xs text-slate-400">
        <p>© 2026 IFPE — Instituto Federal de Educação, Ciência e Tecnologia de Pernambuco. Todos os direitos reservados.</p>
        <p class="text-slate-500">Projeto Acadêmico • Design UI/UX Institucional</p>
      </div>
    </div>
  </footer>

  <!-- ===================================================================== -->
  <!-- MODAL 1: DETALHES DO ITEM                                             -->
  <!-- ===================================================================== -->
  <div id="modal-detalhes" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-950/60 backdrop-blur-sm">
    <div class="bg-white rounded-3xl max-w-lg w-full overflow-hidden shadow-2xl border border-slate-200 animate-[fadeIn_0.2s_ease-out]">
      <div class="relative h-60 bg-slate-100">
        <img id="detalhe-img" src="" alt="" class="w-full h-full object-cover">
        <button onclick="closeModal('modal-detalhes')" class="absolute top-4 right-4 w-9 h-9 rounded-full bg-white/90 hover:bg-white text-slate-800 flex items-center justify-center shadow-md transition-colors" aria-label="Fechar janela">
          <i data-lucide="x" class="w-5 h-5"></i>
        </button>
        <span id="detalhe-categoria" class="absolute bottom-4 left-4 px-3 py-1 rounded-full text-xs font-semibold bg-ifpe-700 text-white shadow"></span>
      </div>
      
      <div class="p-6 sm:p-7">
        <div class="flex items-center justify-between gap-2 mb-2">
          <span id="detalhe-status" class="inline-flex items-center gap-1.5 text-xs font-semibold text-emerald-700 bg-emerald-50 border border-emerald-200 px-2.5 py-1 rounded-full">
            <span class="w-1.5 h-1.5 rounded-full bg-emerald-500"></span>
            Disponível para retirada
          </span>
          <span id="detalhe-data" class="text-xs text-slate-400 font-medium"></span>
        </div>

        <h3 id="detalhe-titulo" class="font-display font-bold text-2xl text-slate-900 mt-1"></h3>
        <p id="detalhe-descricao" class="text-slate-600 text-sm leading-relaxed mt-2"></p>

        <div class="mt-5 p-4 rounded-2xl bg-slate-50 border border-slate-200/70 space-y-2.5 text-sm">
          <div class="flex items-center gap-2.5 text-slate-700">
            <i data-lucide="map-pin" class="w-4 h-4 text-ifpe-600 shrink-0"></i>
            <span><strong>Encontrado em:</strong> <span id="detalhe-local"></span></span>
          </div>
          <div class="flex items-center gap-2.5 text-slate-700">
            <i data-lucide="building-2" class="w-4 h-4 text-ifpe-600 shrink-0"></i>
            <span><strong>Local de retirada:</strong> <span id="detalhe-retirada"></span></span>
          </div>
        </div>

        <div class="mt-6 flex flex-col sm:flex-row gap-3">
          <button onclick="reivindicarItem()" class="flex-1 py-3 px-4 rounded-xl bg-ifpe-600 hover:bg-ifpe-700 text-white font-semibold text-sm transition-colors flex items-center justify-center gap-2">
            <i data-lucide="check-circle-2" class="w-4 h-4"></i>
            Este item é meu
          </button>
          <button onclick="closeModal('modal-detalhes')" class="py-3 px-5 rounded-xl border border-slate-200 hover:bg-slate-50 text-slate-700 font-semibold text-sm transition-colors">
            Fechar
          </button>
        </div>
      </div>
    </div>
  </div>

  <!-- ===================================================================== -->
  <!-- MODAL 2: ADICIONAR NOVO ITEM                                          -->
  <!-- ===================================================================== -->
  <div id="modal-adicionar" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-950/60 backdrop-blur-sm">
    <div class="bg-white rounded-3xl max-w-lg w-full overflow-hidden shadow-2xl border border-slate-200">
      <div class="px-6 py-5 bg-ifpe-900 text-white flex items-center justify-between">
        <div class="flex items-center gap-2.5">
          <i data-lucide="package-plus" class="w-5 h-5 text-ifpe-200"></i>
          <h3 class="font-display font-bold text-lg">Cadastrar Objeto Encontrado</h3>
        </div>
        <button onclick="closeModal('modal-adicionar')" class="text-white/80 hover:text-white p-1" aria-label="Fechar formulário">
          <i data-lucide="x" class="w-5 h-5"></i>
        </button>
      </div>

      <form onsubmit="handleAddItem(event)" class="p-6 space-y-4">
        <div>
          <label class="block text-xs font-semibold uppercase tracking-wider text-slate-600 mb-1.5">Nome do Objeto *</label>
          <input type="text" id="novo-titulo" required placeholder="Ex: Garrafa térmica verde, Chaveiro..." class="w-full px-4 py-2.5 rounded-xl border border-slate-300 text-sm focus:outline-none focus:border-ifpe-600 focus:ring-2 focus:ring-ifpe-500/20">
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
          <div>
            <label class="block text-xs font-semibold uppercase tracking-wider text-slate-600 mb-1.5">Categoria *</label>
            <select id="novo-categoria" class="w-full px-4 py-2.5 rounded-xl border border-slate-300 text-sm bg-white focus:outline-none focus:border-ifpe-600">
              <option value="Material Escolar">Material Escolar</option>
              <option value="Livros">Livros</option>
              <option value="Acessórios">Acessórios</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-semibold uppercase tracking-wider text-slate-600 mb-1.5">Local Encontrado *</label>
            <input type="text" id="novo-local" required placeholder="Ex: Biblioteca, Bloco B..." class="w-full px-4 py-2.5 rounded-xl border border-slate-300 text-sm focus:outline-none focus:border-ifpe-600">
          </div>
        </div>

        <div>
          <label class="block text-xs font-semibold uppercase tracking-wider text-slate-600 mb-1.5">Descrição detalhada *</label>
          <textarea id="novo-descricao" required rows="3" placeholder="Informe cor, marca, adesivos ou detalhes que ajudem a identificar o dono..." class="w-full px-4 py-2.5 rounded-xl border border-slate-300 text-sm focus:outline-none focus:border-ifpe-600"></textarea>
        </div>

        <div class="pt-2 flex justify-end gap-3">
          <button type="button" onclick="closeModal('modal-adicionar')" class="px-4 py-2.5 rounded-xl border border-slate-200 text-slate-700 text-sm font-semibold hover:bg-slate-50">
            Cancelar
          </button>
          <button type="submit" class="px-5 py-2.5 rounded-xl bg-ifpe-600 hover:bg-ifpe-700 text-white text-sm font-semibold shadow-sm transition-colors">
            Publicar no Mural
          </button>
        </div>
      </form>
    </div>
  </div>

  <!-- ===================================================================== -->
  <!-- MODAL 3: LOGIN / CADASTRO INSTITUCIONAL                               -->
  <!-- ===================================================================== -->
  <div id="modal-auth" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-950/60 backdrop-blur-sm">
    <div class="bg-white rounded-3xl max-w-md w-full overflow-hidden shadow-2xl border border-slate-200">
      <div class="p-6 sm:p-7">
        <div class="flex items-center justify-between mb-6">
          <div class="flex items-center gap-2.5">
            <div class="w-9 h-9 rounded-xl bg-ifpe-50 text-ifpe-600 flex items-center justify-center">
              <i data-lucide="user-check" class="w-5 h-5"></i>
            </div>
            <div>
              <h3 id="auth-title" class="font-display font-bold text-xl text-slate-900">Acesso Institucional</h3>
              <p class="text-xs text-slate-500">Estudantes, docentes e técnicos do IFPE</p>
            </div>
          </div>
          <button onclick="closeModal('modal-auth')" class="text-slate-400 hover:text-slate-700 p-1" aria-label="Fechar">
            <i data-lucide="x" class="w-5 h-5"></i>
          </button>
        </div>

        <!-- Abas Login / Cadastro -->
        <div class="grid grid-cols-2 p-1 rounded-xl bg-slate-100 mb-5">
          <button id="tab-login" onclick="switchAuthTab('login')" class="py-2 rounded-lg text-xs font-bold bg-white text-ifpe-700 shadow-sm transition-all">
            Login
          </button>
          <button id="tab-cadastro" onclick="switchAuthTab('cadastro')" class="py-2 rounded-lg text-xs font-bold text-slate-500 hover:text-slate-800 transition-all">
            Cadastro
          </button>
        </div>

        <form onsubmit="handleAuth(event)" class="space-y-4">
          <div id="field-nome" class="hidden">
            <label class="block text-xs font-semibold text-slate-700 mb-1">Nome Completo</label>
            <input type="text" placeholder="Seu nome completo" class="w-full px-3.5 py-2.5 rounded-xl border border-slate-300 text-sm focus:outline-none focus:border-ifpe-600">
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-700 mb-1">E-mail Institucional ou Matrícula</label>
            <input type="text" required placeholder="ex: nome@discente.ifpe.edu.br" class="w-full px-3.5 py-2.5 rounded-xl border border-slate-300 text-sm focus:outline-none focus:border-ifpe-600">
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-700 mb-1">Senha</label>
            <input type="password" required placeholder="••••••••" class="w-full px-3.5 py-2.5 rounded-xl border border-slate-300 text-sm focus:outline-none focus:border-ifpe-600">
          </div>
          <button type="submit" id="auth-submit-btn" class="w-full py-3 rounded-xl bg-ifpe-600 hover:bg-ifpe-700 text-white font-semibold text-sm shadow-sm transition-colors mt-2">
            Entrar na Plataforma
          </button>
        </form>
      </div>
    </div>
  </div>

  <!-- NOTIFICAÇÃO TOAST (Substitui alert() de forma elegante) -->
  <div id="toast" class="fixed bottom-5 right-5 z-50 transform translate-y-24 opacity-0 transition-all duration-300 pointer-events-none">
    <div class="bg-ifpe-900 text-white px-5 py-3.5 rounded-2xl shadow-xl border border-ifpe-700 flex items-center gap-3 max-w-sm">
      <div class="w-8 h-8 rounded-full bg-ifpe-500/20 text-ifpe-200 flex items-center justify-center shrink-0">
        <i data-lucide="check" class="w-4 h-4"></i>
      </div>
      <p id="toast-msg" class="text-sm font-medium"></p>
    </div>
  </div>

  <!-- LÓGICA DE INTERAÇÃO E DADOS INICIAIS -->
  <script>
    // Dados baseados exatamente nos 3 itens presentes na imagem original enviada
    const itemsData = [
      {
        id: 1,
        titulo: "Caderno Hello Kitty",
        categoria: "Material Escolar",
        descricao: "Caderno espiral com capa temática da Hello Kitty, sem identificação ou nome do dono(a) na contracapa.",
        local: "Biblioteca — Mesa de estudos 04",
        retirada: "Coordenação de Apoio ao Ensino (CAE)",
        data: "Encontrado em 22/11/2026",
        imagem: "https://images.unsplash.com/photo-1544816155-12df9643f363?auto=format&fit=crop&w=800&q=80",
        fallbackText: "Caderno+Hello+Kitty"
      },
      {
        id: 2,
        titulo: "Guarda-Chuva",
        categoria: "Acessórios",
        descricao: "Guarda-chuva dobrável escuro com cabo ergonômico, esquecido próximo à entrada principal durante a chuva.",
        local: "Bloco A — Corredor térreo",
        retirada: "Guarita Central / Recepção",
        data: "Encontrado em 23/11/2026",
        imagem: "https://images.unsplash.com/photo-1556905200-279565513a2d?auto=format&fit=crop&w=800&q=80",
        fallbackText: "Guarda-Chuva"
      },
      {
        id: 3,
        titulo: "Livro: Vermelho, Branco e Sangue Azul",
        categoria: "Livros",
        descricao: "Exemplar de romance contemporâneo ('Uma história emocionante sobre amor e identidade...'), em ótimo estado de conservação.",
        local: "Pátio de Convivência",
        retirada: "Balcão da Biblioteca",
        data: "Encontrado em 24/11/2026",
        imagem: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?auto=format&fit=crop&w=800&q=80",
        fallbackText: "Livro+Achado"
      }
    ];

    let currentCategory = 'Todos';

    // Renderiza os cartões na grade
    function renderItems(list) {
      const grid = document.getElementById('items-grid');
      const emptyState = document.getElementById('empty-state');
      const heroCounter = document.getElementById('hero-counter');

      heroCounter.textContent = `${itemsData.length} ${itemsData.length === 1 ? 'objeto aguardando retirada' : 'objetos aguardando retirada'}`;

      if (list.length === 0) {
        grid.innerHTML = '';
        emptyState.classList.remove('hidden');
        lucide.createIcons();
        return;
      }

      emptyState.classList.add('hidden');

      grid.innerHTML = list.map(item => `
        <article class="card-item bg-white rounded-3xl border border-slate-200/90 overflow-hidden shadow-soft hover:shadow-card-hover hover:border-ifpe-500/40 flex flex-col">
          <!-- Imagem do Objeto -->
          <div class="relative h-52 bg-slate-100 overflow-hidden group">
            <img 
              src="${item.imagem}" 
              alt="${item.titulo}"
              onerror="this.onerror=null;this.src='https://placehold.co/600x400/144d1e/ffffff?text=${item.fallbackText}';"
              class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500"
            >
            <span class="absolute top-3.5 left-3.5 px-3 py-1 rounded-full text-xs font-semibold bg-white/95 text-ifpe-800 shadow-sm backdrop-blur-sm">
              ${item.categoria}
            </span>
          </div>

          <!-- Conteúdo do Cartão -->
          <div class="p-6 flex-1 flex flex-col">
            <div class="flex items-center gap-1.5 text-xs text-slate-400 font-medium mb-2">
              <i data-lucide="calendar" class="w-3.5 h-3.5 text-ifpe-600"></i>
              <span>${item.data}</span>
            </div>

            <h3 class="font-display font-bold text-xl text-slate-900 leading-snug">
              ${item.titulo}
            </h3>

            <p class="text-sm text-slate-600 mt-2 line-clamp-2 leading-relaxed flex-1">
              ${item.descricao}
            </p>

            <div class="mt-4 pt-4 border-t border-slate-100 flex items-center justify-between gap-2">
              <div class="flex items-center gap-1.5 text-xs text-slate-500 truncate">
                <i data-lucide="map-pin" class="w-3.5 h-3.5 text-ifpe-600 shrink-0"></i>
                <span class="truncate">${item.local}</span>
              </div>

              <button 
                onclick="openDetails(${item.id})"
                class="inline-flex items-center gap-1.5 px-3.5 py-2 rounded-xl text-xs font-bold text-ifpe-700 bg-ifpe-50 hover:bg-ifpe-600 hover:text-white transition-colors shrink-0">
                <span>Mais detalhes</span>
                <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i>
              </button>
            </div>
          </div>
        </article>
      `).join('');

      lucide.createIcons();
    }

    // Filtra por categoria e texto de busca
    function filterItems() {
      const query = document.getElementById('search-input').value.toLowerCase().trim();
      const filtered = itemsData.filter(item => {
        const matchCat = currentCategory === 'Todos' || item.categoria === currentCategory;
        const matchText = item.titulo.toLowerCase().includes(query) ||
                          item.descricao.toLowerCase().includes(query) ||
                          item.local.toLowerCase().includes(query);
        return matchCat && matchText;
      });
      renderItems(filtered);
    }

    function setCategory(cat) {
      currentCategory = cat;
      document.querySelectorAll('.cat-btn').forEach(btn => {
        if (btn.dataset.cat === cat) {
          btn.className = 'cat-btn active px-4 py-2 rounded-xl text-sm font-semibold bg-ifpe-700 text-white shadow-sm transition-all';
        } else {
          btn.className = 'cat-btn px-4 py-2 rounded-xl text-sm font-medium bg-white text-slate-600 border border-slate-200 hover:border-ifpe-500 hover:text-ifpe-700 transition-all';
        }
      });
      filterItems();
    }

    function resetFilters() {
      document.getElementById('search-input').value = '';
      setCategory('Todos');
    }

    // Abre modal de detalhes do item
    function openDetails(id) {
      const item = itemsData.find(i => i.id === id);
      if (!item) return;

      const imgEl = document.getElementById('detalhe-img');
      imgEl.src = item.imagem;
      imgEl.alt = item.titulo;
      imgEl.onerror = function() {
        this.onerror = null;
        this.src = `https://placehold.co/600x400/144d1e/ffffff?text=${item.fallbackText}`;
      };

      document.getElementById('detalhe-categoria').textContent = item.categoria;
      document.getElementById('detalhe-data').textContent = item.data;
      document.getElementById('detalhe-titulo').textContent = item.titulo;
      document.getElementById('detalhe-descricao').textContent = item.descricao;
      document.getElementById('detalhe-local').textContent = item.local;
      document.getElementById('detalhe-retirada').textContent = item.retirada;

      openModal('modal-detalhes');
    }

    function reivindicarItem() {
      closeModal('modal-detalhes');
      showToast('Solicitação registrada! Procure o setor de retirada com seu documento.');
    }

    // Adiciona novo item ao mural
    function handleAddItem(e) {
      e.preventDefault();
      const titulo = document.getElementById('novo-titulo').value.trim();
      const categoria = document.getElementById('novo-categoria').value;
      const local = document.getElementById('novo-local').value.trim();
      const descricao = document.getElementById('novo-descricao').value.trim();

      const newItem = {
        id: Date.now(),
        titulo,
        categoria,
        descricao,
        local,
        retirada: "Coordenação de Apoio ao Ensino (CAE)",
        data: "Encontrado hoje",
        imagem: "https://images.unsplash.com/photo-1586769852044-692d6e3703f0?auto=format&fit=crop&w=800&q=80",
        fallbackText: encodeURIComponent(titulo)
      };

      itemsData.unshift(newItem);
      e.target.reset();
      closeModal('modal-adicionar');
      resetFilters();
      showToast('Objeto publicado com sucesso no mural do IFPE!');
    }

    // Controle de Modais e Menu Mobile
    function openModal(id, mode) {
      const modal = document.getElementById(id);
      modal.classList.remove('hidden');
      modal.classList.add('flex');
      if (id === 'modal-auth' && mode) {
        switchAuthTab(mode);
      }
      lucide.createIcons();
    }

    function closeModal(id) {
      const modal = document.getElementById(id);
      modal.classList.add('hidden');
      modal.classList.remove('flex');
    }

    function toggleMobileMenu() {
      document.getElementById('mobile-menu').classList.toggle('hidden');
    }

    function switchAuthTab(mode) {
      const tabLogin = document.getElementById('tab-login');
      const tabCadastro = document.getElementById('tab-cadastro');
      const fieldNome = document.getElementById('field-nome');
      const btnSubmit = document.getElementById('auth-submit-btn');

      if (mode === 'cadastro') {
        tabCadastro.className = 'py-2 rounded-lg text-xs font-bold bg-white text-ifpe-700 shadow-sm transition-all';
        tabLogin.className = 'py-2 rounded-lg text-xs font-bold text-slate-500 hover:text-slate-800 transition-all';
        fieldNome.classList.remove('hidden');
        btnSubmit.textContent = 'Criar Conta Institucional';
      } else {
        tabLogin.className = 'py-2 rounded-lg text-xs font-bold bg-white text-ifpe-700 shadow-sm transition-all';
        tabCadastro.className = 'py-2 rounded-lg text-xs font-bold text-slate-500 hover:text-slate-800 transition-all';
        fieldNome.classList.add('hidden');
        btnSubmit.textContent = 'Entrar na Plataforma';
      }
    }

    function handleAuth(e) {
      e.preventDefault();
      closeModal('modal-auth');
      showToast('Autenticação realizada com sucesso!');
    }

    // Notificação Toast
    function showToast(message) {
      const toast = document.getElementById('toast');
      document.getElementById('toast-msg').textContent = message;
      toast.classList.remove('translate-y-24', 'opacity-0');
      setTimeout(() => {
        toast.classList.add('translate-y-24', 'opacity-0');
      }, 4000);
    }

    // Fechar modais ao clicar fora
    window.addEventListener('click', (e) => {
      ['modal-detalhes', 'modal-adicionar', 'modal-auth'].forEach(id => {
        const modal = document.getElementById(id);
        if (e.target === modal) closeModal(id);
      });
    });

    // Inicialização
    document.addEventListener('DOMContentLoaded', () => {
      renderItems(itemsData);
      lucide.createIcons();
    });
  </script>
</body>
</html>
