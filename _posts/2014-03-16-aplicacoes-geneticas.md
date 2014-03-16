---
layout: post
title: "Como a estatística pode ajudar as pesquisas sobre o câncer?"
categories: []
tags: []
fullview: true
---
{% include JB/setup %}

Dei o pontapé inicial no blog, mas a falta de tempo não deixou que eu desse continuidade. Para não deixar essa ideia de divulgação das aplicações da estatística morrer, resolvi escrever sobre um dos projetos aos quais estou me dedicando, que é o uso da estatística no estudo de dados genômicos.

Meu intuito não é falar sobre a estatística envolvida no processo, mas apenas dar uma idéia do que é o estudo de dados de expressão genética e explicar qual a importância da estatística para essa área.

### O câncer e o estudo de expressões genéticas

O câncer é uma doença caracterizada pela multiplicação descontrolada de algumas células, formando tumores e invadindo órgãos e tecidos. Esse crescimento desordenado acontece quando ocorre alguma mutação nos genes que controlam a reprodução celular.

Quase todas as nossas células carregam todo o genoma humano. Entretanto, em um dado momento, apenas alguns genes estão se expressando e, consequentemente, atuando em nosso corpo. Identificar quais genes estão atuando em uma célula cancerígena é um passo importante no estudo da doença. Chamamos essa análise de **gene expression profiling**.

Para um gene se expressar, o seu código precisa ser sintetizado como mRNA (RNA mensageiro). Portanto, para saber se um gene está ativo ou não em uma determinada célula, precisamos olhar para os seus mRNA's.

Os dados de **microarray** representam justamente essa expressão genética e ajudam a identificar quais os genes estão ativos em uma determinada célula. Entretanto, apesar de carregar muita informação útil, esse tipo de dado possui muito ruído e variabilidade. Variações no scanner utilizado para a "leitura" dos dados, variações na concentração das soluções de hibridização e vários outros fenômenos dificultam a interpretação dos dados pelos cientistas.

Além disso, o número de variáveis (são analisados de 20.000 a 50.000 genes, cada um composto por 20 a 40 probes) é muito maior do que o número de amostras (alguma coisa em torno de 100 amostras), em virtude do alto custo para se produzir esse tipo de dado.

Para lidar com essas adversidades, precisamos adotar um modelo estatístico capaz de lidar muito bem com a variabilidade dos dados e que ainda consiga capturar padrões, apesar do pequeno tamanho da amostra.

![Microarray](/assets/img/combined_matrices.png)

As imagens acima representam dados de microarray. Nas linhas temos o que chamamos de **probes**, que são pedaços de sequência genética, e nas colunas temos as diferentes amostras.

Quando identificamos um padrão, como na imagem da esquerda, temos uma evidência de que o gene representado nessa imagem está ativo. Quando os dados são aleatórios e não apresentam nenhum padrão, como vemos na imagem da direita, isso sugere que o gene não está ativo nesta célula.

### O modelo fatorial latente esparso (SLFM)

Estou atualmente trabalhando no estudo e desenvolvimento do Modelo Fatorial Esparso Latente (SLFM), que consegue lidar muito bem com essas particularidades. Separando o ruído e detectando fatores latentes nos dados, ele consegue informar, com bastante precisão, a probabilidade de existencia de padrões que evidenciem a atividade de um determinado gene.

![Microarray](/assets/img/rma_fac14_nevins3_resize.png)

A imagem acima mostra um tipo de dado um pouco diferente, pois nas linhas não temos mais **probes**, mas **probe sets** que representam, cada uma, um gene. À esquerda da matriz temos um gráfico **boxplot** que indica a probabilidade de existencia de um padrão em cada linha.
Como podemos ver, as primeiras linhas possuem uma probabilidade alta de padrão (indicada pelos pontos pretos), e a imagem reflete isso, pois o padrão é bastante claro. Da mesma forma, as linhas de baixo possuem baixa probabilidade de padrão e apresentam dados aparentemente aleatórios. 

Como podemos ver, a estatística é uma ciência cujas contribuições se estendem atualmente a um número cada vez maior de áreas, que vão dos estudos genéticos à física das partículas, passando pela identificação de padrões no comportamento dos consumidores, pelos algoritmos de busca utilizados pelo Goggle, ou ainda, pelos algoritmos de recomendação de livros em uso na Amazon.

Nos próximos **posts** vou falar um pouco sobre outros usos da estatística.       