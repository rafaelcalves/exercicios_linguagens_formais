---
tags: [Unisinos/2020/1/Linguagens Formais]
title: Trabalho GA
created: '2020-03-21T19:41:39.359Z'
modified: '2020-03-21T22:12:53.735Z'
---

# Trabalho GA
#### Alunos: Fabiane Kuhn e Rafael Corrêa
## 1. As seguir são apresentadas as regras de produção de uma gramática capaz de gerar uma linguagem de programação muito simples, cujo símbolo inicial é P:
$P \rightarrow\ LD\ \{LC\}$
$LD \rightarrow \varepsilon\ |\ D\ LD$
$D \rightarrow TV;$ 
$V \rightarrow x\ |\ y$
$T \rightarrow int | char$ 
$LC \rightarrow \varepsilon\ |\ C\ LC$
$C \rightarrow V=E;\ |\ if\ (V)\ \{LC\};\ |\ while\ (V)\ \{LC\};$
$E \rightarrow V\ |\ N$ 
$N \rightarrow 0\ |\ 1$
----------------------------------------------------
### Agora construa uma cadeia de derivação para os programas a seguir, gerados pela gramática acima:
- a) $\{x=1;\}$
$$
LD\{\undergroup{LC}\}\ =>\newline 
LD\{\undergroup{C}\ LC\}\ =>\newline 
LD\{\undergroup{V}=E;LC\} =>\newline 
LD\{x=\undergroup{E};LC\}\ =>\newline 
LD\{x=\undergroup{N};LC\} =>\newline 
\undergroup{LD}\{x=1;LC\} =>\newline 
\{x=1;\undergroup{LC}\}\ =>\newline 
\underbrace{\{x=1;\}}
$$

- b) $int\ x;\ int\ y;\ \{if\ (x)\ \{y=0\};\ x=1;\}$
$$
LD\{\undergroup{LC}\}\ =>\newline
LD\{\undergroup{C}\ LC\}\ =>\newline
LD\{if\ (\undergroup{V})\{LC\};\ LC\}\ =>\newline
LD\{if\ (x)\{\undergroup{LC}\};\ LC\}\ =>\newline 
LD\{if\ (x)\{\undergroup{C}\ LC\};\ LC\}\ =>\newline 
LD\{if\ (x)\{y=\undergroup{E};\ LC\};\ LC\}\ =>\newline 
LD\{if\ (x)\{y=\undergroup{N};\ LC\};\ LC\}\ =>\newline 
LD\{if\ (x)\{y=0\ \undergroup{LC}\};\ LC\}\ =>\newline 
LD\{if\ (x)\{y=0;\};\ \undergroup{LC}\}\ =>\newline 
LD\{if\ (x)\{y=0;\};\ \undergroup{C}\ LC\}\ =>\newline 
LD\{if\ (x)\{y=0;\};\ \undergroup{V}=E;\ LC\}\ =>\newline
LD\{if\ (x)\{y=0;\};\ x=\undergroup{E};\ LC\}\ =>\newline
LD\{if\ (x)\{y=0;\};\ x=\undergroup{N};\ LC\}\ =>\newline
LD\{if\ (x)\{y=0;\};\ x=1;\ \undergroup{LC}\}\ =>\newline
\undergroup{LD}\{if\ (x)\{y=0;\};\ x=1;\}\ =>\newline
\undergroup{D}\ LD\{if\ (x)\{y=0;\};\ x=1;\}\ =>\newline
\undergroup{T}V;\ LD\{if\ (x)\{y=0;\};\ x=1;\}\ =>\newline
int\ \undergroup{V};\ LD\{if\ (x)\{y=0;\};\ x=1;\}\ =>\newline
int\ x;\ \undergroup{LD}\{if\ (x)\{y=0;\};\ x=1;\}\ =>\newline
int\ x;\ \undergroup{D}\ LD\{if\ (x)\{y=0;\};\ x=1;\}\ =>\newline
int\ x;\ \undergroup{T}V;\ LD\{if\ (x)\{y=0;\};\ x=1;\}\ =>\newline
int\ x;\ int\ \undergroup{V};\ LD\{if\ (x)\{y=0;\};\ x=1;\}\ =>\newline
int\ x;\ int\ y;\ LD\{if\ (x)\{y=0;\};\ x=1;\}\ =>\newline
\underbrace{int\ x;\ int\ y;\ \{if\ (x)\{y=0;\};\ x=1;\}}
$$


2. Crie uma gramática para a linguagem {a
n
b
n
c
n
 | n≥0}
3. Crie autômatos finitos determinísticos que reconheçam as seguintes linguagens sobre o alfabeto
∑={0, 1} :
(a) {w | w possui 111 como subpalavra }
(b) {w | o sufixo de w é 000 }
(c) {w | o terceiro símbolo da direita para a esquerda de w é 1 }
4. Crie autômatos finitos não-determinísticos, com ou sem movimentos vazios, que reconheçam as
seguintes linguagens sobre o alfabeto ∑={a, b} :
(a) {w1w2w1 | w2 é qualquer palavra e |w1| = 3 }
(b) {w | o décimo símbolo da direita para esquerda de w é a }
