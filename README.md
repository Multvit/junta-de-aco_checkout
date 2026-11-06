# Junta de Aço · Landing page

Landing page de produto do **Junta de Aço (um produto Multvit)**. Site estático (HTML + CSS + JS, sem build), pronto para a Vercel.
Usa a mesma base visual da landing do Fiber SE7E, com a paleta própria do Junta de Aço (violeta do rótulo + amarelo Multvit).

## Estrutura

```
index.html                  página
politica-privacidade.html   política de privacidade (texto do site antigo)
termos-de-uso.html          termos de uso (texto do site antigo)
assets/css/style.css        estilos (tokens de cor no topo)
assets/js/main.js           interações, motion, chat e tracking (CONFIG no topo)
assets/vendor/motion.min.js Motion (motion.dev) 11.11.17, servido localmente
assets/fonts/               Bricolage Grotesque (títulos) e Figtree (texto), woff2 latin
assets/img/                 imagens otimizadas (WebP), logos, favicon, og-image
assets/img/original/        imagens originais recebidas
```

## Onde alterar

Tudo no topo de `assets/js/main.js`:

| Item | Chave |
|---|---|
| Links de checkout (3, 6 e 12 meses) | `CONFIG.checkout` |
| WhatsApp e mensagem inicial | `CONFIG.whatsapp` |
| Assistente virtual “João” (n8n). `""` desliga e volta o botão flutuante do WhatsApp | `CONFIG.chatN8n` |
| Meta Pixel (PageView, Contact, InitiateCheckout, ViewContent) | `CONFIG.metaPixelId` |
| Microsoft Clarity | `CONFIG.clarityId` |

Preços, textos, FAQ e os vídeos de depoimento (atributo `data-yt` com o ID do YouTube) ficam em `index.html`.

## Rodar localmente

```bash
python3 -m http.server 8000
```

## Antes de publicar

- `canonical`, `og:url` e `og:image` apontam para `https://juntadeaco.com.br/`. Se o domínio for outro, troque no `<head>` do `index.html`.
- Meta Pixel e Clarity estão vazios: preencha em `CONFIG` para ativar.
- Os vídeos de depoimento só carregam o YouTube quando a pessoa clica (a página abre mais rápido).
