# Pede.ai

Pedido às gráficas e agências do Sebrae PR em poucos minutos.

O núcleo de criação do Sebrae PR pede impressos (banners, lonas, displays, adesivos) e serviços de design a fornecedores com contrato. Antes, cada pedido era montado à mão: buscar o item na planilha do contrato, calcular o preço, conferir o centro de custo, escrever o texto do pedido e da etiqueta. O Pede.ai faz tudo isso num fluxo só.

> Ferramenta interna do Sebrae PR, por isso o código não é público. Este repo mostra o projeto. Telas com dados fictícios.

## O que faz

- **Pedido de impressão:** escolhe os itens do contrato num carrinho, informa medida e quantidade, e o preço sai calculado por m² ou por unidade.
- **Pedido de serviço:** a agência manda a proposta em PDF, o Pede.ai lê, confere item, código e valor contra o contrato e aponta o que não bate.
- **Centro de custo:** valida se o centro de custo pertence à regional do pedido.
- **Documentos:** gera o texto do pedido e da etiqueta no formato que o atendimento já usa.
- **Meus pedidos:** histórico com download de novo, duplicar e cancelar.
- **Login individual** por e-mail e senha.

## Telas

<!-- falta: prints com dados fictícios -->

## Stack

- MVP em Streamlit, em produção com usuários reais
- API em FastAPI, deploy no Render
- PostgreSQL no Supabase, com RLS e tabelas de histórico só de inserção
- Frontend final em React + Vite, em construção
- Testes com pytest: regras de preço, banco, login, ponta a ponta no Streamlit e teste de estresse com centenas de carrinhos aleatórios

## Decisões

- Lancei primeiro o MVP em Streamlit pra validar o uso real antes de investir no React.
- O preço sempre vem do contrato. A leitura da proposta só aponta divergência, nunca define valor.
- A tabela de preços é gerada da planilha oficial do contrato e não grava nada se qualquer aba vier errada.
