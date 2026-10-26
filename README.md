# Landing do WalletMe

Página estática (um `index.html` + `brand/`), sem build e sem servidor. Dados das telas: fictícios.

## Antes de publicar
- Confirmar a grafia do domínio. O `index.html` usa `walletme.com.br` em `canonical`, `og:url` e `og:image`; se o registro for outro, trocar nesses três pontos.
- O botão "Conhecer e entrar" aponta para `https://www.orangeinvest.com.br/entrar/walletme`: é a porta do WalletMe (login com a cara do WalletMe; quem já está logado vai para o app, ou para a página de apresentação se ainda não tiver acesso).

## Publicação sugerida: GitHub Pages (grátis, HTTPS automático)
1. Criar um repositório **público** só para a landing (por exemplo `walletme-landing`) e enviar o conteúdo desta pasta na raiz. Não há segredo nenhum aqui.
2. No repositório: Settings > Pages > "Deploy from a branch" > `main` / raiz. Em "Custom domain", informar o domínio (o GitHub cria o arquivo `CNAME`). Marcar "Enforce HTTPS" quando o certificado sair.
3. No Registro.br, em DNS do domínio:
   - Apex (`walletme.com.br`): quatro registros **A** para `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (e, se quiser IPv6, os **AAAA** `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`).
   - `www`: um **CNAME** para `<usuario-do-github>.github.io`.
   - Conferir os endereços na documentação do GitHub Pages antes de configurar; eles podem mudar.
4. Esperar a propagação (de minutos a algumas horas) e conferir `https://walletme.com.br` e `https://www.walletme.com.br`.

## Por que não no Railway
O serviço do Orange Invest já usa os dois domínios personalizados que o plano permite (www e app). Uma landing estática não precisa de servidor.

## Alternativa: Cloudflare Pages
Também grátis, mas pede trocar os servidores de DNS do domínio para a Cloudflare no Registro.br.
