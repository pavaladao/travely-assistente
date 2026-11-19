---
name: criar-roteiro
description: >-
  Monta um roteiro no Travely. Use quando a pessoa pedir para criar, montar,
  escrever ou completar um roteiro ou itinerário. O rascunho inteiro fica
  pronto na conversa antes de gravar.
---

# Criar roteiro

Leia `perfil.md` na raiz. Sem arquivo, ou com `nome` vazio, pare e siga configurar-agencia.

Leia também `titulo_roteiro`, `tom`, `trata_cliente` e `publico`. Grave no Travely só depois do rascunho. Sem o rascunho completo, não chame a ferramenta de escrita.

## O que perguntar

Pergunte, numa mensagem só, o que faltar. Não invente horário de voo, preço, voucher nem nome de hotel.

- Quem viaja, do jeito que entra no título
- Origem e destino
- Saída e volta, ou a quantidade de noites
- O que já está fechado: voo, hotel, traslado, ingresso, com horário, número e fornecedor
- O que é só sugestão
- A viagem já cadastrada, quando o roteiro for ligado a ela
- Crianças e a idade, se `publico` for `familias` ou `misto`. Nos outros públicos, só pergunte se a pessoa falar de criança

Clima do mês, descrição de um ponto famoso e a escolha da foto podem ser escritos sem perguntar.

## Rascunho

Copie `rascunho.md` desta pasta para a conversa, preencha e apague a seção que ficou sem fato. Não preencha com texto genérico.

O título da capa usa `titulo_roteiro`, com `{quem}` já trocado. Foto vazia sai. `tom: proximo` escreve como quem conversa com `trata_cliente`. `tom: formal` tira a intimidade e mantém o fato.

A capa é a primeira coisa que o cliente lê. O subtítulo é uma frase, não um parágrafo. A abertura separa o que já foi reservado do que dá para trocar.

Importante é o que evita surpresa naquele mês: roupa, temporada, temperatura, chuva. Uma dica por linha. Não repete o passeio.

Hospedagem leva nome, regime, noites, endereço e as comodidades que mudam a estadia, uma por linha.

O mapa marca um lugar só, em geral o hotel ou o centro do destino.

O que inclui, o que não inclui e o plano de pagamento só entram com fato dado pela pessoa. Para crianças obedece ao `publico` e sai quando não há criança. Plano de pagamento só leva valor que a pessoa ou o Travely já informou.

Cada dia cobre uma data, da saída à volta. O título do dia é o fato principal. Dentro do dia, a ordem é a do relógio. O que está fechado leva os dados reais. Sugestão começa o nome com "Sugestão" e o texto diz que dá para trocar. Nota é um aviso curto e não tem foto.

## Fotos

Escolha as fotos no rascunho, antes de gravar. Siga a skill baixar-fotos. A capa leva até três fotos de lugares diferentes. A primeira é a principal. Passeio, ingresso, aéreo, traslado, hospedagem e importante levam uma foto daquele lugar. Sem uma imagem à altura, deixe sem foto.

## Gravar

Com o rascunho fechado, ache as ferramentas com `descobrir` e grave com `executar_gravacao`. Datas em AAAA-MM-DD. Liste a viagem antes de usar o id.

1. `gravar_roteiro` com a capa e as seções que estão no rascunho, nesta ordem: importante, hospedagem, mapa, inclui, nao_inclui, criancas, pagamento. `viagem_id` quando a pasta existe.
2. Um `montar_dia` por dia, na ordem das datas. Peças na ordem do horário: `aereo`, `traslado`, `passeio`, `ingresso`, `nota`. Hospedagem não é peça do dia. A foto não entra aqui.
3. `ordenar_roteiro` com alvo `blocos`. A ordem é o id de importante, o id de hospedagem, `itinerario`, e depois mapa, inclui, nao_inclui, criancas, pagamento.
4. `colocar_foto` para cada imagem, como na skill baixar-fotos. Capa usa `roteiro_id` e o slot `foto`, `foto_2` ou `foto_3`. Peça usa `peca_id`. Sem arquivo, grave sem essa foto.

`dias_do_periodo` serve quando a capa já tem saída e volta e a pessoa quer um dia por data, para preencher depois. Não substitui o rascunho.

`gerar_link` só quando a pessoa pedir o link do cliente. `publicar_roteiro` é administrador, com `confirmar=true`. `apagar_roteiro` pede confirmação. Apagar peça ou dia não apaga a venda ligada.

Trecho de voo é `trecho` numa peça `aereo` já criada. Não use `trecho` em passeio nem traslado. A logo fica na tela.
