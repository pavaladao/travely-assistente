---
name: ler-financeiro
description: >-
  Lê o financeiro do mês no Travely e explica comissão, a receber, o que caiu,
  repasse na conta, meta e sobra. Use quando a pessoa perguntar do mês, do
  faturamento, da meta, do custo, da sobra ou de quanto falta receber. Não use
  para lançar uma venda.
---

# Ler o financeiro

Leia `perfil.md` na raiz. Sem arquivo, ou com `nome` vazio, pare e siga configurar-agencia. Fale na língua do perfil.

`descobrir` "financeiro do mês" e `executar_leitura` em `ver_financeiro`. Mês vazio é o mês atual. `mes` em `AAAA-MM`. `pessoa_id` só se a pessoa nomeou alguém, e só dentro do alcance.

| Cargo | O que mostrar | O que não mostrar |
| --- | --- | --- |
| Consultor | O próprio mês: comissão, a receber, o que caiu | Custo, meta de outro, sobra da agência |
| Gerente | O próprio e o de quem aponta para ele. Sem pessoa, a equipe | Custo e sobra da agência |
| Administrador | Sem pessoa: faturamento, meta, custos e sobra. Com pessoa: o balanço dela | Livro de quem a ferramenta recusou |

Como explicar o número:

- Faturamento do mês é a soma das comissões. Na intermediação, entra a venda cuja data de venda cai no mês. No repasse, entra a comissão cuja data de pagamento ao fornecedor cai no mês.
- A receber é intermediação do mês cuja comissão ainda não caiu, ou caiu depois do fim do mês.
- O que caiu é a comissão com data dentro do mês. Essa data não muda o mês do faturamento.
- Na conta ignora o mês escolhido: repasse já recebido do cliente e ainda não pago ao fornecedor. Diga recebido, a pagar e a margem.
- Valor total da venda é referência. Não some total no faturamento.
- Preço de proposta não entra nesta conta.
- Sobra, para o administrador, é faturamento menos custos do mês.
- Meta do consultor só aparece na faixa da home se existir. A leitura do mês continua valendo sem meta.

Custo, meta e dia de fechamento não se lançam nesta skill. "Lança o aluguel" ou "muda a meta" seguem administrar-agencia. Se `descobrir` não devolver a ferramenta, diga que esta chave não faz isso.
