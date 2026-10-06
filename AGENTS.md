# Regras para os agentes (Claude)

Este repositório guarda sites de nicho com links de afiliado. O dono só **aprova**: todo trabalho chega como pull request, e nada vai para `main` sem o merge dele.

## Fluxo obrigatório

1. Crie um branch a partir de `main` (`artigo/<slug>`, `manutencao/<data>`, `pauta/<data>`).
2. Faça as mudanças só dentro do nicho em questão (`sites/<nicho>/`). O tema compartilhado (`themes/base/`) só muda em PR próprio, explicando o motivo.
3. Abra um PR com: o que mudou, fontes consultadas (links), o que falta o dono fazer (por exemplo, colar um link de afiliado).
4. **Nunca** faça merge, force-push ou commit direto em `main`.

## Regras de conteúdo

- **Não invente testes.** Não escreva "testamos", "usamos por 3 meses" e afins. Os guias se baseiam em especificações publicadas e no tipo de uso.
- **Toda especificação precisa de fonte**, de preferência o site ou o manual do fabricante. Se não conseguir confirmar um dado, omita ou escreva "não informado pelo fabricante".
- **Não fixe preço no texto.** Preço muda; use faixas qualitativas ("entrada", "intermediário") e o botão "Ver preço".
- **Não use nem imite marcas, logos ou textos de lojas.** Não copie descrições de produto.
- **Não faça avaliações ou depoimentos falsos.** Nada de "clientes dizem".
- Escreva em português do Brasil, direto, com seções úteis: para quem é, o que olhar na hora de comprar, os modelos e as perguntas frequentes.
- Cada artigo deve ter de 3 a 6 produtos, um veredito claro e a data em `date`/`lastmod`.

## Produtos e links

- Produtos ficam em `sites/<nicho>/data/produtos.yaml` e entram no texto com `{{< produto id="..." >}}`.
- `ofertas[].link` deve ser **link de afiliado**. Se ainda não houver um, deixe `link: ""` e liste no PR, em "Pendências do dono", quais links ele precisa gerar.

## Manutenção (agente semanal)

- Verifique se os links de oferta respondem e se os produtos continuam à venda.
- Sinalize produtos descontinuados e sugira substitutos em um PR de manutenção.

## Novo nicho

Copie `sites/ferramentas/` para `sites/<novo-nicho>/`, troque título, tagline e cor em `hugo.toml`, esvazie `content/guias/` e `data/produtos.yaml`, e adicione o nicho à matriz em `.github/workflows/build.yml`.
