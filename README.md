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
 No Dart não aceita variáveis com valores nulos, e em alguns casos eu tenho que garantir que o valor não é nulo para fazer alguma ação, como por exemplo converter tipos. Pata não ter que testar valores de variáveis posso colocar uma esclamação após a variável.
 ```dart
 // Aceitar valor nulo a força
 String nome?;
 
 // Garantiar que a variável não é nula
 nome =  'Israel';
 print(nome!);
 
 // Podemos usar uma forma de atribuir valor depois e nunca mais nulificar
 late String name;
 ```