---
name: lancar-venda
description: >-
  Lança ou corrige a venda de uma viagem no Travely: serviço, modo, total e
  comissão. Use quando a pessoa pedir para registrar uma venda, lançar
  comissão, hotel, aéreo, passeio, traslado, seguro ou pacote pago. Não use
  para o preço de vitrine da proposta.
---

# Lançar venda

Leia `perfil.md` na raiz. Sem arquivo, ou com `nome` vazio, pare e siga configurar-agencia.

A venda mora numa viagem. Sem pasta, a skill criar-viagem vem antes. Sem a pessoa ter pedido a pasta, pergunte o título e o destino e crie. Não deixe a venda solta.

Obrigatórios na criação, dentro de `campos`: `cliente_nome`, `data_venda`, `servico`, `modo`, `valor_total`, `comissao`. A viagem vai em `viagem_id`, fora de `campos`.

Antes de gravar, `forma_venda` com o modo. Sem modo, a forma devolve o miolo e não traz os campos do repasse. `lancar_venda` e `editar_venda` recebem só as chaves que a forma listou, dentro de `campos`. Campo a mais volta com a lista daquele modo. Campo omitido numa correção permanece.

| Campo | O que significa |
| --- | --- |
| `servico` | `aereo`, `hotel`, `passeio`, `traslado`, `seguro`, `pacote`, `outro` |
| `modo` | `intermediacao`: a agência não segura o dinheiro do cliente. `repasse`: o cliente paga a agência e a agência paga o fornecedor |
| `valor_total` | Referência. Não entra no faturamento |
| `comissao` | O que fica com a agência. É o número do mês |
| `data_venda` | Mês da intermediação no faturamento |
| `data_comissao` | Dia em que a comissão caiu. Não muda o mês |
| `fornecedor_nome` | Tem de existir no cadastro compartilhado |

Ache as ferramentas com `descobrir` e grave com `executar_gravacao`.

## Cliente

1. `listar_clientes` com o nome.
2. Um igual: mande `cliente_id` e `cliente_nome` iguais ao cadastro, dentro de `campos`.
3. Dois próximos: pare e mostre os dois.
4. Nenhum: diga que o nome nasce pendente. Se a pessoa passou telefone, e-mail ou documento, grave a venda e em seguida `salvar_cliente` com o id que a venda devolveu. Sem contato, a venda segue e o aviso de cliente pendente aparece no painel.

## Fornecedor

Se a pessoa nomeou um: liste os fornecedores. Um igual: use o id. Nenhum: pare e pergunte se cadastra. `salvar_fornecedor` só depois do sim. A venda sem fornecedor é válida. A venda com nome que não existe falha.

## Modo

- "A operadora me paga" ou "comissão da companhia": `intermediacao`. Não mande valor recebido nem valor do fornecedor.
- "O cliente me pagou e eu pago o hotel": `repasse`. Pergunte, se não vieram, o valor recebido, a data de recebimento, o valor do fornecedor e a data do pagamento. Valor do fornecedor vazio vira total menos comissão quando os dois existem.
- Não deu para saber: pare e pergunte. Não escolha no escuro.

O preço da proposta não entra em `valor_total` nem em `comissao`. Se a pessoa disser "usa o valor do orçamento", repita o número e pergunte se aquele é o total de referência e qual é a comissão.

Correção é `editar_venda` com `venda_id` e `campos`. Campo omitido permanece. Cancelar é `cancelar_venda`, só administrador, com `confirmar=true`, depois de a pessoa confirmar. Cancelar não apaga o registro.

`venda_da_peca` é o caminho quando a venda nasce de uma peça do roteiro. Total e comissão vão em `campos`, na mesma forma da venda. A peça não traz preço.

Depois de gravar, `obter_viagem` e diga cliente, serviço, modo, total, comissão e se o cliente ficou pendente.
