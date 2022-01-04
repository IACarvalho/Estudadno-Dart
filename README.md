# Estudadno-Dart
## Variáveis
Dart possui variáveis estáticas e fortemente tipadas.
**Declaração de variáveis**
```dart
// Inteiro
int age = 29;

// String
String name = 'Israel Afonso';

// Booleano
bool isProgrammer = true;

// Arrays
List<String> petsNames = ['Noir', 'Odie'];
```

## Null-safety
 No Dart não aceita variáveis com valores nulos, e em alguns casos eu tenho que garantir que o valor não é nulo para fazer alguma ação, como por exemplo converter tipos. Pata não ter que testar valores de variáveis posso colocar uma esclamação (**!**) após a variável.
 ```dart
 // Aceitar valor nulo a força
 String nome?;
 
 // Garantiar que a variável não é nula
 nome =  'Israel';
 print(nome!);
 
 // Podemos usar uma forma de atribuir valor depois e nunca mais nulificar
 late String name;
 ```
 
## IF e SWITCH
A estrutura de **if** **else** do dart é bem semelhante a todas linguagens c like. **switch case** também.
```dart

// IF ELSE
int age = 29;
if(age >= 18){
  print('maior de idade');
}
else {
  print('menor de idade');
}

// SWITCH CASE
int diaDaSemana = 3;
switch(diaDaSemana){
  case 1:
    print('Domingo');
    break;
  case 2:
    print('Segunda');
    break;
  case 3:
    print('Terça');
    break;
  case 4:
    print('Quarta');
    break;
  case 5:
    print('Quinta');
    break;
  case 6:
    print('Sexta');
    break;
  case 7:
    print('Sábado');
    break;
  default:
    print('Valor inválido');
}
```

## Estruturas de repetição

Assim como as estruturas condicionais é bem semelhante com todas linguagens c like

```dart
// Taboada de 2 com FOR
for (int i = 1; i <= 10; i++) {
  print(i * 2);
}

// contagem regressiva WHILE
int count = 10;
while (count > 0) {
  print(count);
  count--;
}
```
## Metodos e classes
Criação de classe do dart funciona semelhante ao Java
É obrigatório eu especificar o retorno de meus métodos em dart, assim como em java ou c#.

```dart
class Pesso {
  // Ao usar final passa a responsabilidade de inicializar apra o construtor
  final String nome;
  final int idade;
  final double peso;
  final double altura;

  // construtor dart
  Pessoa(this.nome, this.idade, this.peso, this.altura);

  // metodo
  String toString() {
    return 'nome: $nome, idade: $idade, peso: $peso';
  }

  double calcularImc(){
    return peso/(altura * altura);
  }
}
```
## POO
Para declarar uma propriedade privadea em dart basta nomear a variável com um underscore(**_**) na frente do nome

Get e set em dart é um pouco diferente de linguagens como java e c#
```dart
class Carro{
	final String modelo;
	// variável privada
	String _segredo = 'Muito dinheiro';
	
	int _valor = 1000;
	
	Carro(this.modelo);
	
	// função get
	int get valorDoCarro => _valor;
	
	// setter
	void setValue(int valor) => +valor = valor;
}
```
## Interfaces, Herança e Polimorfismo
No dart NÃO tem interfaces, no lugar tem abstract classes que funcionam de forma semelhante. Para usar essa "interface" usa a palavra reservada **implements**

```dart
abstract class Pessoa {
  String comunicar();
}

class PessoaEt implements Pessoa {
  // como estou implementando uma classe abstrata sou obrigado a implementar o comunicar
  String comunicar() {
    return 'Olá mundo';
  }
}

class PessoaNaoET {
  String comunicar() {
    return 'Bom dia';
  }
}
```
Para usar herança no dart usa o **extends**
```dart
class Pessoa{
  String locomocao(){
    return 'Andar';
  }
}

class Programador extends Pessoa{
  // mesmo não tendo os métodos eu posso acessar o método locomoção
}
```

**Polimorfismo**

```dart
abstract Pagamento{
  void pagar();
}

class PagarComBoleto implements Pagamento {
  void pagar() {
    print('Pagar com boleto');
  }
}

class PagarComPix implements Pagar {
  void pagar() {
    print('Pagar com pix');
  }
}

Pagamento pagamento = PagarComBoleto();
pagamento.pagar();

// pode mudar para uma classe que sua a mesma interface

pagamento = PagarComPix();
pagamento.pagar();
```

## Future, Async e Await
```dart
void main() async {
  String nome = 'Israel Afonso'
  late String cep;
  // String cep = getCepByStreetName('Rua Marcelino de Melo');
  // print(cep);
  Future<String> cepFuture = getCepByStreetName('Rua Marcelino de Melo');

  cepFuture.then((result) => cep = result);

  print(cepFuture);
  print(cep);
}
// external service
Future<String> getCepByStreetName(String streetName){
  // Simulando requisição externa
  return Future.value('60833622');
}
```