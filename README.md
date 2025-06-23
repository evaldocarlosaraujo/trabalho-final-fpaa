# 📘 Trabalho Final – Fundamentos de Projeto e Análise de Algoritmos (FPAA)

Este repositório contém a solução para o trabalho final da disciplina **Fundamentos de Projeto e Análise de Algoritmos (FPAA)**. O projeto tem como objetivo resolver um problema utilizando **programação dinâmica** e **backtracking**, aplicando os conceitos estudados em aula.

---

## 🧠 Descrição da Solução

A solução proposta tem como objetivo resolver o problema da Maior Subsequência Comum (LCS) entre duas cadeias de caracteres fornecidas pelo usuário. Para isso, foi utilizada uma abordagem híbrida, combinando programação dinâmica para calcular o comprimento da LCS e backtracking para recuperar todas as subsequências comuns possíveis com esse comprimento.

A interface foi desenvolvida em Windows Forms (C#), proporcionando uma experiência visual amigável para entrada de dados e exibição dos resultados. O usuário pode inserir duas sequências e visualizar tanto o tamanho da LCS quanto todas as subsequências comuns encontradas.

A matriz dp armazena os valores parciais da LCS para subproblemas, otimizando o tempo de execução. Já a técnica de backtracking é aplicada sobre essa matriz para reconstruir todas as possíveis LCS de forma correta, mesmo em casos onde múltiplas subsequências possuem o mesmo comprimento.

## ❓ Perguntas

### 1. Como a programação dinâmica foi aplicada na solução?

A programação dinâmica foi usada para calcular a maior subsequência comum (LCS) entre duas sequências de caracteres. Foi construída uma matriz dp[m+1][n+1], onde m e n são os tamanhos das strings de entrada. Cada célula dp[i][j] armazena o comprimento da LCS entre os prefixos s1[0..i-1] e s2[0..j-1]. O preenchimento dessa matriz foi feito com base na comparação entre os caracteres e o uso do resultado de subproblemas menores, evitando repetições de cálculo.

### 2. Por que o uso de backtracking é necessário neste problema?

A programação dinâmica fornece apenas o comprimento da LCS. Para reconstruir todas as subsequências comuns de maior comprimento, é necessário explorar todos os caminhos possíveis na matriz dp que mantêm esse valor ótimo. O backtracking permite percorrer a matriz de trás para frente (da última célula até a origem), reconstruindo todas as sequências que formam a LCS. Esse processo garante que todas as soluções corretas sejam encontradas.

### 3. Houve desafios na implementação? Quais? Como foram superados?

Principais desafios:

Validação das entradas: Garantir que as strings contivessem apenas letras minúsculas e até 80 caracteres.

Solução: Implementação da função IsValidSequence.

Interface gráfica com posicionamento dinâmico: Centralizar e alinhar todos os controles no formulário do Windows Forms.

Solução: Uso de Panel, manipulação do evento Resize, Anchor e cálculos manuais de Location.

Backtracking com múltiplas soluções: Manter controle para evitar LCS duplicadas.

Solução: Uso de HashSet<string> para armazenar subsequências únicas.


### 4. Qual é a complexidade da solução proposta?

#### a) Versão utilizando apenas programação dinâmica:

Preenchimento da matriz dp:

Tamanho da matriz: (m+1) x (n+1)

Tempo por célula: O(1)

Complexidade total: O(m * n)


#### b) Versão que combina programação dinâmica com backtracking:

Programação dinâmica: O(m * n) (mesmo cálculo acima)

Backtracking:

No pior caso, pode haver exponencialmente muitas subsequências (até 2^L, onde L é o comprimento da LCS).

Cada chamada de BacktrackLCS pode bifurcar em até 2 chamadas recursivas.

Complexidade de tempo total no pior caso: O(2^L) (para a parte de reconstrução).

Complexidade combinada: O(m * n + k), onde k é o número de subsequências de LCS geradas.

### 5. O que o grupo aprendeu ao resolver esse problema?

Como aplicar programação dinâmica para resolver problemas de subsequências.

A importância de armazenar subproblemas para evitar recomputações e melhorar a eficiência.

Como backtracking permite recuperar as soluções completas a partir da matriz dp.

Como implementar interfaces gráficas em Windows Forms com posicionamento dinâmico e responsivo.

A necessidade de validações e tratamento de entradas para garantir robustez do sistema.

A prática de estruturas de dados como HashSet e List para controle de duplicatas e ordenação de resultados.
