# Space Prospects

SaaS para encontrar e abordar clientes locais: busca leads de empresas, analisa cada um, gera mensagens de abordagem e sites de apresentação, e organiza tudo num CRM simples.

**Site no ar:** https://spaceprospects.online

> O código-fonte deste projeto é privado, porque é um produto comercial em operação. Este repositório é a vitrine: mostra o que o sistema faz e como foi construído. Posso mostrar partes do código em uma conversa.

<!-- Troque pelos seus prints: crie uma pasta "prints" neste repositório e envie as imagens -->
![Painel](prints/painel.png)
![Leads](prints/leads.png)
![CRM](prints/crm.png)

## O que o sistema faz

- **Busca de leads** por nicho e cidade, com dados de contato e presença online.
- **Análise de cada lead**, apontando pontos fracos (como falta de site) para orientar a abordagem.
- **Mensagens de abordagem geradas por IA**, personalizadas por lead.
- **Gerador de sites** de apresentação para mostrar ao cliente.
- **CRM** com listas, histórico de atividade e bloqueio de contatos.
- **Planos pagos**: assinatura do plano Plus com pagamento por Pix ou cartão e liberação automática.
- **Painel administrativo** com assinantes, vendas e financeiro.

## Tecnologias

| Área | Tecnologia |
| --- | --- |
| Frontend e backend | Next.js 14 (App Router), React 18, TypeScript |
| Estilo | Tailwind CSS |
| Banco, login e arquivos | Supabase (PostgreSQL, Auth, Storage) |
| Pagamentos | InfinitePay (Checkout Integrado) |
| Proteção contra bots | Cloudflare Turnstile |
| Hospedagem | Vercel |

## Decisões técnicas

- **Segurança de dados:** Row Level Security no PostgreSQL, então cada usuário só acessa os próprios dados. Operações privilegiadas rodam só no servidor.
- **Pagamentos confiáveis:** o webhook não é aceito como prova de pagamento. O servidor confere cada transação direto na API, valida o valor e libera o acesso uma única vez, com tentativa automática se algo falhar.
- **Migrações versionadas:** o banco evolui por scripts SQL numerados.
- **Cabeçalhos de segurança** (HSTS, proteção contra clickjacking) e limite de requisições nas rotas sensíveis.

## Contato

**Israel Amaral** · [GitHub](https://github.com/IsraelCodando)
