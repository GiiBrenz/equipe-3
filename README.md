# ⚡ PromTrim — Painel de Controle de Intenções

O **PromTrim** é um Painel de Controle de Intenções projetado para consumir modelos de IA generativa (Google Gemini) de forma ultra-otimizada. Através de **Engenharia de Prompts Invisível** no back-end, o PromTrim lapida as requisições do usuário antes de enviá-las, garantindo respostas cirúrgicas, latência mínima, economia drástica de tokens e eliminação de alucinações.

![Demonstração do PromTrim](Frontend-ezgif.com-speed.gif)

---

## ✨ Funcionalidades Principais

* 🎯 **Filtro de Intenções Invisível**: A aplicação não envia apenas a sua pergunta. Ela envelopa o seu problema em system instructions específicas de acordo com a sua intenção de uso:
  1. **Código Limpo (Apenas Implementação)**: Resposta contendo única e exclusivamente código modular, documentado e pronto para produção, sem blá-blá-blá introdutório ou conclusões verbosas.
  2. **Explicação Teórica (Arquitetura/Conceitos)**: Foco nos padrões de projeto (Design Patterns), trade-offs, escalabilidade e impacto na performance, usando diagramas conceituais e sem códigos longos desnecessários.
  3. **Recomendação de Ferramentas / Libs**: Comparação crítica de pacotes do ecossistema moderno contendo prós, contras, popularidade e um veredito de recomendação explícito.
  4. **Revisão de Segurança (Caça-Bugs)**: Análise de vulnerabilidades sob a ótica de segurança de aplicações (AppSec, OWASP Top 10) com snippets de mitigação imediatos.
* 🚀 **Latência Otimizada e Economia de Tokens**: As system instructions forçam respostas curtas e focadas, reduzindo o tempo de espera do usuário e economizando o uso de tokens da API do Gemini.
* 🎨 **Interface Premium Glassmorphism**: Um design escuro sofisticado e responsivo, dotado de:
  - Micro-animações e esqueleto de carregamento animado (skeleton loader).
  - Renderização fluida de Markdown em tempo real.
  - Realce de sintaxe de código profissional (Syntax Highlighting) com **PrismJS**.
  - Função integrada de cópia rápida para a área de transferência.
* 🔌 **Modo Fallback Inteligente**: Se você não possuir uma chave do Gemini configurada, o PromTrim entra em modo de depuração/mock mostrando exatamente a ideia recebida e o prompt invisível de sistema correspondente montado pelo backend.

---

## 📂 Arquitetura MVC do Projeto

O projeto é estruturado de forma limpa e modular seguindo o padrão MVC:

```text
promtrim/
├── requirements.txt         # Pacotes Python dependentes
├── .env                     # Arquivo de configuração de chaves
├── servidor.py              # [CONTROLLER] Inicializa o Flask, valida requisições e serve rotas
├── model.py                 # [MODEL] Gerencia perfis de prompts invisíveis e chama a API do Gemini
├── templates/               
│   └── index.html           # [VIEW] Estrutura semântica HTML da interface
└── static/                  # [VIEW - Recursos Estáticos]
    ├── css/
    │   └── style.css        # Design System (HSL), dark mode, glassmorphism e skeleton
    └── js/
        └── app.js           # Comunicação AJAX com a API Flask, Marked parser e Prism highlighter
