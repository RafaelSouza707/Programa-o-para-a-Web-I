# Métodos de Arrays em JavaScript: Reduce, Map e Filter

Este repositório contém exemplos ilustrativos do uso dos métodos `reduce`, `map` e `filter` em JavaScript. Esses métodos são amplamente utilizados para manipulação de dados de forma funcional, concisa e legível.

---

## 🧮 Reduce

O método `reduce()` reduz os elementos de um array a um único valor. Ele executa uma função acumuladora para cada valor do array.

### 🔢 Somatório

```javascript
let listaSomar = [1, 2, 3, 4, 5];
const resposta = listaSomar.reduce((acumulado, valorAtual) => acumulado += valorAtual);
console.log(resposta); // 15
```

### 👥 Criar objetos a partir de uma lista

```javascript
let listaPessoas = [
    {nome : "Pessoa1", idade : "18"},
    {nome : "Pessoa2", idade : "19"},
    {nome : "Pessoa3", idade : "20"},
    {nome : "Pessoa4", idade : "21"},
    {nome : "Pessoa5", idade : "22"}
]; 

const obJetosPessoas = listaPessoas.reduce((acumulador, pessoa) => {
    acumulador[pessoa.nome] = pessoa.idade;
    return acumulador;
}, {});

console.log(obJetosPessoas);
```

### 🆔 Indexar lista de objetos por ID

```javascript
const lista = [
    {id: 1, nome : "Nome Da Silva"},
    {id: 2, nome : "Nome De Moura"},
    {id: 3, nome : "Nome Da costa"}
];

const callback = (acumulador, valor) => {
    acumulador[valor.id] = valor.nome;
    return acumulador;
};

const PessoasIndexadasPorId = lista.reduce(callback, {});
console.log(PessoasIndexadasPorId[2]); // Nome De Moura
```

---

## 🔁 Map

O método `map()` cria um novo array com os resultados da chamada de uma função para cada elemento.

### 🎯 Modificar valores de um array

```javascript
let array = [1, 2, 3, 4, 5];
let modificarArray = array.map(function(element) {
    return element * 3;
});

console.log(modificarArray); // [3, 6, 9, 12, 15]
```

### 🔐 Usar objetos como chave com `Map`

```javascript
const usuario1 = {nome: 'Joao'};
const usuario2 = {nome: 'Maria'};

const idade = new Map();
idade.set(usuario1, 20);
idade.set(usuario2, 22);

console.log(idade.get(usuario1)); // 20
```

### 🧱 Criar objetos com `Map`

```javascript
const nomeMap = new Map([
    ['nome', 'Rafael'],
    ['sobrenome', 'Moura']
]);

console.log(nomeMap.get('sobrenome'), nomeMap.get('nome')); // Moura Rafael
```

---

## 🔍 Filter

O método `filter()` cria um novo array com todos os elementos que passaram no teste implementado pela função fornecida.

### 💰 Filtrar por preço

```javascript
const produto = [
    {nome: 'Arroz', preco: 4.5},
    {nome: 'Frango', preco: 20},
    {nome: 'Chocolate', preco: 12.5},
    {nome: 'Camarão', preco: 32},
    {nome: 'Feijão', preco: 7.8}
];

const filtraValor = produto.filter(p => p.preco <= 12.5);
for (let i = 0; i < filtraValor.length; i++) {
    console.log(filtraValor[i]);
}
```

### 🔤 Filtrar nomes curtos

```javascript
const nomes = ['Ana', 'Carlos', 'Mel', 'Roberto'];
const nomesCurtos = nomes.filter(nome => nome.length <= 4);
console.log(nomesCurtos); // ['Ana', 'Mel']
```

### ➗ Filtrar números pares

```javascript
const numeros = [1, 2, 3, 4, 5, 6];
const pares = numeros.filter(n => n % 2 === 0);
console.log(pares); // [2, 4, 6]
```

---

## 💡 Como executar

1. Crie um arquivo `index.js`.
2. Cole o conteúdo do código.
3. Execute com Node.js:

```bash
node index.js
```

---

## 🛠️ Tecnologias

- JavaScript (ES6+)
- Node.js

---

## 📄 Licença

Este projeto está sob a licença MIT.
