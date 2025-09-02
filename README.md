WebGym: Seu Treinador de Fitness Digital PessoalWebGym é um treinador de fitness digital pessoal com inteligência artificial que ajuda os usuários a atingir suas metas de saúde. A aplicação permite que você faça login com segurança, crie um perfil pessoal detalhado, e então a IA gera planos semanais de treino e dieta personalizados para você. Você pode acompanhar seu progresso diário e alternar entre os modos escuro e claro para uma experiência confortável.✨ RecursosAutenticação e Autorização do Usuário: Registre-se e faça login com segurança. O aplicativo atua como um "segurança" que garante que apenas usuários autenticados possam acessar seus dados e painéis privados.Geração de Plano com IA: Após o assistente de onboarding, a IA, alimentada pelo Google Gemini, gera instantaneamente um plano semanal de treino e dieta personalizado, com base nos seus dados e metas exclusivos.Assistente de Onboarding de Perfil: Um formulário interativo de várias etapas que coleta informações pessoais, físicas e de saúde essenciais de maneira estruturada.Persistência de Dados: Todos os seus dados importantes, incluindo seu perfil, planos e registros de progresso, são armazenados de forma segura em um banco de dados Supabase para que estejam sempre disponíveis quando você fizer login. O Supabase Client é a principal interface para interagir com esses dados.Painel e Interface de Abas: Uma interface organizada que serve como seu centro de comando de fitness. Navegue facilmente entre seu painel principal, planos de treino e dieta, e configurações usando um menu de navegação lateral.Estado Global da Aplicação: O aplicativo mantém um "quadro branco central" dos seus dados, garantindo que as alterações (como marcar um exercício como concluído) sejam instantaneamente refletidas em todo o aplicativo para uma experiência fluida.Gerenciamento de Tema: Personalize sua experiência alternando entre o modo claro e o modo escuro com um único clique. Sua preferência é salva e lembrada para a próxima visita.🏗️ Arquitetura TécnicaO WebGym é construído com uma arquitetura moderna, projetada para escalabilidade e desempenho. A aplicação é composta por alguns sistemas chave que trabalham juntos para entregar o produto final.flowchart TD
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

Componentes PrincipaisSupabase Client (src/supabase.ts): Esta biblioteca é a principal interface para o nosso aplicativo interagir com o banco de dados Supabase. Ela gerencia operações de dados seguras como insert, select, update e upsert.Supabase Edge Functions (supabase/functions/): É um ambiente seguro e sem servidor para nossa lógica de IA. Quando um usuário completa seu perfil, o aplicativo envia uma solicitação para a função generate-workout. Esta função então envia os dados do usuário para a IA Google Gemini, recebe o plano gerado e o salva no banco de dados.React Context API (src/context/): Usamos dois contextos principais:AuthContext: Gerencia a sessão e o status de login do usuário (user, session, loading).AppContext: O hub de dados central para o aplicativo. Ele armazena o perfil do usuário, planos de treino, dados de dieta e outras informações dinâmicas.React Router (react-router-dom): Esta biblioteca gerencia a navegação e as rotas do aplicativo. O componente ProtectedRoute é uma parte fundamental desse sistema, garantindo que páginas como o painel só possam ser acessadas por usuários autenticados.Tailwind CSS: Um framework CSS que usa a configuração darkMode: 'class', permitindo uma troca de tema suave ao simplesmente adicionar ou remover uma classe dark na tag <html> principal do documento.🚀 Como ComeçarPara rodar o WebGym localmente, você precisará configurar um projeto Supabase e as variáveis de ambiente necessárias.Clone o repositório:git clone [https://github.com/seu-usuario/webgym.git](https://github.com/seu-usuario/webgym.git)
cd webgym

Configure o Supabase:Vá para o Supabase e crie um novo projeto.Você precisará configurar suas tabelas de banco de dados (usuarios, planos_treino, exercicios_treino, etc.) e a Edge Function.Configure as variáveis de ambiente:Crie um arquivo .env.local na raiz do seu projeto.Obtenha a URL e a chave anon do seu projeto nas configurações de API e adicione-as ao arquivo:VITE_SUPABASE_URL="[Sua URL Supabase]"
VITE_SUPABASE_ANON_KEY="[Sua chave pública Supabase]"

Você também precisará configurar seu serviço de IA e outros segredos para a Edge Function, que são armazenados em um arquivo diferente e seguro.Instale as dependências:npm install

Execute a aplicação:npm run dev

A aplicação estará disponível em http://localhost:5173.
