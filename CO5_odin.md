✅História e surgimento da linguagem;  
✅Paradigma e domínio de aplicação (onde / para o que é utilizada?);  
Escopo, variáveis e tipos de dados;  
Estruturas de controle (decisão e repetição);  
Funções/métodos;  
Características extras (como vantagens em relação às outras linguagens);  
Ambientes de desenvolvimento (IDES);  
Principais bibliotecas e frameworks;  
Curiosidades e cases de projetos que usam a linguagem.  
Exemplos breves.  

-----
### história do projeto? 
O projeto começou em uma noite no final de julho de 2016, quando Ginger Bill estava irritado com a programação em C++. A linguagem começou como um clone do Pascal (com begine ende mais), mas mudou rapidamente para se tornar algo diferente.

Bill tentou originalmente criar um pré-processador para C para ampliar e adicionar novos recursos à linguagem. No entanto, ele descobriu que essa empreitada era um beco sem saída. Naquela noite, Bill decidiu criar uma linguagem inteiramente nova do zero, em vez de tentar ampliar C.

Quais foram as principais influências no design da linguagem? #
A linguagem toma emprestado muito de (em ordem de filosofia e impacto): Pascal , C , Go , Oberon-2 , Newsqueak , GLSL .

Niklaus Wirth e Rob Pike foram os ídolos do design da linguagem de programação durante todo este projeto

----

### Quais são os princípios orientadores por trás do design de Odin? 

Simplicidade e legibilidade
Mínimo: deve haver uma maneira de escrever algo
Buscando a ortogonalidade
Os programas visam transformar dados em outras formas de dados
O código é sobre expressar algoritmos, não o sistema de tipos
Há conhecimento e sabedoria incorporados em linguagens de programação mais antigas
Toda a especificação da linguagem deveria ser possível de ser memorizada por um mero mortal

------

### A linguagem de programação Odin é mais utilizada
nichos específicos, como desenvolvimento de jogos, sistemas de baixa latência e ferramentas de sistemas, onde o desempenho e o controle de baixo nível são cruciais. Não é uma linguagem mainstream como Python ou JavaScript, mas tem uma comunidade ativa e crescente nesses setores. 
Em mais detalhes:
Desenvolvimento de jogos:
Odin tem sido adotada por alguns desenvolvedores de jogos devido à sua capacidade de produzir código de alta performance, comparável a C e C++, mas com uma sintaxe mais moderna e expressiva. 
Sistemas de baixa latência:
A linguagem é adequada para sistemas que exigem respostas rápidas e previsíveis, como servidores de negociação de alta frequência ou sistemas de tempo real. 
Ferramentas de sistemas:
Odin também é utilizada na criação de ferramentas de sistema, como compiladores, interpretadores e sistemas operacionais, onde o controle preciso sobre o hardware e a memória são importantes. 

-----


### Hellope! 
Para começar este passeio, vamos começar com uma versão modificada do famoso programa “hello world”:

```
package main

import "core:fmt"

main :: proc() {
	fmt.println("Hellope!")
}
```

----




