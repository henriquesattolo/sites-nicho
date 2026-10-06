# Sites de nicho (afiliados)

Sites estáticos (Hugo) de guias de compra com links de afiliado. Um tema compartilhado e um site por nicho.

```
themes/base/          tema comum a todos os nichos
sites/ferramentas/    primeiro nicho: Bancada Certa
AGENTS.md             regras que os agentes Claude seguem
```

## Como funciona

Os agentes Claude pesquisam, escrevem e mantêm os artigos, **sempre por pull request**. Você revisa e dá merge (dá para fazer pelo app do GitHub). O CI valida o build de todo PR.

## Rodar localmente

```bash
cd sites/ferramentas
hugo server
```

## Publicação (Cloudflare Pages, grátis e funciona com repositório privado)

1. No Cloudflare: Workers & Pages → Create → Pages → conecte este repositório.
2. Build command: `hugo --minify`, com root directory `sites/ferramentas`, output `public`. Defina a variável `HUGO_VERSION=0.140.2`.
3. Aponte o domínio e atualize `baseURL` em `sites/ferramentas/hugo.toml`.

Cada nicho novo vira um projeto Pages separado, apontando para a sua pasta em `sites/`.
