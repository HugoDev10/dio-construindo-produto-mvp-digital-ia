# 🏷️⚡ GarimpoClub ⚡🏷️

Desafio DIO (Junto com Santander) MeuNegócio.AI: Construindo um Produto Digital com Agentes de IA e Lovable.

> Marketplace mobile-first de curadoria de ofertas e grupos VIP de WhatsApp para compradores que buscam descontos reais em eletrônicos, games, informática, esportes e infantil.

---

## 1. A Dor Escolhida e Por Que Ela Vale um Negócio

### A Dor
* **Compradores perdem descontos relâmpago**: Ofertas reais em grandes marketplaces (Amazon, Mercado Livre, Shopee) duram poucos minutos ou acabam por ruptura de estoque. Grupos de WhatsApp e canais de Telegram costumam ser desorganizados, cheios de spam, links quebrados e ofertas falsas ("metade do dobro").
* **Curadores e afiliados não conseguem escalar**: Administradores de grupos de ofertas gastam horas garimpando promoções manualmente, perdem histórico e não contam com uma vitrine centralizada nem relatórios de cliques e comissões transparentes.

### Por que vale um negócio?
1. **Intenção de compra imediata**: O usuário que navega atrás de ofertas já está na fase final de decisão de compra; a taxa de conversão é expressivamente superior à de redes sociais generalistas.
2. **Monetização em duas pontas**: Comissão por cliques/conversões de afiliados (Amazon Associates, Shopee Affiliates, Mercado Livre Afiliados) + taxa de intermediação/destaque de grupos parceiros.
3. **Efeito de rede**: Quanto mais parceiros trazem ofertas reais e auditadas, mais compradores entram nos grupos e utilizam o app como ponto de partida diário.

---

## 2. O Tamanho de Mercado e o Business Model Canvas

### Tamanho de Mercado
* **TAM (Total Addressable Market)**: Mercado de e-commerce brasileiro (R$ 185+ bilhões/ano), com penetração móvel acima de 70%.
* **SAM (Serviceable Available Market)**: Compras originadas por marketing de afiliados e social commerce no Brasil (estimado em R$ 12 a 15 bilhões/ano).
* **SOM (Serviceable Obtainable Market)**: Nichos de alta recorrência e tíquete médio atrativo (Eletrônicos, Games, Informática, Esportes e Infantil) intermediados por comunidades de WhatsApp.

### Business Model Canvas (BMC)

| Bloco | Detalhes no GarimpoClub |
| :--- | :--- |
| **Proposta de Valor** | **Compradores**: Ofertas auditadas de lojas confiáveis, histórico de preço e grupos VIP sem spam.<br>**Parceiros**: Vitrine unificada para suas ofertas, rastreamento de cliques, relatórios de audiência e solicitação de saques. |
| **Segmentos de Clientes** | 1. Consumidores caçadores de ofertas e gamers em busca de hardware/acessórios.<br>2. Criadores de conteúdo, canais de descontos e afiliados profissionais. |
| **Canais** | PWA/Web App responsivo, grupos de WhatsApp, notificações push/web e indicação orgânica. |
| **Relacionamento** | Autosserviço, experiência mobile-first com estética premium (preto, branco e dourado), curadoria estrita e suporte via comunidade. |
| **Fontes de Receita** | 1. Comissões de afiliados das lojas parceiras (Amazon, Mercado Livre, Shopee).<br>2. Assinatura de destaque para grupos parceiros.<br>3. Taxa operacional sobre o volume transacionado em saques de parceiros. |
| **Recursos-Chave** | Plataforma Lovable Cloud (PostgreSQL + Auth + Storage), catálogo de ofertas em tempo real, links de afiliação e regras de validação. |
| **Atividades-Chave** | Curadoria diária, validação de preços, moderação e aprovação de grupos/parceiros e prevenção a links fraudulentos. |
| **Parcerias-Chave** | Programas de afiliados (Amazon, Shopee, Mercado Livre) e administradores de grupos/influenciadores de nicho. |
| **Estrutura de Custos** | Hospedagem serverless (Cloudflare Workers/Edge), banco de dados/autenticação Lovable Cloud e custos de marketing/aquisição de usuários. |

