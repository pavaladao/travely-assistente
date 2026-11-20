---
name: baixar-fotos
description: >-
  Baixa a foto de um lugar, praia, parque, mirante ou hotel e grava no roteiro
  do Travely. Use ao escolher ou colocar foto de capa, de passeio ou de
  hospedagem, e quando um link de imagem não baixar.
---

# Baixar fotos

A foto mostra aquele lugar. A praia do destino mostra a praia. A fachada do parque mostra o parque. Hotel mostra o hotel ou a vista dele.

Não use foto genérica de outro lugar, rua sem o atrativo, selfie, cardápio, print de mapa, logo ou imagem com marca d'água. Se a pessoa enviou a foto, use a dela. Sem uma imagem à altura, deixe sem foto e diga isso. O resto do roteiro segue.

## Onde achar

Procure nesta ordem, parando no primeiro arquivo que o Travely conseguir baixar:

1. O jpg, png, webp ou gif no site do lugar: hotel, parque, praia, prefeitura ou secretaria de turismo. O endereço é o do arquivo, não o da página.
2. A mesma foto salva no navegador, quando o site recusar o download automático. Não repita o link que falhou. Não leia a imagem para a conversa.
3. Wikimedia Commons e Google Imagens servem para achar a foto. O link deles não entra no roteiro. O Commons recusa o download do servidor. A miniatura do Google é pequena e o endereço muda. Abra a foto no navegador e salve o arquivo.

Pexels e Unsplash não substituem a praia da cidade nem a fachada do parque.

## Gravar

Siga o tamanho ideal e o mecanismo descritos em `colocar_foto`. A conversa leva só um texto curto.

- Endereço http(s) do arquivo: passe em `imagem`.
- Arquivo no disco deste servidor: passe o caminho em `imagem`.
- Arquivo em outra máquina: `POST /mcp/foto` com a mesma chave, campo `arquivo`, e passe o `id` da resposta em `imagem`.

Não mande data URI nem base64.

- Capa: `roteiro_id` e o slot `foto`, `foto_2` ou `foto_3`. Até três lugares diferentes. A primeira é a principal.
- Peça ou seção: `peca_id`. Passeio, ingresso, aéreo, traslado, hospedagem e importante levam foto. Nota não leva.

Tire uma foto só com `remover` e `confirmar=true`. A logo fica na tela.
