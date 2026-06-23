# FOMEZERO — Frontend

O **FOMEZERO** é uma aplicação web desenvolvida para facilitar a busca e a escolha de restaurantes, lanchonetes, cafeterias, confeitarias e outros estabelecimentos gastronômicos.

A proposta do projeto é oferecer uma interface simples, visual e intuitiva, permitindo que o usuário navegue por categorias, visualize restaurantes, aplique filtros de busca e consulte informações como avaliações, faixa de preço, tempo estimado e cardápio.

Este repositório contém a parte **frontend** da aplicação, desenvolvida com **HTML5, CSS3 e JavaScript**.

---

## Funcionalidades

- Tela inicial, onboarding, cadastro e login visual;
- Cadastro de usuários integrado ao backend;
- Listagem de restaurantes por categoria;
- Categorias de lanches, almoço, comida vegana, doces e bebidas;
- Pesquisa por nome de restaurante ou prato;
- Filtro por categoria, preferência, avaliação e preço máximo;
- Cardápio filtrado pelo preço selecionado;
- Detalhes e cardápio de cada restaurante;
- Publicação de avaliações com nota de 1 a 5 e comentário;
- Média e quantidade de avaliações calculadas pelo backend;
- Listagem das avaliações de cada restaurante;
- Tela "Minhas Avaliações" preenchida com os dados do usuário atual;
- Exclusão de avaliações;
- Favoritos, perfil, suporte e demais telas demonstrativas;
- Comunicação com a API REST por meio de `fetch()`.

---

## Tecnologias

- HTML5
- CSS3
- JavaScript
- Fetch API
- Session Storage
- Live Server

---

## Estrutura

```text
fomezero-frontend/
|-- src/
|   |-- index.html
|   |-- style.css
|   `-- script.js
`-- README.md
```

---

## Integração com o backend

O frontend utiliza como endereço base:

```javascript
const API_BASE_URL = 'http://localhost:8080/api';
```

Principais requisições realizadas:

| Método | Endpoint | Finalidade |
|---|---|---|
| POST | `/api/usuarios` | Cadastrar usuário |
| GET | `/api/restaurantes` | Listar restaurantes |
| POST | `/api/avaliacoes` | Publicar ou atualizar avaliação |
| GET | `/api/avaliacoes/restaurante/{nome}` | Avaliações de um restaurante |
| GET | `/api/avaliacoes/restaurante/{nome}/media` | Média e quantidade de avaliações |
| GET | `/api/avaliacoes/usuario/{email}` | Avaliações do usuário atual |
| DELETE | `/api/avaliacoes/{id}` | Excluir avaliação |

---

## Como executar

### 1. Iniciar o backend

Execute primeiro o projeto `fomezero-backend`. A API deve estar disponível em:

```text
http://localhost:8080
```

Teste no navegador:

```text
http://localhost:8080/api/restaurantes
```

### 2. Iniciar o frontend

Abra `src/index.html` com o Live Server. O endereço normalmente será:

```text
http://127.0.0.1:5500/src/index.html
```

Também é possível executar pelo servidor interno do IntelliJ, geralmente na porta `63342`.

Não abra o HTML usando um endereço `file:///`, pois o frontend precisa ser servido por HTTP para se comunicar corretamente com a API.

---

## Fluxo das avaliações

1. O usuário abre um restaurante.
2. Seleciona uma nota e escreve um comentário.
3. O frontend envia a avaliação ao backend.
4. O backend armazena ou atualiza a avaliação do usuário.
5. A média e a quantidade de avaliações são recalculadas.
6. A avaliação aparece no restaurante e na tela "Minhas Avaliações".

---

## Estado atual e limitações

- O cadastro e as avaliações estão integrados ao backend.
- O login ainda é visual e não autentica credenciais no backend.
- Os dados do usuário atual são mantidos no `sessionStorage`.
- Alguns dados da interface ainda são demonstrativos.
- Como o backend armazena dados em memória, novos cadastros e avaliações são perdidos quando a API é reiniciada.
