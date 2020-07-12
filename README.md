<img alt="GoStack" src="https://storage.googleapis.com/golden-wind/bootcamp-gostack/header-desafios.png" />

<h3 align="center">
  Desafio 08: Fundamentos do React Native
</h3>

## :rocket: Sobre o desafio

Nesse desafio, foi desenvolvida uma nova aplicação, chamada GoMarketplace. Dessa vez colocou-se em prática o que foi aprendido até agora no React Native, junto com TypeScript, utilizando rotas, Async Storage e a Context API.

### Utilizando uma fake API

Antes de tudo, para que haja os dados para exibir em tela, foi criado um arquivo para ser utilizado como fake API que irá prover estes dados.

Para isso, está instalada no package.json uma dependência chamada `json-server`, e um arquivo chamado `server.json` que contém os dados para uma rota `/products`. Para executar esse servidor basta executar o comando:

```js
  yarn json-server server.json -p 3333
```

### Layout da aplicação

Essa aplicação possui um layout que pode ser seguido para conseguir visualizar o seu funcionamento.

O layout pode ser acessado através da página do Figma, no [seguinte link](https://www.figma.com/file/VgK3hsmyGbqiGu9FdqfUzF/GoMarketplace?node-id=0%3A1).

Você precisará uma conta (gratuita) no Figma pra inspecionar o layout e obter detalhes de cores, tamanhos, etc.

### Funcionalidades da aplicação

Deve-se verificar os arquivos da pasta `src` e completar onde não possui código, com o código para atingir os objetivos de cada rota.

- **`Listar os produtos da fake API`**: A página `Dashboard` deve ser capaz de exibir uma listagem através de uma tabela, com o campo `title`, `image_url` e `price`.

- **`Adicionar itens ao carrinho`**: Em toda a aplicação, deve-se utilizar o Contexto chamado `cart` que está disponível. Deve-se completar as funcionalidades dentro de `hooks/cart.tsx` para adicionar itens ao carrinho.

Caso um produto a ser adicionando já exista no carrinho, a quantidade dele deve ser alterada no contexto para evitar itens duplicados.

- **`Exibir itens do carrinho`**: Na página `Cart` deve-se exibir todos os itens do carrinho, junto com a quantidade, valor único, valor subtotal dos itens e total de todos os items.

- **`Aumentar quantidade de itens do carrinho`**: Na página `Cart` deve-se permitir que o usuário aumente a quantidade de itens do mesmo produto, utilizando a função `increment` dentro do contexto em `/src/hooks/cart.tsx`.

- **`Diminuir quantidade de um item do carrinho`**: Na página `Cart` deve-se permitir que o usuário decremente a quantidade de itens do mesmo produto, utilizando a função `decrement` dentro do contexto em `/src/hooks/cart.tsx`.

- **`Exibir valor total dos itens no carrinho`**: Tanto na página `Dashboard` como na página `Cart`, deve-se exibir o valor total de todos os itens que estão no carrinho.

### Específicação dos testes

Em cada teste, há uma breve descrição no que a aplicação deve cumprir para que o teste passe.

Para esse desafio, existem os seguintes testes:

- **`should be able to list the products`**: Para que esse teste passe, a aplicação deve permitir que sejam listados na sua tela `Dashboard`, todos os produtos que são retornadas da Fake API. Essa listagem deve exibir o `title` e o `price` que deve ser formatado utilizando a função `Intl`.

- **`should be able to add a product to the cart`**: Para que esse teste passe, deve-se permitir que seja possível adicionar produtos da `Dashboard` ao carrinho, utilizando o contexto de `cart` disponibilizado.

- **`should be able to list the products on the cart`**: Para que esse teste passe, deve-se permitir que seja possível listar os produtos que estão salvos no contexto do carrinho na página `Cart`, nessa página deve-se exibir o nome do produto, o subtotal total de cada produto (price \* quantity).

- **`should be able to calculate the cart total`**: Para que esse teste passe, tanto na página `Dashboard` como na página `Cart`, deve-se exibir o valor total de todos os itens que estão no carrinho.

- **`should be able to show the total quantity of itens in the cart`**: Para que esse teste passe, tanto na página `Dashboard` como na página `Cart`, deve-se exibir o número total de itens que estão no carrinho.

- **`should be able to increment product quantity on the cart`**: Para que esse teste passe, deve-se permitir que seja possível incrementar a quantidade de um produto do carrinho, utilizando o contexto de `cart` disponibilizado.

- **`should be able to decrement product quantity on the cart`**: Para que esse teste passe, deve-se permitir que seja possível decrementar a quantidade de um produto do carrinho, utilizando o contexto de `cart` disponibilizado.

Ao decrementar a quantidade de um produto, não deve ser permitido que ele seja decrementado para um valor negativo, sendo a quantidade mínima 1 para estar no carrinho.

- **`should be able to navigate to the cart`**: Para que esse teste passe, no componente `FloatingCart` na Dashboard, deve-se permitir que ao clicar no botão de carrinho com o testID de `navigate-to-cart-button`, o usuário seja redirecionado para a página `Cart`.

- **`should be able to add products to the cart`**: Para que esse teste passe, no arquivo onde contém o contexto do carrinho, deve-se permitir que a função `addToCart` adicione um novo item ao carrinho.

- **`should be able to increment quantity`**: Para que esse teste passe, no arquivo onde contém o contexto do carrinho, deve-se permitir que a função `increment` incremente em `1` unidade a quantidade de um item que está armazenado no contexto.

- **`should be able to decrement quantity`**: Para que esse teste passe, no arquivo onde contém o contexto do carrinho, deve-se permitir que a função `decrement` decremente em `1` unidade a quantidade de um item que está armazenado no contexto.

- **`should store products in AsyncStorage while adding, incrementing and decrementing`**: Para que esse teste passe, no arquivo onde contém o contexto do carrinho deve-se permitir que todas as atualizações feitas no carrinho, sejam salvas no AsyncStorage. Por exemplo, ao adicionar um item ao carrinho, adicioná-lo também no AsyncStorage. Também atualizar o valor do AsyncStorage quando incrementar ou decrementar a quantidade de um item.

- **`should load products from AsyncStorage`**: Para que esse teste passe, no arquivo onde contém o contexto do carrinho, deve-se permitir que todos os produtos que foram adicionados sejam buscados do AsyncStorage.
