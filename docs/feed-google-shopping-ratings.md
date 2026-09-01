---
title: "Feed Google Shopping de avaliações (Product Ratings) — como gerar o XML para Tray e Merchant Center"
description: "Guia para gerar o feed de Google Product Ratings (avaliações de produto) a partir de pedidos CSV, compatível com Tray e Google Merchant Center. Explicamos o formato das estrelas no Shopping."
---

# Feed Google Shopping de avaliações (Product Ratings): do CSV ao XML sem dor

As estrelas ao lado do produto no Google Shopping vêm de um arquivo chamado **feed de Product Ratings**. Ele mistura três fontes: o produto (SKU), o pedido (quem comprou) e a avaliação (quantas estrelas). Fazer esse arquivo manualmente é chato e erra fácil — e um erro derruba a aprovação no Merchant Center.

## Por que o Product Ratings importa

- Produtos com avaliações no Google Shopping **têm mais cliques** que os sem
- As estrelinhas aparecem junto ao anúncio/lista, aumentando a credibilidade
- O Google exige o **feed no formato XML** certo, com os dados agrupados por produto

## A estrutura que o Google espera

O `product review feed` do Product Ratings tem, basicamente:

- **Marca / Identificação do produto** (Gtin, MPN ou Brand+Name)
- **Reviews múltiplos por produto** — o agregado de quem comprou e avaliou
- **Campos por avaliação**: nota (1-5), título, conteúdo, autor, data
- Código do país da moeda (ex.: `BR`) e a moeda (ex.: `BRL`)

Cada produto precisa ter pelo menos **um review válido** para as estrelas aparecerem. O feed inteiro é re-enviado periodicamente para o Merchant Center.

## Como montar sem digitar XML na mão

Se você já tem **um CSV de pedidos** (o gerado pelo seu ERP/Tray com as avaliações) e **um CSV de produtos**, o passo a passo é:

1. **Cruzar**: identificar quais pedidos tiveram review e qual SKU de produto cada um representa
2. **Agrupar**: juntar os reviews por produto
3. **Gerar o XML**: montar o arquivo no formato que o Google espera, no layout da sua moeda (BRL/BR)
4. **Enviar**: subir no Google Merchant Center e manter atualizado (execução recorrente)

## A opção pronta: script Python

Em vez de estruturar o XML toda semana, um **script Python** faz isso automaticamente: lê os dois CSVs, cruza, agrupa e gera o feed no formato certo — sem XML manual, sem erro de tag.

👉 O **Google Product Ratings Feed Generator** (compatível com Tray) faz exatamente isso: alimente com os CSVs de pedidos e produtos e receba o feed pronto para subir no Merchant Center. [Baixe o script no Gumroad](https://yodabug.gumroad.com/l/ucbnjz).