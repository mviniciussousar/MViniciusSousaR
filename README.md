> # 👨‍💻 Marcos Vinícius

`Automação • Sistemas Internos • Integrações`

Me chamo Marcos Vinícius Sousa, trabalho com **CRM e operação de call center** e construo o software
que a operação usa todo dia: sistemas de gestão de acesso, integrações com as APIs dos discadores e
robôs que fazem o trabalho repetitivo que ninguém deveria estar fazendo à mão. Quase tudo que eu
escrevo nasce de um problema que eu vi acontecendo na mesa ao lado — uma planilha que virou gargalo,
um provisionamento de usuário que levava dias, um relatório montado manualmente toda segunda-feira.
Meu projeto mais autoral é a **Prancheta**, um motor narrativo determinístico e auditável onde a IA
só narra e nunca decide.

![Usuários](https://img.shields.io/badge/USUÁRIOS_GERENCIADOS-300%2B-E63946?style=for-the-badge&labelColor=1a1a1a)
![Unidades](https://img.shields.io/badge/UNIDADES-85-F1A208?style=for-the-badge&labelColor=1a1a1a)
![Automações](https://img.shields.io/badge/AUTOMAÇÕES_AGENDADAS-8%2B-2A9D8F?style=for-the-badge&labelColor=1a1a1a)
![Apps](https://img.shields.io/badge/APPS_EM_PRODUÇÃO-2-4361EE?style=for-the-badge&labelColor=1a1a1a)

---

## 🧰 Linguagens e Tecnologias

[![Tecnologias](https://skillicons.dev/icons?i=ts,js,python,react,nextjs,nodejs,express,prisma,postgres,supabase,tailwind,vercel,cloudflare,githubactions,git,github&perline=16)](https://skillicons.dev)

<div align="center">

![Distribuição por linguagem](https://readme-stats-marvin99.vercel.app/api/top-langs/?username=mviniciussousar&layout=donut&hide_border=true&langs_count=6&locale=pt-br&theme=react&custom_title=Distribui%C3%A7%C3%A3o%20por%20linguagem)

<sub>Medido sobre todos os repositórios, inclusive os privados — que é onde está a maior parte do trabalho.</sub>

</div>

---

## 📌 Projetos

### 🔐 Controle de Acessos CRM `privado`

Sistema web que substituiu a planilha de controle de acessos de **300+ usuários** em 85 unidades e 3
sistemas diferentes. Foi crescendo até virar a central de operação do setor:

- **Provisionamento automático** — criar, alterar, inativar e reativar usuário no app propaga para os
  sistemas externos: por **API REST** em um deles e por **robô Playwright rodando no GitHub Actions**
  no outro, que não tem API. Toda escrita real exige confirmação humana no painel.
- **Coletores agendados** que leem as APIs dos 3 ambientes e reconciliam os cadastros por nome.
- **Monitor de saldo pré-pago** com alerta no próprio app, custo estimado de licenças por perfil e
  painel com o status de todas as automações.

`Next.js` `TypeScript` `PostgreSQL (Neon)` `Playwright` `GitHub Actions` `Vercel`

### 📅 Agendamentos UJVP `privado`

Aplicação de agendamento para uma organização de projetos sociais: formulário público que resolve o
responsável a partir do projeto e **avisa conflito de horário**, mais um painel administrativo com
**RBAC de permissões granulares** (perfis editáveis por área e ação), dark mode e sessões JWT. Passou
por uma auditoria de segurança que rendeu teto de permissões contra escalação de privilégio e
revogação de sessão na troca de senha.

`Next.js` `PostgreSQL` `JWT` `bcrypt`

### 🤖 Automações do discador `privado`

Scripts Python que conversam com a API do discador em **3 ambientes/empresas diferentes** e mantêm
tudo sincronizado com o Google Sheets: status de listas de mailing, relatórios de ligações, de
agentes, de acionamentos e uma verificação recorrente de equipes operando sem lista ativa. Rodam
agendados e reportam o próprio status de volta para o painel do Controle de Acessos.

`Python` `Google Sheets API` `Agendador do Windows`

### 📨 Automação da base de leads `privado`

Automação sem nenhuma dependência externa (só a stdlib do Python) que espera a base chegar por e-mail,
baixa o anexo, divide conforme a regra do dia e repassa por SMTP — com **trava anti-duplicidade** que
consulta a pasta de enviados antes de disparar. Migrou da máquina local para o GitHub Actions, com o
cron calibrado a partir do atraso real medido na fila do runner.

`Python` `IMAP/SMTP` `GitHub Actions`

### 🔗 Link rastreável de RCS → WhatsApp `fora do GitHub`

Cloudflare Worker que faz o redirecionamento 302 instantâneo para o WhatsApp e registra o clique em
segundo plano no Google Sheets, com dashboard próprio. O interessante ficou na parte suja: **6 camadas
anti-bot** — selo assinado no link, filtro de user-agent, país, parâmetros vazios — que nasceram de
cliques-fantasma reais aparecendo na base.

`Cloudflare Workers` `Google Apps Script` `Chart.js`

### ⚽ Prancheta `privado`

Transforma o modo carreira do FIFA 17 em um **RPG narrativo persistente**. A premissa é uma restrição
de arquitetura — *o sistema controla o universo, a IA só narra*. Toda consequência sai de um motor
determinístico e auditável, e qualquer evento na tela responde "por que isso aconteceu?" mostrando a
regra, as entradas e a probabilidade que o geraram. Clean Architecture com regra de dependência
verificada por lint, e migrations testadas contra um Postgres real compilado para WebAssembly.

`Next.js` `TypeScript` `Supabase` `Clean Architecture`

### 🎓 Sistema de Gestão Escolar `privado`

CRUD completo de professores, alunos e horários com validação de conflito, permissões granulares por
perfil e um **ambiente de testes fisicamente isolado** — sandbox em um schema separado do PostgreSQL,
com promoção de registros validados para a produção.

`Node.js` `Express` `Prisma` `React` `TypeScript`

---

## 🧭 Como eu gosto de trabalhar

- **Automação que não depende do meu computador ligado.** O que era tarefa agendada no Windows hoje
  roda no GitHub Actions.
- **Escrita destrutiva sempre com confirmação humana.** Robô que cria e inativa usuário em sistema de
  terceiro roda em *dry-run* primeiro, com screenshot para conferência.
- **Registrar as pegadinhas.** Cada projeto meu tem a lista do que quebrou e por quê — de cache de
  dados congelando leitura a acento corrompido no terminal do Windows.

<sub>💬 Explicações em português, sempre.</sub>
