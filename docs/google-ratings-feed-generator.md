---
title: "Google Product Ratings Feed Generator — script Python compatível Tray"
description: "Script Python que gera o feed de Google Product Ratings para e-commerce a partir de CSV de pedidos. Compatível com Tray, Merchant Center. Automatize avaliações de produto."
---

# Google Product Ratings Feed Generator — crie o feed de avaliações sem digitar XML na mão

O Google Product Ratings (estrelinhas nas listagens) depende de um feed XML misturando reviews, produtos e dados do pedido. Fazer esse feed manualmente é demorado e quebra fácil.

## O problema

- O formato XML do Product Ratings é chato e cheio de tags
- Precisa cruzar os pedidos (que tiveram review) com o catálogo de produtos
- Atualização recorrente vira trabalho contínuo se for manual
- Errar um campo derruba a aprovação no Merchant Center

## A solução: um script que gera o feed para você

O **Google Product Ratings Feed Generator** é um script Python que:

- Lê um CSV de pedidos (os que geraram avaliação) e um CSV de produtos
- Monta o feed XML no formato exigido pelo Google (Product Ratings)
- Gera o arquivo pronto para subir no Merchant Center / integração Tray
- Suporta execução recorrente (agendável) para manter o feed atualizado

Sem digitar XML na mão, sem perder tempo reescrevendo a mesma estrutura toda semana.

## Para quem é

- Lojas e e-commerces que querem as estrelinhas no Google Shopping/Ads
- Quem já usa Tray ou outro automação e quer o feed gerado por script
- Devs/agências que atendem lojistas e cobram por feed de ratings

👉 [Baixar o script no Gumroad](https://yodabug.gumroad.com/l/ucbnjz)