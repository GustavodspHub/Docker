# Introdução

## O que são containers?

> Um container é um padrão de unidade de software
> que empacota código e todas as dependências de
> uma aplicação fazendo que a mesma seja executada
> rapidamente de forma confiável de uma ambiente
> computacional para o outro.

## Como funcionam os containers?

Quando se trata de container, envolve alguns pilares que devemos estar
familiarizados. São elas:

- Namespaces: Os namespaces servem para isolar processos.
- CGroups: Os CGroups servem para controlar os recursos de cada processos.
- OFS (Overlay File System) File System : Trabalha com camadas de forma individualizada.
- Imagens: Conjunto de dependências encadeadas para ser utilizado.
- Dockerfile: Arquivo declarativo para construir imagens.

## As imagens são imutáveis

Todas as imagens que são construídas, são imutáveis. É possível escrever dentro de um container, mas isso só é possível pois quando a imagem é construída, é criada uma camada de Read/Write (Leitura e Escrita). Porém, a imagem em sí não é alterada, e sim o comportamento do container.

## Segunda maneira de criar uma imagem

Caso seja feita alguma alteração na camada de Read/Write do container, é feito um processo de "commit", e assim gerando uma nova imagem com as novas alterações.

## Onde ficam as imagens?

As imagens que utilizamos ficam dentro do "IMAGE REGISTRY" do Docker. Algo parecido como o GitHub. Ou seja, toda vez que utilizamos alguma imagem dentro de um Dockerfile por exemplo, estamos efetuando um "Pull", e toda vez que realizamos o build de uma imagem, estamos efetuando o "Push".

## Como o Docker funciona? (Pontos principais)

- Docker Host (API): O Docker Host roda um processo que disponibiliza uma API.
- Docker Host (Cache): O cache do Docker Host, armazena as imagens que tiveram "Push" ou "Pull" do "IMAGE REGISTRY", para quando for criado outros containers, utilizar as informações do cache para não ficar realizado downloads.
- Docker Host (Volumes): Gerenciamento de Volumes
- Docker Host (Network): Comunicação entre containers
- Docker Client: O Docker Client faz chamadas para a API do Docker Host
