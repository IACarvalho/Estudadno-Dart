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
