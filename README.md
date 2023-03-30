- [Estudos em C](#estudos-em-c)
- [Syntax](#syntax)
  - [Comentários](#comentários)
  - [Esqueleto Padrão](#esqueleto-padrão)
  - [Comandos de repetição](#comandos-de-repetição)
  - [Desvios incondicionais (break, continue, goto)](#desvios-incondicionais-break-continue-goto)
  - [Operadores](#operadores)
    - [Operadores bit a bit](#operadores-bit-a-bit)
  - [Declaração de variáveis](#declaração-de-variáveis)
    - [Tipos de variáveis:](#tipos-de-variáveis)
      - [typedef](#typedef)
      - [sizeof()](#sizeof)
    - [Modificadores](#modificadores)
      - [Sinônimos](#sinônimos)
  - [Atribuição de valor](#atribuição-de-valor)
  - [Casting](#casting)
  - [Ponteiros](#ponteiros)
- [Bibliotecas](#bibliotecas)
  - [\<STDIO.H\>](#stdioh)
    - [printf()](#printf)
      - [Especificação de conversão:](#especificação-de-conversão)
      - [\[flags\]](#flags)
      - [\[largura\]](#largura)
      - [\[.precisão\]](#precisão)
      - [\[tamanho\] (Placeholders)](#tamanho-placeholders)
    - [puts()](#puts)
    - [scanf()](#scanf)
      - [Especificadores de conversão](#especificadores-de-conversão)
      - [Flags](#flags-1)
    - [fgets()](#fgets)
- [Funções](#funções)
  - [Criação de funções](#criação-de-funções)
  - [printf()](#printf-1)
  - [Funções importantes](#funções-importantes)
    - [Limpar entrada (p/ usar fgets)](#limpar-entrada-p-usar-fgets)
    - [Ler texto (fgets + tira o ENTER)](#ler-texto-fgets--tira-o-enter)

# Estudos em C
- ### [Udemy](https://www.udemy.com/course/curso-algoritmos-logica-de-programacao/)
- ### [Youtube Playlist - Ponteiros (Canal De aluno para aluno)](https://youtube.com/playlist?list=PLa75BYTPDNKbhUVggmU3JUEBPibvh0C2t)

# Syntax

## Comentários

```c
// Comentários na linha utilizam "//"

/*
 * Comentários em várias linhas
 * utilizam no início "/*"
 * e no fim o inverso
 */
```
## Esqueleto Padrão

```c
int main()
{
    return 0;
}
```

## Comandos de repetição

if()
```c
if(condição)
{    
    // Sentenças
}
else if(condição 2)
{
    // Sentenças
}
else
{
    // Sentenças
}
```

Ternário
```c
condição ? verdadeiro : falso
```
while
```c
while(condição)
{
    // Sentenças
}
```

do
```c
do
{
    // Sentenças
} while (condição);
// No "do" o teste é feito depois, então executará ao menos 1x
```

for
```c
for(inicio; condição; incremento)
{
    // Sentenças
}
/* Omitindo argumentos:
 * for(;;)
 * 
 * Caso uma variável seja definida dentro do for
 * seu escopo será apenas o for
 */

// Equivalencia do for em while
inicio;
while (condição)
{
    // Sentenças
    incremento;
}
```

switch
```c
switch (expressão_integral)
{
    case constante_integral:
        // Sentenças

    case constante_integral:
        // Sentenças

    default:
        // Sentenças
}
```

## Desvios incondicionais (break, continue, goto)

Não recomendado por quebrar fluxo de comandos e piorar legibilidade
```c
break; // Termina uma repetição ou switch

continue; // Interrompe apenas uma iteração, voltando pro teste
// Pode ser usado em for, while e do

goto identificador;
// Salta para uma sentença rotulada, por exemplo
identificador : sentença;
```

## Operadores

    + -> Adição
    - -> Subtração
    * -> Multiplicação
    / -> Divisão
    % -> Resto da divisão ("mod")

    >  -> Maior
    <  -> Menor
    >= -> Maior ou igual
    <= -> Menor ou igual
    == -> Igual
    != -> Diferente
    ...
    var op= expressão equivale a var = var op expressão
    Ex: i /= 2 equivale a i = i/2

    && -> e
    || -> ou
    !  -> não
    Obs: && e || param de executar se o resultado puder ser decidido

    ++ -> Incremento
    -- -> Decremento
    Obs: n++ != ++n
    n++ incrementa depois de executar, enquanto ++n incrementa antes de executar

Exemplo:
```c
n = 5;
x = n++;
// x = 5 e n = 6

n = 5;
x = ++n;
// x = 6 e n = 6
```

### Operadores bit a bit

Se aplicam a tipos integrais
Aplicam a operação bit a bit

    & -> and
    | -> or
    ^ -> xor
    ~ -> not
    << -> Deslocamento à esquerda
    >> -> Deslocamento à direita

Exemplo:
```
  1011 0101
& 1111 0110
  ---------
  1011 0100

  1011 0101
| 1111 0110
  ---------
  1111 0111

  1011 0101
       << 1
  ---------
  0110 1010
OBS: Deslocar p/ a esquerda é equivalente a multiplicar por 2

  1011 0101
       >> 1
  ---------
  0101 1010
```

## Declaração de variáveis

    qualificador* modificador* tipo nome1, nome2, ...;

### Tipos de variáveis:

```c
int
float
double
char
char vetor[n]
char matriz[m][n]
```

#### typedef

```c
typedef int inteiro; // Cria o sinônimo "inteiro" para int
typedef unsigned int natural; // Cria o sinônimo "natural" para int
```

#### sizeof()
Retorna um inteiro indicando quantos bytes tem seu argumento
```c
sizeof(int) // Retorna o n° de bytes para o tipo "int"
sizeof(n) // Retorna o n° de bytes para a variável "n"
```

### Modificadores

    short     -> int
        Geralmente o compilador armazena menos espaço

    long      -> int e double
        Geralmente o compilador armazena mais espaço

    long long -> int

    unsigned  -> char e int
        Inteiro sem sinal (0+)

    signed    -> char e int
        Inteiro com sinal


#### Sinônimos

    int = signed int
    short = short int
    long = long int
    long long = long long int
    unsigned = unsigned int
    signed = signed int = int

## Atribuição de valor

```c
int a = 5;
double b = 2.5;
char c = 'V';
strcpy(nome, "Carlos");
```

## Casting

```c
int x;
double y;

y = (tipo) x;
```


## Ponteiros

```c
tipo *ponteiro; // Declara um ponteiro
ponteiro = &x;  // APONTA o ponteiro para o endereço de memória (&) da variável "x"
*ponteiro = y;  // O VALOR do ponteiro apontando pra a variável "x" vai ser o valor da variável "y"
x = *ponteiro // variável "x" recebe o VALOR APONTADO pelo ponteiro

tipo *ponteiro =  &x // Declara o ponteiro e já aponta para o endereço da variável "x"
```

# Bibliotecas

## <b><STDIO.H></b>

### <b>printf()</b>
Saída formatada
```c
int printf(const char *fmt, ...)
// Imprime os parâmetros na lista ... em stdout usando a cadeia fmt para determinar como
// Retorna: número de caractéres impressos ou um número negativo se houver erro
```

#### <b>Especificação de conversão:</b>

%[flags][largura][.precisão][tamanho]conversão

#### <b>[flags]</b>

    0   -> Usa zeros ao invés de espaços para alinhar à direita
    -   -> Alinha à esquerda
    +   -> Sempre acrescente o sinal de + ou -
    " " -> Acrescenta um espaço antes de um número positivo
    #   -> Forma alternativa para g,G,f,F,e,E,o,x,X

#### <b>[largura]</b>

Substitui "*" com a quantidade necessária entregue pelos argumentos
```c
printf("%*d", largura, var) // Imprime "var" com * <- largura
// Adicionará espaços em branco se necessário, se não, imprimirá o n° normalmente

printf("%*.*f", largura, precisao, var) // Imprime "var" com largura e precisão
```

#### <b>[.precisão]</b>

Conversões d, i, o, u, x, X: Número mínimo de dígitos que deve ser mostrado

Conversões a, A, e, E, f, F: Número mínimo à direita da vírgula

Conversões g, G: Número máximo de dígitos significativos

Conversões s, S: Número máximo de caracteres impressos

#### <b>[tamanho]</b> (Placeholders)

    %d/%i -> int
    %f    -> float
    %lf   -> double
    %c    -> char
    %s    -> cadeia
    %p    -> endereço


    %u    -> unsigned int

    %hi   -> short int
    %hu   -> short int (unsigned)

    %li   -> long int
    %lu   -> long int (unsigned)

    %lli  -> long long int
    %llu  -> long long int (unsigned)

    %e  -> (float) Notação científica (Ex: 3.16e7 = 3.16*10^7)
    %le -> (double) Notação científica

    %Lf -> long double
    
    %x -> Número hexadecimal

### <b>puts()</b>

```c
puts(""); // print de apenas uma string
```

### <b>scanf()</b>
Entrada formatada
```c
int scanf(const char *fmt, ...)
// Usa a cadeia de formato fmt e armazena na lista de endereços ...
// Retorna o n° de variáveis convertidas ou EOF se algo impedir a conversão
```

#### Especificadores de conversão

    %d   -> Inteiro decimal com sinal
    %i   -> Dec, Hexa ou Octal com sinal
    %u   -> Decimal sem sinal
    %o   -> Octal sem sinal
    %x/X -> Hexadecimal sem sinal
    %s   -> Cadeia sem brancos
    %c   -> Cadeia de tamanho w
    
    %[""]  -> Cadeia com apenas os carac. especificados
    %[^""] -> Cadeia sem os carac. especificados
    $p     -> void
    %n     -> Nada. Armazena o n° de carac. já lidos
    %e/E/f/g -> Número em ponto flutuante com sinal

    Obs: d, i, f, s consomem brancos, já c e [ não

#### Flags

    *  -> O campo deve ser lido mas não armazenado
    n° -> Limita o número de dígitos lidos com i/f ou símbolos com s
    '  -> Com números, especifica que há separadores de milhar
    m  -> Com cadeias, faz com que a memória suficiente para a cadeia seja alocada

### fgets()

```c
fgets(var, lenght, stdin); // textos e digitos até a quebra de linha (c/ espaço)
```

# Funções

## Criação de funções

```c
tipo|void nome(args)
{
  // Sentenças

  return var;
}
// Obs: void é usado quando a função não retornará nada
```

## printf()





## Funções importantes
### Limpar entrada (p/ usar fgets)

```c
/*
 * Usar para limpar entrada antes do fgets
 */

void limpar_entrada()
{
    char c;
    while ((c = getchar()) != '\n' && c != EOF) {}
}
```
### Ler texto (fgets + tira o ENTER)

```c
/*
 * Usar para ler texto fgets e tirar a quebra de linha causada pelo ENTER
 * (não dispensa o limpar entrada)
 * Necessita da biblioteca string.h
 */

#include <string.h>

void ler_texto(char *var, int lenght)
{
    fgets(var, lenght, stdin);
    strtok(var, "\n");
}
```