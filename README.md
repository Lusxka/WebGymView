WebGym: Seu Treinador de Fitness Digital Pessoal
WebGym é um treinador de fitness digital pessoal que usa inteligência artificial para ajudar você a atingir seus objetivos de saúde. A aplicação permite que você faça login com segurança, crie um perfil detalhado e, em seguida, a IA gera planos semanais de treino e dieta personalizados. Você pode acompanhar seu progresso diário e alternar entre os modos escuro e claro para uma experiência mais confortável.

✨ Recursos Principais
🔐 Autenticação e Autorização: Registre-se e faça login com segurança. Apenas usuários autenticados podem acessar seus dados e painéis privados.

🤖 Planos com IA: Após um breve onboarding, a IA, com a tecnologia do Google Gemini, gera instantaneamente um plano de treino e dieta semanal personalizado com base nos seus dados e objetivos.

🧙‍♂️ Assistente de Onboarding: Um formulário interativo de várias etapas que coleta informações essenciais de forma simples e intuitiva.

💾 Persistência de Dados: Todos os seus dados — perfil, planos e progresso — são armazenados de forma segura em um banco de dados Supabase, acessíveis a qualquer momento.

📈 Painel e Interface de Abas: Uma interface organizada que serve como seu centro de comando de fitness. Navegue facilmente entre seu painel, planos, dieta e configurações.

🌐 Estado Global da Aplicação: A aplicação mantém um "quadro branco central" dos seus dados, garantindo que as alterações sejam instantaneamente refletidas em toda a interface.

🎨 Gerenciamento de Tema: Personalize a sua experiência alternando entre o modo claro e o modo escuro com um único clique. A sua preferência é salva e lembrada.

🏗️ Arquitetura Técnica
O WebGym foi construído com uma arquitetura moderna, projetada para ser escalável e de alto desempenho. A aplicação é composta por alguns sistemas-chave que trabalham em conjunto.

flowchart TD
    A0["User Authentication & Authorization
"]
    A1["Global Application State
"]
    A2["AI-Powered Plan Generation (Supabase Edge Function)
"]
    A3["User Profile Onboarding Wizard
"]
    A4["Data Persistence (Supabase Client)
"]
    A5["Dashboard & Tabbed UI
"]
    A6["Theme Management (Dark/Light Mode)
"]
    A0 -- "Authenticates via" --> A4
    A0 -- "Populates user session" --> A1
    A3 -- "Submits profile for AI" --> A2
    A2 -- "Stores generated plans" --> A4
    A3 -- "Stores user profile" --> A4
    A4 -- "Provides app data to" --> A1
    A1 -- "Displays data on" --> A5
    A1 -- "Controls theme" --> A6
    A5 -- "Initiates onboarding" --> A3

Componentes Principais
Supabase Client (src/supabase.ts): A biblioteca principal para a interação segura da nossa aplicação com o banco de dados Supabase.

Supabase Edge Functions (supabase/functions/): Um ambiente seguro e sem servidor para a nossa lógica de IA. Quando você completa o seu perfil, a função generate-workout é acionada para se comunicar com a IA do Google Gemini.

React Context API (src/context/): Usamos dois contextos para gerenciar o estado da aplicação: AuthContext para a sessão do usuário e AppContext como o hub de dados central.

React Router (react-router-dom): Gerencia a navegação da aplicação, com o componente ProtectedRoute a garantir que apenas usuários autenticados possam aceder a certas páginas.

Tailwind CSS: O framework CSS que permite a troca de tema (modo claro/escuro) ao adicionar ou remover a classe dark da tag <html>.

🚀 Como Começar
Para executar o WebGym localmente, siga os passos abaixo para configurar o seu projeto Supabase e as variáveis de ambiente necessárias.

1. Clonar o Repositório
git clone [https://github.com/seu-usuario/webgym.git](https://github.com/seu-usuario/webgym.git)
cd webgym

2. Configurar o Supabase
Crie um novo projeto no Supabase e configure as tabelas do banco de dados (usuarios, planos_treino, exercicios_treino, etc.), bem como a Edge Function.

3. Configurar Variáveis de Ambiente
Crie um arquivo .env.local na raiz do seu projeto com as suas chaves Supabase.

VITE_SUPABASE_URL="[Sua URL Supabase]"
VITE_SUPABASE_ANON_KEY="[Sua chave pública Supabase]"

As chaves para o serviço de IA e outros segredos da Edge Function são gerenciados separadamente.

4. Instalar as Dependências
npm install

5. Executar a Aplicação
npm run dev

A aplicação estará disponível em http://localhost:5173.
