# 🏋️‍♂️ WebGym
### *Seu Treinador de Fitness Digital Pessoal powered by AI*

<div align="center">

![WebGym Banner](https://via.placeholder.com/800x200/6366f1/ffffff?text=WebGym+🏋️‍♂️)

[![Stars](https://img.shields.io/github/stars/Lusxka/WebGymView?style=for-the-badge&logo=github&color=6366f1)](https://github.com/Lusxka/WebGymView/stargazers)
[![Forks](https://img.shields.io/github/forks/Lusxka/WebGymView?style=for-the-badge&logo=github&color=8b5cf6)](https://github.com/Lusxka/WebGymView/network)
[![Issues](https://img.shields.io/github/issues/Lusxka/WebGymView?style=for-the-badge&logo=github&color=06d6a0)](https://github.com/Lusxka/WebGymView/issues)
[![License](https://img.shields.io/github/license/Lusxka/WebGymView?style=for-the-badge&color=f59e0b)](LICENSE)

**[🚀 Demo ao Vivo](https://webgym-demo.vercel.app)** • **[📚 Documentação](https://docs.webgym.app)** • **[🐛 Reportar Bug](https://github.com/Lusxka/WebGymView/issues)**

</div>

---

## 🌟 **Sobre o Projeto**

WebGym é um **treinador de fitness digital pessoal** que usa **inteligência artificial** para ajudar você a atingir seus objetivos de saúde. A aplicação permite que você faça login com segurança, crie um perfil detalhado e, em seguida, a IA gera planos semanais de treino e dieta personalizados. Você pode acompanhar seu progresso diário e alternar entre os modos escuro e claro para uma experiência mais confortável.

<div align="center">

```ascii
    🤖 IA Personalizada    📊 Tracking Completo    🔒 100% Seguro
         ↓                        ↓                     ↓
    Planos Únicos         Progresso Visual      Dados Protegidos
```

</div>

---

## ✨ **Recursos Principais**

<table>
<tr>
<td width="50%">

### 🔐 **Autenticação & Segurança**
- ✅ Registro e login seguro
- ✅ JWT tokens para proteção
- ✅ Dados criptografados
- ✅ Acesso apenas para usuários autenticados

### 🤖 **IA Personalizada**
- ✅ Powered by **Google Gemini**
- ✅ Planos de treino únicos
- ✅ Dietas personalizadas
- ✅ Adaptação baseada em progresso

### 💾 **Persistência Total**
- ✅ Database Supabase
- ✅ Sincronização em tempo real
- ✅ Backup automático
- ✅ Acesso multi-dispositivo

</td>
<td width="50%">

### 🧙‍♂️ **Onboarding Intuitivo**
- ✅ Formulário multi-etapas
- ✅ Coleta de dados inteligente
- ✅ UI/UX otimizada
- ✅ Experiência guiada

### 📈 **Dashboard Completo**
- ✅ Interface de abas organizada
- ✅ Centro de comando fitness
- ✅ Navegação intuitiva
- ✅ Métricas em tempo real

### 🎨 **Experiência Premium**
- ✅ Modo claro/escuro
- ✅ Design responsivo
- ✅ Animações fluidas
- ✅ Preferências salvas

</td>
</tr>
</table>

---

## 🛠️ **Stack Tecnológica**

<div align="center">

### **Frontend**
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-B73BFE?style=for-the-badge&logo=vite&logoColor=FFD62E)

### **Backend & IA**
![Supabase](https://img.shields.io/badge/Supabase-181818?style=for-the-badge&logo=supabase&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)

### **Deploy & Tools**
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
![ESLint](https://img.shields.io/badge/eslint-3A33D1?style=for-the-badge&logo=eslint&logoColor=white)

</div>

---

## 🏗️ **Arquitetura do Sistema**

```mermaid
graph TB
    A[👤 Usuário] --> B[🖥️ React Frontend]
    B --> C[🔐 Auth Layer]
    C --> D[🧠 AI Engine - Gemini]
    C --> E[💾 Supabase DB]
    
    D --> F[📋 Plano de Treino]
    D --> G[🥗 Plano de Dieta]
    
    E --> H[👤 Perfil do Usuário]
    E --> I[📊 Dados de Progresso]
    E --> J[⚙️ Configurações]
    
    F --> K[📈 Dashboard]
    G --> K
    H --> K
    I --> K
    J --> K
    
    style A fill:#6366f1,stroke:#4f46e5,color:#fff
    style D fill:#06d6a0,stroke:#059669,color:#fff
    style E fill:#8b5cf6,stroke:#7c3aed,color:#fff
    style K fill:#f59e0b,stroke:#d97706,color:#fff
```

---

## 🚀 **Começando**

### **Pré-requisitos**
```bash
Node.js >= 18.0.0
npm >= 9.0.0
```

### **Instalação Rápida**

```bash
# 1️⃣ Clone o repositório
git clone https://github.com/Lusxka/WebGymView.git

# 2️⃣ Navegue até a pasta
cd WebGymView

# 3️⃣ Instale as dependências
npm install

# 4️⃣ Configure as variáveis de ambiente
cp .env.example .env.local
# Edite o arquivo .env.local com suas chaves

# 5️⃣ Execute o projeto
npm run dev
```

### **Variáveis de Ambiente**

```env
# Supabase
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_key

# Google Gemini AI
VITE_GEMINI_API_KEY=your_gemini_key

# App Settings
VITE_APP_URL=http://localhost:3000
```

---

## 📸 **Screenshots**

<div align="center">

### 🌙 **Modo Escuro**
![Dark Mode](https://via.placeholder.com/800x450/1e293b/f1f5f9?text=WebGym+Dark+Mode+🌙)

### ☀️ **Modo Claro**
![Light Mode](https://via.placeholder.com/800x450/f8fafc/1e293b?text=WebGym+Light+Mode+☀️)

### 📱 **Responsivo**
<img src="https://via.placeholder.com/300x600/6366f1/ffffff?text=Mobile+View+📱" width="250">

</div>

---

## 🎯 **Roadmap**

- [x] **Fase 1**: Autenticação e perfil básico
- [x] **Fase 2**: Integração com IA para planos
- [x] **Fase 3**: Dashboard e tracking
- [x] **Fase 4**: Modo escuro/claro
- [ ] **Fase 5**: Integração com wearables 📱
- [ ] **Fase 6**: Comunidade e social 👥
- [ ] **Fase 7**: App mobile nativo 📲
- [ ] **Fase 8**: Planos premium 💎

---

## 🤝 **Contribuindo**

Contribuições são **sempre bem-vindas**! Veja o arquivo [CONTRIBUTING.md](CONTRIBUTING.md) para detalhes.

### **Como Contribuir**

1. 🍴 **Fork** o projeto
2. 🌿 Crie uma **branch** para sua feature (`git checkout -b feature/AmazingFeature`)
3. ✅ **Commit** suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. 📤 **Push** para a branch (`git push origin feature/AmazingFeature`)
5. 🔄 Abra um **Pull Request**

---

## 📝 **Licença**

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

---

## 💬 **Contato & Suporte**

<div align="center">

**Lusxka** - Desenvolvedor Principal

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Lusxka)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/lusxka)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:lusxka@email.com)

---

### 💪 **Construído com paixão por fitness e tecnologia**

**Se este projeto te ajudou, considere dar uma ⭐!**

</div>

---

<div align="center">
<sub>🏋️‍♂️ WebGym - Transforme sua jornada fitness com IA personalizada • 2024</sub>
</div>
