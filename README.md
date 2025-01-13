# README: Algoritmos de Aproximação para o Problema do Caixeiro Viajante (TSP)

---

## **Informações do Trabalho**

Este projeto é parte do **Trabalho Prático 2 (TP2)** da disciplina **DCC207 - Algoritmos 2**, ministrada pelo **Departamento de Ciência da Computação** do **Instituto de Ciências Exatas da Universidade Federal de Minas Gerais (UFMG)**, sob orientação do **Prof. Renato Vimieiro**.

### **Objetivo do Trabalho**

O objetivo do trabalho prático é abordar os aspectos práticos dos algoritmos para solucionar problemas difíceis, com foco no **Problema do Caixeiro Viajante (TSP)**. O trabalho consiste em implementar três algoritmos para resolver o problema:

1. **Branch and Bound (Exato)**
2. **Twice Around the Tree (Aproximação de fator 2)**
3. **Christofides (Aproximação de fator 1.5)**

Os alunos devem avaliar o desempenho de cada algoritmo em termos de:

- **Tempo de execução**
- **Uso de memória**
- **Qualidade da solução obtida**

Os experimentos devem ser realizados utilizando instâncias da biblioteca **TSPLIB** com distância euclidiana em 2D.

---

## **Descrição do Projeto**

Este projeto implementa e analisa três algoritmos de aproximação para resolver o famoso **Problema do Caixeiro Viajante (TSP)**:

1. **Branch and Bound (Exato)**
2. **Christofides (Aproximação de fator 1.5)**
3. **Twice Around the Tree (Aproximação de fator 2)**

O objetivo é comparar o desempenho, tempo de execução e uso de memória desses algoritmos, utilizando diferentes conjuntos de dados.

---

## **Estrutura do Código**

O código está organizado em várias funções e seções, conforme detalhado abaixo:

### **1. Funções principais**

- `branch_and_bound(grafo)`: Resolve o TSP utilizando o algoritmo exato de Branch and Bound.
- `christofides(grafo)`: Aplica o algoritmo de Christofides para obter uma solução aproximada do TSP com fator de aproximação máximo de 1.5.
- `twice_around_the_tree(grafo)`: Utiliza o algoritmo Twice Around the Tree para obter uma solução aproximada com fator de aproximação máximo de 2.

Cada função retorna:
- O caminho encontrado.
- O comprimento total do caminho.
- O pico de uso de memória em megabytes.

### **2. Função de análise**

- `analise_dados(idx_dataset, df_dados_dataset, dataset_info, alg)`: Executa um algoritmo específico em um conjunto de dados e retorna:
  - Limiar ótimo esperado.
  - Valor máximo esperado com base no fator de aproximação.
  - Comprimento do caminho encontrado.
  - Taxa de aproximação atingida.
  - Tempo de execução.
  - Memória utilizada.

### **3. Função de análise completa**

- `analise_completa(dados_limiares, dataset_info, alg, nome_arquivo)`: Realiza a análise completa para um algoritmo específico e salva os resultados em um arquivo de texto.

### **4. Função para exibir resultados**

- `exibir_resultados_analise(arquivos_analise)`: Lê os arquivos de análise gerados e exibe os resultados em formato tabular.

### **5. Função de visualização**

- A última parte do código gera gráficos que comparam o tempo de execução dos algoritmos em função do número de nós.

---

## **Requisitos**

Os seguintes pacotes Python são necessários para executar o código:

- `networkx`
- `numpy`
- `pandas`
- `matplotlib`
- `tracemalloc`
- `time`
- `os`

---

## **Como Executar**

1. Certifique-se de que todos os pacotes necessários estejam instalados.
2. Execute o notebook na ordem sequencial das células.
3. Após a execução, os resultados das análises serão salvos em arquivos `.txt`.
4. Os gráficos comparativos serão exibidos no final da execução.

---

## **Entradas**

Os dados de entrada consistem em datasets representando coordenadas de cidades, com a seguinte estrutura:

- `cordenadas`: Lista de tuplas representando as coordenadas (x, y) de cada cidade.
- `numero_de_nos`: Quantidade total de nós (cidades) no grafo.
- `limiar`: Valor ótimo esperado.
- `name_dataset`: Nome identificador do dataset.

---

## **Saídas**

Os resultados das análises incluem:

- **Tempo de execução**: Tempo total gasto pelo algoritmo para resolver o problema.
- **Taxa de aproximação**: Relação entre o valor obtido e o valor ótimo esperado.
- **Comprimento do caminho**: Custo total do caminho encontrado.
- **Memória utilizada**: Pico de memória usado durante a execução (em megabytes).

Os resultados são salvos em arquivos `.txt` no formato tabular.

---

## **Exemplo de Saída**

Para o algoritmo **Branch and Bound**, a saída pode ser algo como:

| Dataset      | Algoritmo       | Tempo Execução (s) | Taxa Aproximação | Comprimento Caminho | Espaço (MB) Usado |
|--------------|-----------------|--------------------|------------------|---------------------|-------------------|
| dataset_01   | branch_and_bound| 12.34              | 1.00             | 150.00              | 32.56             |

---

## **Gráficos**

Os gráficos comparativos mostram o tempo de execução dos algoritmos em função do número de nós, permitindo visualizar a eficiência relativa de cada abordagem.

---

## **Erros e Tratamento de Exceções**

- O código inclui verificações para garantir que apenas algoritmos válidos sejam executados.
- Em caso de erro durante a execução, a mensagem de erro correspondente será exibida.

---

## **Contribuição**

Sinta-se à vontade para contribuir com melhorias neste projeto! Sugestões de novos algoritmos ou aprimoramentos nos gráficos e análises são bem-vindos.

---