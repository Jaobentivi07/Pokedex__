É um projeto de Pokédex desenvolvido com HTML, CSS e JavaScript, que utiliza a API pública [PokéAPI](https://pokeapi.co/?utm_source=chatgpt.com) para buscar informações dos Pokémon.

## 1. Como o projeto funciona

A aplicação permite:

- Pesquisar Pokémon pelo nome ou número.
- Visualizar o nome e o número do Pokémon.
- Exibir a imagem animada do Pokémon.
- Navegar entre Pokémon usando os botões Prev e Next.
- Reproduzir uma música de fundo.

## 2. Estrutura do projeto

| Arquivo         | Responsabilidade              |
| --------------- | ----------------------------- |
| `index.html`    | Estrutura da página           |
| `css/style.css` | Aparência e posicionamento    |
| `js/script.js`  | Lógica e integração com a API |

## 3. Como funciona a comunicação com a API?

O principal trecho está no arquivo `js/script.js`:

```
const fetchPokemon = async (pokemon) => {
    const APIResponse = await fetch(
        `https://pokeapi.co/api/v2/pokemon/${pokemon}`
    );

    if (APIResponse.status === 200) {
        const data = await APIResponse.json();
        return data;
    }
}
```

Aqui acontecem três coisas:

1. `fetch()` realiza uma requisição HTTP para a PokéAPI.
2. `await` espera a resposta da API.
3. `.json()` transforma a resposta em um objeto JavaScript.

Depois, o projeto utiliza os dados recebidos para atualizar a tela:

```
pokemonName.innerHTML = data.name;
pokemonNumber.innerHTML = data.id;
```

## 4. Como funciona a autenticação?

Não utiliza autenticação

Esse é um detalhe importante: seu projeto não possui sistema de login, cadastro, senhas ou tokens.

A comunicação acontece diretamente entre o navegador do usuário e a PokéAPI.

Usuário

Pesquisa um Pokémon

JavaScript

Executa o fetch()

PokéAPI

Retorna os dados do Pokémon

Página atualizada

Nome, número e imagem

Não há geração, armazenamento ou validação de tokens nesse fluxo.

## 5. O que pratiquei nesse projeto?

trabalhei com conceitos importantes de JavaScript:

- `async/await`: programação assíncrona.
- `fetch()`: consumo de APIs.
- `addEventListener()`: eventos.
- `querySelector()`: manipulação do DOM.
- `innerHTML`: atualização de conteúdo.
- `JSON`: manipulação de dados.
- Condicionais: tratamento de Pokémon não encontrado.
