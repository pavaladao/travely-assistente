---
name: cuidar-proposta
description: >-
  Cria, atualiza, marca ou aceita uma proposta no Travely. Use quando a pessoa
  falar em orçamento, proposta, carta, preço por pessoa, casal, família ou
  grupo, ou em ganhar ou perder o orçamento. O preço é vitrine. Não lance
  comissão aqui.
---

# Cuidar da proposta

Leia `perfil.md` na raiz. Sem arquivo, ou com `nome` vazio, pare e siga configurar-agencia.

O preço é vitrine. Não vira comissão e não entra no faturamento.

Obrigatório na criação: título. O resto da pasta é o que a pessoa já souber: clientes (um nome por linha), origem, destino, saída, volta, noites, preço de vitrine e `preco_por` (`pessoa`, `casal`, `familia`, `grupo`).

Carta, inclui, não inclui e pagamento não entram em `salvar_proposta`. São seções do documento. `obter_proposta` devolve `documento_id`. `ler_roteiro` com esse id mostra cada seção. `forma_secao` devolve os campos daquele tipo. `editar_peca` grava `peca_id` e `campos`. No pagamento, a forma também traz preço, preço por, parcelas, operadora, `clientes_nomes` e o texto. O preço continua vitrine e não entra no balanço.

Na correção da pasta, `proposta_id` e o campo que muda. O título atual permanece se não for enviado.

A operadora da proposta é texto. Não é o fornecedor da venda. A carta é o texto da pessoa. Não escreva uma carta que ela não pediu.

Ache as ferramentas com `descobrir` e grave com `executar_gravacao`.

## Cliente

Liste os clientes antes. Um nome igual: use o cadastro. Dois próximos: pare. Nome novo na lista fica pendente.

## Estágio e aceite

Estágios sem criar viagem: `rascunho`, `em_andamento`, `perdida`, `cancelada`, por `marcar_proposta`. "Perdemos" é `perdida`, depois de dizer qual proposta.

`aceitar_proposta` cria a viagem em pagamento e exige `confirmar=true`. Não lança comissão. Antes de pedir a confirmação, leia a proposta com `obter_proposta` e diga título, destino, datas e clientes. A pasta que nasce ainda precisa das vendas, se a pessoa quiser o mês contabilizado.

Ligar a uma viagem que já existe é `viagem_id` em `salvar_proposta`. Soltar é `desvincular_proposta`. Apagar é `apagar_proposta` com `confirmar=true`. A viagem ligada continua.

Orçamento é proposta. Pasta já vendida é viagem. Se a pessoa aceitou, a viagem nasce do aceite, não de um segundo `salvar_viagem`.
