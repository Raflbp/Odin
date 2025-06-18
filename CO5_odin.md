# História e surgimento da linguagem

### ✅história do projeto? 
O projeto começou em uma noite no final de julho de 2016, quando Ginger Bill estava irritado com a programação em C++. A linguagem começou como um clone do Pascal (com begine ende mais), mas mudou rapidamente para se tornar algo diferente.

Bill tentou originalmente criar um pré-processador para C para ampliar e adicionar novos recursos à linguagem. No entanto, ele descobriu que essa empreitada era um beco sem saída. Naquela noite, Bill decidiu criar uma linguagem inteiramente nova do zero, em vez de tentar ampliar C.

Quais foram as principais influências no design da linguagem? #
A linguagem toma emprestado muito de (em ordem de filosofia e impacto): Pascal , C , Go , Oberon-2 , Newsqueak , GLSL .

Niklaus Wirth e Rob Pike foram os ídolos do design da linguagem de programação durante todo este projeto

### ✅Quais são os princípios orientadores por trás do design de Odin? 

Simplicidade e legibilidade
Mínimo: deve haver uma maneira de escrever algo
Buscando a ortogonalidade
Os programas visam transformar dados em outras formas de dados
O código é sobre expressar algoritmos, não o sistema de tipos
Há conhecimento e sabedoria incorporados em linguagens de programação mais antigas
Toda a especificação da linguagem deveria ser possível de ser memorizada por um mero mortal


------

# ✅ Paradigma e domínio de aplicação (onde / para o que é utilizada?)

### A linguagem de programação Odin é mais utilizada
nichos específicos, como desenvolvimento de jogos, sistemas de baixa latência e ferramentas de sistemas, onde o desempenho e o controle de baixo nível são cruciais. Não é uma linguagem mainstream como Python ou JavaScript, mas tem uma comunidade ativa e crescente nesses setores. 
Em mais detalhes:
Desenvolvimento de jogos:
Odin tem sido adotada por alguns desenvolvedores de jogos devido à sua capacidade de produzir código de alta performance, comparável a C e C++, mas com uma sintaxe mais moderna e expressiva. 
Sistemas de baixa latência:
A linguagem é adequada para sistemas que exigem respostas rápidas e previsíveis, como servidores de negociação de alta frequência ou sistemas de tempo real. 
Ferramentas de sistemas:
Odin também é utilizada na criação de ferramentas de sistema, como compiladores, interpretadores e sistemas operacionais, onde o controle preciso sobre o hardware e a memória são importantes. 

------
# ✅Escopo, variáveis e tipos de dados; 

// Para começar este passeio, vamos começar com uma versão modificada do famoso programa “hello world”:

// O core:prefixo é usado para indicar onde a importação deve procurar; isso é chamado de coleção de biblioteca. Se nenhum prefixo estiver presente, a importação procurará em relação ao arquivo atual.

```
package main

import "core:fmt"

main :: proc() {
	fmt.println("Hellope!")
```

#  Criação de um pacote 

Um pacote é um diretório de arquivos de código Odin, todos com a mesma declaração de pacote no topo, por exemplo package main, . Cada arquivo .odin deve ter o mesmo nome de pacote. Um diretório não pode conter mais de um pacote

### Números 
Literais numéricos são escritos de forma semelhante à maioria das outras linguagens de programação. Um recurso útil no Odin é que sublinhados são permitidos para melhor legibilidade: 1_000_000_000(um bilhão). Um número que contém um ponto é um literal de ponto flutuante: 1.0e9(um bilhão). Se um literal numérico for sufixado com i, é um literal numérico imaginário: 2i(2 multiplicado pela raiz quadrada de -1).

Literais binários são prefixados com 0b, literais octais com 0o, e literais hexadecimais com 0x. Um zero à esquerda não produz uma constante octal (ao contrário de C).

No Odin, se uma constante numérica puder ser representada por um tipo sem perda de precisão, ela será automaticamente convertida para esse tipo.

```
x: int = 1.0 // A float literal but it can be represented by an integer without precision loss
```

