**Português** · [voltar ao README](../README.md)

# Registro de versões

Cada versão é uma publicação no servidor. Antes da 1.0 está o caminho até a interface final. Depois dela, o segundo número sobe com funcionalidade nova e o terceiro com ajuste.

`novo` funcionalidade · `ajuste` mudança pedida no uso · `correção` defeito resolvido · `segurança` · `dados` · `desempenho`

---

## v1.1.3 · 25/11/2026
- `ajuste` Centro de custo gravado inteiro, com o complemento depois do hífen (ex: 755702-1), no pedido, no arquivo e no card. A regional continua conferida pelo número principal.
- `ajuste` Pedido de impressão no modelo do atendimento: no item por m², a quantidade é a metragem total, e os valores saem com vírgula e milhar.

## v1.1.2 · 25/11/2026
- `correção` A janela "Trocar senha" aparecia cortada no topo da tela.

## v1.1.1 · 24/11/2026
- `ajuste` Proposta de serviço mais curta: uma descrição geral, o nome do item como está no contrato e uma sugestão de nome para salvar o arquivo.

## v1.1 · 23/11/2026
- `novo` Aba Usuários para o administrador: criar conta (senha provisória mostrada uma vez), gerar nova senha, desativar e reativar.
- `segurança` Virar administrador só é possível por comando no servidor, e o próprio banco impede desativar um administrador.
- `dados` Todo evento de conta fica registrado (quem criou, desativou ou trocou a senha), num registro só de inserção.
- `dados` Banco de produção limpo antes da entrada dos beta testers; a numeração recomeçou do nº 1.

## v1.0.1 · 23/11/2026
- `ajuste` O aviso de centro de custo diz de que regional ele é.
- `ajuste` Sangria digitada em centímetros.
- `ajuste` O card no Ummense leva o nome do evento.
- `novo` Esteira real do Ummense ligada: todo pedido de impressão vira card sozinho.

## v1.0 · 23/11/2026: a versão final no ar
- `novo` Interface em React, no visual do protótipo aprovado, substituindo o MVP:
  - **novo pedido** em 3 etapas: dados, vitrine de itens com carrinho e revisão;
  - **meus pedidos**: detalhe, linha do tempo, baixar de novo, duplicar e cancelar;
  - **importar proposta**.
- `segurança` Sessão num cookie protegido, que o JavaScript não lê.
- `segurança` Nenhuma rota de dado é pública, e a documentação automática da API foi desligada.
- `segurança` A API não aceita chamadas de outros sites, e toda resposta sai com cabeçalhos de segurança.
- `segurança` Depois de 5 senhas erradas, o e-mail fica travado por 15 minutos.
- `desempenho` A própria API serve a interface, sem servidor extra.
- 378 testes automatizados.

## v0.12 · 19/11/2026
- `novo` O pedido de impressão vira card na esteira do Ummense (testado numa cópia do fluxo).
- `correção` Um envio por pedido: o Ummense duplica o card se o envio se repetir e não devolve identificador. Se o Ummense falhar, o pedido não é afetado.
- `novo` Protótipo da interface final aprovado (arquivo à parte, fora do servidor).

## v0.11 · 13/10/2026
- `novo` Descrição e observação por item na proposta. O atendimento pediu e entrou no mesmo dia.

## v0.10 · 13/10/2026
- `novo` Leitura da proposta em PDF, conferida linha a linha contra o contrato. Com 8 propostas reais, em dois layouts: 22 de 22 linhas e 8 de 8 totais certos.
- `novo` Fluxo de serviço em produção, 3 semanas antes do prazo.

## v0.9 · 13/10/2026
- `desempenho` Pool de conexões e cache: abrir um pedido caiu de ~8 s para ~1,3 s, e os testes de 274 s para 108 s.

## v0.8 · 08/10/2026
- `dados` Cada licitada configurada num arquivo próprio, com contrato, vigência e se está ativa. Com o contrato vencido, ela some da tela.
- `dados` Tabela de preços gerada no "tudo ou nada": se uma aba vier com defeito, nada é gravado.
- `correção` Juntar abas transformava o item "40" em "40.0".

## v0.7 · 06/10/2026
- `novo` Login individual e "Meus pedidos".
- `correção` 1 centavo a menos em ~0,1% dos itens, achado por teste de estresse; a conta passou para Decimal.
- `correção` Um caractere invisível derrubava a gravação.
- `correção` Medida gravada diferente da cobrada.
- `correção` O carrinho usava valores da tela anterior.
- `correção` Duplicar um pedido devolvia o número do antigo.
- `segurança` Erros sem detalhe interno, e entradas absurdas recusadas.

## v0.6 · 02/10/2026
- `segurança` Gravação de pedido só com chave de API.
- `segurança` A API usa um usuário de banco que só lê e insere.

## v0.5 · 02/10/2026
- `dados` SQLite → PostgreSQL, com tabelas que só aceitam inserção.
- `novo` O pedido é gravado antes de liberar os arquivos.

## v0.4 · 02/10/2026
- `novo` Etiqueta com um bloco por destino.
- `segurança` Senha fora do código.
- `correção` 2 itens errados na planilha-fonte, achados pelo teste de integridade.

## v0.3 · 25/08/2026
- `novo` Sangria opcional (única ou por lado), destino por item e título do Ummense automático.
- `correção` Sangria negativa permitia mexer no preço; mais 9 bugs de cálculo e de tela.
- Regra de negócio de 0% para ~90% de cobertura de testes.

## v0.2 · 29/05/2026
- `novo` Número do contrato no pedido.

## v0.1 · 28/05/2026
- `novo` MVP no ar.
- `correção` 3 publicações falharam seguidas por falta de uma dependência; resolvido no mesmo dia.
