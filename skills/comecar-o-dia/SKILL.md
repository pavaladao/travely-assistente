---
name: comecar-o-dia
description: >-
  Lê o painel da home do Travely e explica viagens abertas, orçamentos, avisos
  e a faixa do mês. Use quando a pessoa perguntar o que tem hoje, o que está
  pendente, as saídas da semana ou por onde começar.
---

# Começar o dia

Leia `perfil.md` na raiz. Sem arquivo, ou com `nome` vazio, pare e siga configurar-agencia.

Chame `ver_painel`. Não chame o financeiro nesta skill. A faixa é o resumo. O mês fechado, com a receber e o que caiu, é a skill ler-financeiro.

Fale na língua do perfil. Traduza o que voltar, nesta ordem:

| O que veio | O que dizer |
| --- | --- |
| Viagens abertas | Título, destino, saída. A que sai primeiro vem antes |
| Orçamentos em andamento | Título. Não é venda e não é comissão |
| Saída perto | Saída nos próximos 14 dias |
| Cliente pendente | Nome na viagem, cadastro ainda sem telefone, e-mail ou documento |
| Comissão a receber | Intermediação deste mês, comissão ainda sem data em que caiu |
| A receber do cliente | Repasse em que o cliente ainda não pagou |
| Na conta | Repasse já recebido do cliente e ainda não pago ao fornecedor |
| Sem roteiro | Viagem aberta sem dia montado |
| Roteiro sem link | Roteiro com dia, link do cliente ainda não gerado |
| Faixa do administrador | Faturamento, meta e sobra do mês. Sobra é faturamento menos custos |
| Faixa do gerente | Comissão da equipe e meta. Sem custo |
| Faixa do consultor | Comissão e meta, quando a meta do mês existe. Sem meta, a faixa não vem |

Ofereça o próximo passo em uma frase, sem executar: completar o cliente, lançar a venda ou montar o roteiro. A pessoa escolhe.
