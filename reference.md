# Ultra SEO/GEO — Referência Técnica

Material de apoio para a skill `ultra-seo-geo`. Consulte quando precisar recomendar schema, checklist técnico, funções de site, HTML amigável para agentes de IA ou robots.txt para crawlers de IA.

## Dados Estruturados Essenciais (JSON-LD)

Use JSON-LD sempre que fizer sentido. O markup precisa corresponder ao conteúdo visível da página.

| Tipo de página | Schema recomendado |
|---|---|
| Blog post / notícia / guia | `Article` ou `BlogPosting` |
| Página institucional | `Organization` |
| Negócio local | `LocalBusiness` |
| Página de serviço | `Service` |
| Produto / pacote / oferta | `Product`, `Offer` |
| Turismo / hospedagem | `LodgingBusiness`, `Hotel`, `VacationRental`, quando aplicável |
| FAQ | `FAQPage`, quando o conteúdo visível realmente contém perguntas e respostas |
| Página de pergunta e resposta | `QAPage` |
| Navegação | `BreadcrumbList` |
| Vídeos | `VideoObject` |
| Imagens | `ImageObject` ou metadados de imagem |

## Checklist Técnico Mínimo

```
[ ] Site rápido e responsivo
[ ] HTML semântico
[ ] Conteúdo principal renderizado no HTML ou facilmente processável
[ ] Status HTTP 200 nas páginas indexáveis
[ ] Sitemap.xml atualizado
[ ] Robots.txt sem bloquear páginas importantes
[ ] Canonical correto
[ ] Redirecionamentos 301 corretos
[ ] Imagens WebP/AVIF otimizadas
[ ] Lazy loading sem quebrar indexação
[ ] Core Web Vitals aceitável
[ ] Schema JSON-LD válido
[ ] Páginas com conteúdo único
[ ] Evitar thin content
[ ] Evitar duplicação por tags, filtros e parâmetros
[ ] Página 404 útil
[ ] Página de contato, política e sobre
```

Para sites com JavaScript, o cuidado precisa ser maior: Google consegue processar JS, mas SEO em frameworks JavaScript é mais complexo quando conteúdo, links ou metadados importantes dependem demais de renderização tardia.

## Funções que um Site/Blog Deveria Ter

| Função | Por que importa |
|---|---|
| Busca interna | Ajuda usuário e revela intenção real de pesquisa |
| Índice no artigo | Melhora navegação e leitura rápida |
| Breadcrumbs | Melhora UX e entendimento estrutural |
| Posts relacionados | Fortalece cluster e reduz abandono |
| Filtros por categoria/tag | Ajuda blogs grandes e hubs de conteúdo |
| Autor visível | Reforça confiança e E-E-A-T |
| Data de publicação e atualização | Importante para conteúdo fresco |
| FAQ modular | Captura perguntas conversacionais |
| Tabelas comparativas | Excelente para snippets e respostas de IA |
| CTA contextual | Converte sem depender só do final da página |
| Formulários rastreáveis | Permite medir conversão orgânica |
| WhatsApp com UTM | Essencial para negócios que vendem por conversa |
| Schema automático | Escala SEO técnico sem depender de edição manual |
| Sitemap automático | Facilita rastreamento |
| Robots.txt bem configurado | Controla acesso de buscadores e bots |
| Analytics + Search Console + Bing Webmaster | Mede tráfego, indexação e visibilidade em IA |

O Search Console possui relatórios dedicados de desempenho de IA generativa (impressões, páginas, países, dispositivos e datas relacionados a AI Overviews, AI Mode e Discover generativo). O Bing Webmaster possui relatórios de AI Performance com páginas citadas, consultas de grounding, intenção, tópicos, citation share e comparação.

## Estrutura Amigável para Agentes de IA

Agentes de IA não navegam como humanos: interpretam screenshots, HTML bruto e árvore de acessibilidade. Sites com botões falsos em `div`, formulários sem labels, menus confusos, popups agressivos e layout que depende só de efeito visual tendem a ser piores para agentes.

```
[ ] Usar <button> para botões reais
[ ] Usar <a> para links reais
[ ] Usar <label> em formulários
[ ] Nomear campos claramente
[ ] Evitar CTA só em imagem
[ ] Evitar conteúdo importante preso em carrossel
[ ] Não esconder informações comerciais essenciais
[ ] Manter texto, imagem e dados estruturados coerentes
[ ] Usar aria-label quando necessário
[ ] Garantir navegação por teclado
```

Isso ajuda acessibilidade, UX, SEO técnico e navegação por agentes.

## Robots.txt e Crawlers de IA

Para aparecer em buscadores com IA, decida quais bots permitir. OpenAI documenta crawlers como `OAI-SearchBot` e `GPTBot`, controláveis por robots.txt. Perplexity documenta `PerplexityBot` (exibição e link de sites em resultados de busca) e `Perplexity-User` (ações iniciadas por usuários).

Abertura genérica para indexação tradicional e IA de busca:

```
User-agent: *
Allow: /

Sitemap: https://www.seusite.com/sitemap.xml
```

Permitindo bots específicos de busca por IA:

```
User-agent: OAI-SearchBot
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: GPTBot
Allow: /
```

Cuidado: permitir bot de busca, bot de treinamento e agente de usuário não é a mesma coisa. Cada empresa separa esses usos de forma diferente. Confirme a política desejada com o usuário antes de liberar bots de treinamento.