---

## 3. A Tese que o MVP Testa e o que Ficou Manual de Propósito

### Tese do MVP
> *"Compradores confiam mais e convertem mais rápido quando encontram uma vitrine filtrada e categorizada que os direciona para grupos focados de WhatsApp, gerando engajamento e cliques comissionados para parceiros."*

### O que ficou manual de propósito
* **Aprovação de Parceiros e Grupos**: Administradores aprovam ou rejeitam novos grupos manualmente pelo painel (`/admin`) para garantir que nenhum grupo com links suspeitos ou regras abusivas entre na vitrine.
* **Liberação de Saques de Comissões**: O parceiro solicita o saque no painel (`/parceiro`), mas a conciliação financeira com as redes de afiliados e a transferência via Pix permanecem manuais no painel do administrador antes de marcar como "Pago".
* **Cadastro das Melhores Ofertas**: Embora a estrutura suporte automações e web scraping, o cadastro manual incentiva curadoria humana refinada (destaque de cupons, valor à vista e selo de desconto real).

---

## 4. O Mega Prompt e as Correções Posteriores

### Mega Prompt Inicial
* **Objetivo**: Criar o MVP completo do GarimpoClub em tema escuro premium (preto, branco e dourado), mobile-first, com regras rígidas de negócios (apenas lojas permitidas: Amazon, Mercado Livre e Shopee; 5 categorias centrais).
* **Entregáveis gerados**: Catálogo de ofertas, páginas de grupos de WhatsApp, favoritos, perfil do usuário, central do parceiro com métricas de cliques e painel de administração.

PRD (Product requirement document) refinado no Copilot Web:

```markdown
Crie um MVP completo chamado "GarimpoClub", um marketplace de grupos de ofertas focado exclusivamente em WhatsApp. O sistema deve possuir 3 perfis: Cliente, Dono de Grupo e Administrador. Utilize design moderno, responsivo, aparência premium, cores preto, branco e amarelo/dourado, com foco em conversão.

CLIENTE:
- Cadastro e login (e-mail, senha e Google).
- Escolha de categorias de interesse: Eletrônicos, Games, Informática, Esportes e Infantil.
- Feed principal de ofertas com card contendo imagem, título, loja, preço original, preço promocional, percentual de desconto e botão "Ver Oferta".
- Área para explorar grupos.
- Participar de grupos via link do WhatsApp.
- Favoritar ofertas.
- Perfil do usuário.
- Notificações de novas ofertas.

DONO DE GRUPO:
- Cadastro como parceiro.
- Cadastro de grupo com nome, descrição, categoria, imagem e link do WhatsApp.
- Dashboard com total de cliques, visualizações, membros enviados para o WhatsApp e ganhos.
- Publicação de ofertas com imagem, título, descrição, loja, preço original, preço promocional e link.
- Relatórios simples de desempenho.
- Área financeira com saldo e solicitação de saque via PIX.

ADMIN GARIMPOCLUB:
- Dashboard com KPIs gerais.
- Gestão de usuários.
- Gestão de grupos.
- Aprovação/rejeição de grupos.
- Gestão de ofertas.
- Controle financeiro.
- Envio de notificações push.

LOJAS PERMITIDAS:
- Amazon
- Mercado Livre
- Shopee

BANCO DE DADOS:
Users, Groups, Offers, Favorites, UserGroups, Commissions e Withdrawals com relacionamento completo.

TECNOLOGIA:
- Front-end em React + TypeScript + Tailwind.
- Backend preparado para Supabase.
- Autenticação via Supabase Auth.
- Banco PostgreSQL.
- Upload de imagens.
- Estrutura pronta para escalabilidade.

GERAR:
- Todas as telas.
- Rotas.
- Componentes reutilizáveis.
- Layout mobile-first.
- Dashboard administrativo.
- Dashboard do parceiro.
- Dados mockados para demonstração.
- Navegação funcional entre páginas.
- Estrutura completa de SaaS pronta para evolução para produção.
```