Literais constantes são “não tipados”, o que significa que podem ser convertidos implicitamente em um tipo.


```
x: int // `x` is typed as being of type `int`
x = 1 // `1` is an untyped integer literal which can implicitly convert to `int`
```

### Declarações de variáveis ​​

Uma declaração de variável declara uma nova variável para o escopo atual.

```
x: int // declares `x` to have type `int`
y, z: int // declares `y` and `z` to have type `int`
As variáveis ​​são inicializadas como zero por padrão, a menos que especificado de outra forma.
```

Observação: as declarações devem ser exclusivas dentro de um escopo.

```
x := 10
x := 20 // Redeclaration of `x` in this scope
y, z := 20, 30
test, z := 20, 30 // not allowed since `z` exists already
```

### Declarações de atribuição 
A instrução de atribuição atribui um novo valor a uma variável/local:

```
x: int = 123 // declares a new variable `x` with type `int` and assigns a value to it
x = 637 // assigns a new value to `x`
```
=é o operador de atribuição.
Você pode atribuir múltiplas variáveis ​​com ele:
```
x, y := 1, "hello" // declares `x` and `y` and infers the types from the assignments
y, x = "bye", 5
```

Nota: := são dois tokens, :e =. Os seguintes são todos equivalentes:
```
x: int = 123
x:     = 123 // default type for an integer literal is `int`
x := 123
```

### Declarações constantes 

Constantes são entidades (símbolos) que possuem um valor atribuído. O valor da constante não pode ser alterado. O valor da constante deve poder ser avaliado em tempo de compilação:
```
x :: "what" // constant `x` has the untyped string value "what"
```

Constantes podem ser explicitamente digitadas como uma declaração de variável:
```
y : int : 123
z :: y + 7 // constant computations are possible
```
------
# ✅Estruturas de controle (decisão e repetição);  

### Loop básico 

Um loop básico fortem três componentes separados por ponto e vírgula:

A declaração inicial: executada antes da primeira iteração
A expressão de condição: avaliada antes de cada iteração
A instrução post: executada no final de cada iteração
O loop parará de ser executado quando a condição for avaliada como false.

```
for i := 0; i < 10; i += 1 {
	fmt.println(i)
}
```

As instruções initial e post são opcionais:


```
i := 0
for ; i < 10; {
	i += 1
}
```

Esses pontos e vírgulas podem ser omitidos. Este forloop é equivalente ao loop de C while:
```
i := 0
for i < 10 {
	i += 1
}
```
Se a condição for omitida, isso produzirá um loop infinito:
```
for {

}
```

Para loop baseado em intervalo 
```
O loop for básico

for i := 0; i < 10; i += 1 {
	fmt.println(i)
}
```
Também pode ser escrito
```
for i in 0..<10 {
	fmt.println(i)
}
// or
for i in 0..=9 {
	fmt.println(i)
}
```

### if declaração 
As declarações de Odin ifnão precisam estar entre parênteses, ( )mas { }sim doentre chaves.




```
if x >= 0 {
	fmt.println("x is positive")
}
```
Assim como for, a ifinstrução pode começar com uma instrução inicial a ser executada antes da condição. Variáveis ​​declaradas pela instrução inicial estão apenas no escopo dessa ifinstrução
.
```
if x := foo(); x < 0 {
	fmt.println("x is negative")
}
```

Variáveis ​​declaradas dentro de uma ifinstrução inicial também estão disponíveis para qualquer um dos elseblocos:

```
if x := foo(); x < 0 {
	fmt.println("x is negative")
} else if x == 0 {
	fmt.println("x is zero")
} else {
	fmt.println("x is positive")
}
```

Uma instrução switch é outra maneira de escrever uma sequência de instruções if-else. Em Odin, o caso padrão é denotado como um caso sem nenhuma expressão.

```
switch arch := ODIN_ARCH; arch {
case .i386, .wasm32, .arm32:
	fmt.println("32 bit")
case .amd64, .wasm64p32, .arm64, .riscv64:
	fmt.println("64 bit")
case .Unknown:
	fmt.println("Unknown architecture")
}
```
Uma switchinstrução sem condição é o mesmo que switch true. Isso pode ser usado para escrever uma cadeia if-else limpa e longa e ter a capacidade de, breakse necessário


