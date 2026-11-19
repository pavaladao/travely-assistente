---
name: criar-viagem
description: >-
  Cria ou atualiza uma viagem no Travely. Use quando a pessoa pedir para abrir
  uma pasta, criar uma viagem, mudar título, destino, saída, volta ou status.
  Não use para orçamento nem para lançar comissão.
---

# Criar viagem

Leia `perfil.md` na raiz. Sem arquivo, ou com `nome` vazio, pare e siga configurar-agencia.

A viagem é a pasta: título, destino, saída, volta e status (`aberta` ou `concluida`). O título é o único obrigatório. Destino e datas, pergunte se não vieram. Status omitido fica `aberta`.

O cliente não é campo da viagem. Ele entra na venda ou na proposta. "Cria a viagem da Ana para Gramado" cria a pasta e diz que a Ana ainda não está ligada. Pergunte se lança a venda agora. Não invente total nem comissão.

## Antes de gravar

1. `listar_viagens` com um trecho do título ou do destino. Pasta igual, no mesmo destino e nas mesmas datas: abra com `obter_viagem` e pergunte se é essa. Não crie outra.
2. Se a pessoa nomeou o cliente, `descobrir` "listar clientes" e execute a leitura com `q`. Um nome igual: guarde o id para a venda, se ela vier. Dois nomes próximos: pare e pergunte qual. Nenhum: diga que o nome novo fica pendente até ter telefone, e-mail ou documento. Não chame `salvar_cliente` só para segurar o nome.
3. `descobrir` "criar viagem" e `executar_gravacao` em `salvar_viagem`. Sem id, cria. Com id, grava a pasta como deve ficar. Campo omitido na edição permanece.
4. `obter_viagem` e conte título, destino, datas e responsável.

Responsável novo só se a pessoa pediu e a chave é de administrador. Consultor e gerente não repassam. A ferramenta recusa. Não tente de novo.

A viagem não se apaga. Concluir é `status: concluida`.

Pergunte numa mensagem só, e não grave, quando faltar o título, quando duas pastas servirem, ou quando não der para saber se o pedido é pasta, orçamento ou venda.