### Principais Correções e Evoluções
* **Migração para Banco Real (Lovable Cloud)**:
  * Substituição do protótipo inicial com mock/localStorage por PostgreSQL com Row Level Security (RLS) completo.
  * Autenticação real com e-mail/senha e Google OAuth.
  * RPCs seguras (`security definer`) para registrar cliques, comissões de parceiros e solicitações de saque sem risco de manipulação no frontend.
  * Armazenamento de fotos em bucket privado com links assinados seguros.
* **Ajuste de Tipografia e Legibilidade**:
  * Substituição da fonte de títulos anterior por **Sora** para melhorar a legibilidade em telas móveis e manter a identidade visual premium.
* **Validação de Regras de Negócio**:
  * Funções puras em `src/lib/garimpo.ts` com testes automatizados em Vitest garantindo descontos válidos, cálculo de comissões e rejeição de domínios não autorizados.

---

## 5. Endereço da Aplicação e Evidências

* **URL**: https://garimpoclubhub.lovable.app/



### Tela Inicial (Home)
![Tela Inicial](https://github.com/user-attachments/assets/a309a21c-c3f3-4b5b-be67-7ce920e5ace6)
> **Rota (`/`)**: Porta de entrada da plataforma com design mobile-first e identidade visual premium (preto, branco e dourado). Apresenta banner principal com proposta de valor, carrossel de categorias de produtos (Eletrônicos, Games, Informática, Esportes e Infantil), campo de busca rápida e vitrine de promoções em destaque com selos de desconto, loja de origem e acesso rápido aos grupos VIP.

---

### Autenticação e Cadastro
![Tela de Criação de Conta](https://github.com/user-attachments/assets/e766c8d2-d407-417f-a54d-aebf0040f970)
> **Rota (`/entrar`)**: Fluxo unificado de acesso integrado ao backend na nuvem. Oferece autenticação social com Google ou cadastro por e-mail e senha com validação em tempo real, além de permitir a definição do perfil inicial de uso (comprador ou criador de comunidade parceiro).

---

### Perfil do Administrador
![Perfil do Administrador](https://github.com/user-attachments/assets/d0999aa4-56c8-4876-b46f-d564fc0c0e07)
> **Rota (`/perfil`)**: Visão da conta com privilégios de gestão master da plataforma. Exibe badge de perfil de Administrador, atalho para o painel de moderação (`/admin`), configurações de conta e central de avisos e notificações do sistema.

---

### Dashboard do Administrador
![Dashboard do Administrador](https://github.com/user-attachments/assets/331956d4-b69e-4e43-8629-5bbe9bf9ec3b)
> **Rota (`/admin`)**: Hub central de moderação e auditoria. Apresenta métricas operacionais consolidadas, fila de aprovação e rejeição de novos grupos de WhatsApp submetidos e moderação de pedidos de saque financeiro de comissões via RPC protegida.

---

### Perfil do Dono de Grupos (Parceiro)
![Perfil do Parceiro](https://github.com/user-attachments/assets/7dd801cb-9fa5-4648-8239-a8587dc4a68f)
> **Rota (`/perfil`)**: Perfil dedicado aos gestores de comunidades monetizadas. Identificado com o selo de Parceiro, provê atalho rápido para o painel analítico (`/parceiro`), histórico de notificações e edição de dados cadastrais.

---

### Painel do Dono de Grupo (Dashboard do Parceiro)
![Painel do Dono de Grupo](https://github.com/user-attachments/assets/c59ce07b-9822-4ddd-921c-01bec1aba044)
> **Rota (`/parceiro`)**: Área de acompanhamento de performance e ganhos. Exibe gráfico semanal de cliques gerados, saldo acumulado por redirecionamentos válidos, solicitação de saque de comissões via Pix e controle de status de aprovação dos grupos cadastrados.

---

### Perfil do Cliente Comum
![Perfil do Cliente](https://github.com/user-attachments/assets/6743aab6-2f8f-4c2e-a361-e6187b16ed7a)
> **Rota (`/perfil`)**: Painel de personalização para o consumidor. Permite selecionar categorias de interesse para notificações direcionadas, consultar ofertas salvas nos favoritos e solicitar upgrade gratuito para conta de parceiro em um clique.

---

### Catálogo de Grupos VIP (Visão do Cliente)
![Catálogo de Grupos](https://github.com/user-attachments/assets/f573e133-c57a-430d-95b0-604d068aea0b)
> **Rota (`/grupos`)**: Diretório de comunidades curadas com filtros por nicho e lojas foco. Cada card apresenta imagem do grupo, contagem de membros ativos, regras do canal e botão de entrada direta no grupo de WhatsApp.

---

## 💡 Reflexão Final

### O Que Foi Construído
O **GarimpoClub** nasceu para resolver uma dor concreta do e-commerce brasileiro: o ruído e a perda de ofertas relâmpago causados pela fragmentação dos grupos de mensagens. Em vez de criar mais um canal caótico de links, o projeto entrega uma **ponte organizada entre compradores e comunidades de curadores profissionais**.

O ciclo completo de um marketplace de nicho foi validado de ponta a ponta:
1. **Compradores** encontram promoções reais filtradas por categoria (Eletrônicos, Games, Informática, Esportes e Infantil) e ingressam nos grupos certos sem spam.
2. **Criadores de grupos** ganham uma vitrine qualificada para expandir suas audiências e um painel transparente para acompanhar cliques e solicitar saques de comissões.
3. **Administradores** mantêm o controle de qualidade por meio de uma fila de aprovação de comunidades e auditoria financeira centralizada.

---

### Aprendizados Técnicos e de Arquitetura

- **Segurança em Primeiro Lugar no Backend**: Operações sensíveis — como cálculo de saldo, registro de cliques comissionados e solicitação de saques — nunca confiam no cliente web. Foram isoladas em funções com privilégios restritos no banco de dados (`SECURITY DEFINER RPCs`) e protegidas por políticas de Row-Level Security (RLS), impedindo adulterações de valores ou papéis.
- **Armazenamento Responsável de Mídia**: O upload de imagens e logotipos utiliza pastas privadas vinculadas ao identificador do usuário (`userId`), gerando links de acesso assinado de longa duração e garantindo isolamento total entre os criadores de conteúdo.
- **Regras de Negócio Puras e Testadas**: O cálculo de descontos, a validação de lojas permitidas (Amazon, Mercado Livre e Shopee) e os critérios de elegibilidade para saque foram desacoplados em funções puras, cobertas por testes automatizados (`vitest`), o que acelera manutenções futuras sem risco de regressão.
- **Design Mobile-First Orientado à Conversão**: A paleta sóbria (preto, branco e dourado) combinada a tipografia otimizada confere um aspecto premium, essencial para gerar a credibilidade necessária em um produto que lida com dinheiro, links de afiliados e dados bancários Pix.

---

### Impacto e Viabilidade de Negócio
O GarimpoClub ataca um mercado de alta fricção com **custo operacional mínimo**:
- Não há gestão de estoque físico nem intermediação de pagamento do produto final: toda transação ocorre nos marketplaces parceiros.
- A monetização por comissão de cliques e afiliação cria um alinhamento direto de incentivos: o parceiro ganha conforme entrega tráfego qualificado, e a plataforma escala no modelo de comissão compartilhada.
- O efeito de rede é intrínseco: cada novo parceiro atrai novos compradores, e a base crescente de compradores atrai curadores mais especializados.

---

> *"O melhor garimpo não é o que tem mais links, mas aquele que entrega o melhor preço no momento exato em que o comprador está pronto para comprar."*










