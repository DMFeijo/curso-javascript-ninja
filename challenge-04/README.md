# Desafio da semana #4

```js
/*
Declare uma variável chamada `isTruthy`, e atribua a ela uma função que recebe
um único parâmetro como argumento. Essa função deve retornar `true` se o
equivalente booleano para o valor passado no argumento for `true`, ou `false`
para o contrário.
*/
var isTruthy = function(param) {
    return !!param;
};

// Invoque a função criada acima, passando todos os tipos de valores `falsy`.
isTruthy(false);
isTruthy(null);
isTruthy(undefined);
isTruthy('');
isTruthy(0);
isTruthy(-0);
isTruthy(NaN);

/*
Invoque a função criada acima passando como parâmetro 10 valores `truthy`.
*/
isTruthy(true)
isTruthy(1)
isTruthy('Teste')
isTruthy({})
isTruthy([])
isTruthy(function() {})
isTruthy('Daniel')
isTruthy(10 + 10)
isTruthy([1, 2, 3])
isTruthy(10/2)
isTruthy({a: 1, b: 2, c: 3})

/*
Declare uma variável chamada `carro`, atribuindo à ela um objeto com as
seguintes propriedades (os valores devem ser do tipo mostrado abaixo):
- `marca` - String
- `modelo` - String
- `placa` - String
- `ano` - Number
- `cor` - String
- `quantasPortas` - Number
- `assentos` - Number - cinco por padrão
- `quantidadePessoas` - Number - zero por padrão
*/
var carro = {
    marca: 'volkswagen',
    modelo: 'Fusca',
    placa: 'ABC-1234',
    ano: 1978,
    cor: 'Preto',
    quantasPortas: 2,
    assentos: 5,
    quantidadePessoas: 0
}

/*
Crie um método chamado `mudarCor` que mude a cor do carro conforme a cor
passado por parâmetro.
*/
carro.mudarCor = function(cor) {
     carro.cor = cor;
}

/*
Crie um método chamado `obterCor`, que retorne a cor do carro.
*/
carro.obterCor = function() {
    return carro.cor;
}

/*
Crie um método chamado `obterModelo` que retorne o modelo do carro.
*/
carro.obterModelo = function () {
    return carro.modelo;
}

/*
Crie um método chamado `obterMarca` que retorne a marca do carro.
*/
carro.obterMarca = function () {
    return carro.marca;
}

/*
Crie um método chamado `obterMarcaModelo`, que retorne:
"Esse carro é um [MARCA] [MODELO]"
Para retornar os valores de marca e modelo, utilize os métodos criados.
*/
carro.obterMarcaModelo = function () {
    return 'Esse carro é um ' + carro.obterMarca() + ' ' + carro.modelo() + '!'
}

/*
Crie um método que irá adicionar pessoas no carro. Esse método terá as
seguintes características:
- Ele deverá receber por parâmetro o número de pessoas entrarão no carro. Esse
número não precisa encher o carro, você poderá acrescentar as pessoas aos
poucos.
- O método deve retornar a frase: "Já temos [X] pessoas no carro!"
- Se o carro já estiver cheio, com todos os assentos já preenchidos, o método
deve retornar a frase: "O carro já está lotado!"
- Se ainda houverem lugares no carro, mas a quantidade de pessoas passadas por
parâmetro for ultrapassar o limite de assentos do carro, então você deve
mostrar quantos assentos ainda podem ser ocupados, com a frase:
"Só cabem mais [QUANTIDADE_DE_PESSOAS_QUE_CABEM] pessoas!"
- Se couber somente mais uma pessoa, mostrar a palavra "pessoa" no retorno
citado acima, no lugar de "pessoas".
*/
carro.adicionarPessoas = function (numeroPessoas) {
    var totalPessoas = carro.quantidadePessoas + numeroPessoas;

    if (carro.quantidadePessoas === carro.assentos && totalPessoas >= carro.assentos) {
        return 'O carro já está lotado!'
    }

    if (totalPessoas > carro.assentos) {
        var quantasPessoasCabem = carro.assentos - carro.quantidadePessoas;
        var PluralouSingular = quantasPessoasCabem === 1 ? 'pessoa' : 'pessoas';

        return 'Só cabem mais ' + quantasPessoasCabem + ' ' + PluralouSingular + ' no carro!'
    }

    carro.quantidadePessoas += numeroPessoas
    return 'Já temos ' + carro.quantidadePessoas + ' pessoas no carro!'
}

/*
Agora vamos verificar algumas informações do carro. Para as respostas abaixo,
utilize sempre o formato de invocação do método (ou chamada da propriedade),
adicionando comentários _inline_ ao lado com o valor retornado, se o método
retornar algum valor.

Qual a cor atual do carro?
*/
carro.obterCor(); //Preto

// Mude a cor do carro para vermelho.
carro.mudarCor('Vermelho');

// E agora, qual a cor do carro?
carro.obterCor(); //'Vermelho'

// Mude a cor do carro para verde musgo.
carro.mudarCor('Verde Musgo');

// E agora, qual a cor do carro?
carro.obterCor(); //'Verde Musgo'

// Qual a marca e modelo do carro?
carro.obterMarcaModelo(); //'Esse carro é um volkswagen Fusca!'

// Adicione 2 pessoas no carro.
carro.adicionarPessoas(2) //'Já temos 2 pessoas no carro!'

// Adicione mais 4 pessoas no carro.
carro.adicionarPessoas(4) //'Só cabem mais 3 pessoas no carro!'

// Faça o carro encher.
carro.adicionarPessoas(3) //'Já temos 5 pessoas no carro!'

// Tire 4 pessoas do carro.
carro.adicionarPessoas(-4) //'Já temos 1 pessoas no carro!'

// Adicione 10 pessoas no carro.
carro.adicionarPessoas(10) //'Só cabem mais 4 pessoas no carro!'

// Quantas pessoas temos no carro?
carro.quantidadePessoas //1
```