```
switch {
case x < 0:
	fmt.println("x is negative")
case x == 0:
	fmt.println("x is zero")
case:
	fmt.println("x is positive")
}
```

Uma switch instrução também pode usar intervalos como um loop baseado em intervalos:

```
switch c {
case 'A'..='Z', 'a'..='z', '0'..='9':
	fmt.println("c is alphanumeric")
}


switch x {
case 0..<10:
	fmt.println("units")
case 10..<13:
	fmt.println("pre-teens")
case 13..<20:
	fmt.println("teens")
case 20..<30:
	fmt.println("twenties")
}
```

### defer declaração 


Uma instrução defer adia a execução de uma instrução até o final do escopo em que ela está.

O seguinte será impresso 4então 234:

```
package main

import "core:fmt"

main :: proc() {
	x := 123
	defer fmt.println(x)
	{
		defer x = 4
		x = 2
	}
	fmt.println(x)

	x = 234
}
```

### when declaração 
A whendeclaração é quase idêntica à ifdeclaração, mas com algumas diferenças:

Cada condição deve ser uma expressão constante, pois uma wheninstrução é avaliada em tempo de compilação.
As instruções dentro de um branch não criam um novo escopo
O compilador verifica a semântica e o código apenas para declarações que pertencem à primeira condição que étrue
Uma declaração inicial não é permitida em uma whendeclaração
whendeclarações são permitidas no escopo do arquivo
Exemplo:

```
when ODIN_ARCH == .i386 {
	fmt.println("32 bit")
} else when ODIN_ARCH == .amd64 {
	fmt.println("64 bit")
} else {
	fmt.println("Unsupported architecture")
}
```

### break declaração 
Um laço for ou uma instrução switch podem ser deixados prematuramente com uma breakinstrução. Eles deixam a construção mais interna, a menos que um rótulo de construção seja fornecido

### fallthrough statement 
Odin’s switch is like the one in C or C++, except that Odin only runs the selected case. This means that a break statement is not needed at the end of each case. Another important difference is that the case values need not be integers nor constants.
------

# Funções/métodos;  

-----

# Características extras (como vantagens em relação às outras linguagens);  

------

# Ambientes de desenvolvimento (IDES);  

-----

# ✅Principais bibliotecas e frameworks;  

https://github.com/odin-lang/Odin/wiki/Odin-Libs


-----------------------------------------------------------------------------------------------------------------------
# ✅Curiosidades sobre a Linguagem Odin:

### ✅Nome da Linguagem 

O nome "Odin" foi escolhido como referência ao deus da mitologia nórdica, símbolo de força, sabedoria e poder.  

A escolha não teve relação direta com as funções da linguagem, mas sim com a ideia de um nome forte, marcante e culturalmente simbólico.
	A linguagem não possui um mascote oficial. Seu logotipo é um símbolo abstrato, inspirado na arte nórdica, com traços que lembram nós vikings.
Apesar de muitos na comunidade associarem o símbolo a uma serpente ou à Jörmungandr, oficialmente ele foi criado apenas por questões estéticas e de identidade visual.

Projetos Desenvolvidos com Odin:

EmberGen (JangaFX)
	Primeiro grande projeto comercial feito 100% em Odin.
	Software de simulação de fumaça e fogo em tempo real, usado em jogos e filmes.
	Entre os clientes estão estúdios como Bethesda, Capcom, Weta Digital e CD Projekt Red.

CAT & ONION (Steam)
	Primeiro jogo desenvolvido em Odin e lançado na Steam.
	Importante marco para a linguagem no mundo dos jogos independentes.

Spall (Profiler)
	Ferramenta de profiling e análise de performance.
	Muito utilizada por desenvolvedores de jogos e motores gráficos para otimização de desempenho.

---------------------------------

# Referencias:

https://odin-lang.org/docs/overview/  
https://github.com/odin-lang/Odin/wiki/Odin-Libs  

