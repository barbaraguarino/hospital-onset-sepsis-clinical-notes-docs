# Instruções do Projeto de Aplicação

A ideia do **Projeto de Aplicação** é integrar **teoria e prática**. Por meio dele, os alunos desenvolvem competências para aplicar modelos de aprendizado de máquina a problemas reais ou simulados da área da saúde, transformando conhecimentos discutidos em sala em um estudo executável, avaliável e reproduzível.

A proposta promove a **aprendizagem ativa**: o aluno deixa de ser apenas receptor de conhecimento e passa a atuar como protagonista do processo, tomando decisões metodológicas, implementando algoritmos, analisando evidências e comunicando os resultados.

Essa estratégia:

1. Integra pesquisa e prática profissional.
2. Fomenta o pensamento crítico e científico.
3. Estimula a interdisciplinaridade entre saúde, ciência de dados e computação.
4. Prepara para a produção acadêmica e científica.
5. Desenvolve práticas de documentação, avaliação e reprodutibilidade.

## Objetivos do Projeto de Aplicação

O projeto deve resultar em uma investigação prática e documentada, na qual o aluno:

- define um problema relevante da área da saúde;
- seleciona e descreve uma base pública de dados;
- implementa pelo menos um algoritmo de aprendizado de máquina;
- estabelece um método de avaliação coerente com o problema;
- analisa os resultados de forma crítica;
- registra as decisões, limitações, riscos e ameaças à validade;
- disponibiliza documentação e código suficientes para permitir a reprodução do estudo.

## Ciclo do Projeto de Aplicação

O desenvolvimento deve seguir um ciclo organizado em cinco etapas:

1. **Tema:** definição do problema, da motivação, do objetivo e do contexto de aplicação.
2. **Dataset:** seleção, descrição, acesso, preparação e pré-processamento dos dados.
3. **Método:** formalização do problema, escolha e implementação do modelo, definição dos hiperparâmetros e do protocolo experimental.
4. **Avaliação:** divisão das amostras, execução dos experimentos, cálculo das métricas e interpretação dos resultados.
5. **Artigo:** organização das evidências em um relatório ou artigo científico, acompanhada do código e dos materiais necessários para reprodução.

## Engenharia de Software Empírica no projeto

A **Engenharia de Software Empírica (ESE)** deve ser utilizada como abordagem metodológica para planejar, executar, analisar e comunicar o Projeto de Aplicação. Ela não deve ser tratada como uma etapa isolada ou como um conteúdo apenas teórico: seus princípios devem orientar todo o ciclo do projeto.

Na prática, isso significa que o projeto deve investigar o comportamento ou o desempenho do modelo por meio de um estudo sistemático, baseado em perguntas explícitas, evidências observáveis, métricas definidas previamente e um protocolo que possa ser repetido por outra pessoa.

A implementação da ESE será organizada nas seguintes fases:

### 1. Definição

Definir com clareza:

- o objeto de estudo, como um algoritmo, modelo ou comparação entre modelos;
- o propósito da investigação;
- o foco de qualidade, como desempenho preditivo, calibração, robustez ou utilidade clínica;
- a perspectiva da análise;
- o contexto, incluindo população, dataset, desfecho e janela temporal.

Sempre que possível, essa definição deve ser expressa por meio do **GQM (Goal–Question–Metric)**:

> Analisar `<objeto>` com o propósito de `<propósito>`, em relação a `<foco de qualidade>`, do ponto de vista de `<perspectiva>`, no contexto de `<contexto>`.
>

A definição também deve incluir as perguntas de pesquisa e, quando aplicável, hipóteses ou expectativas que serão examinadas.

### 2. Planejamento

Antes da execução, especificar o protocolo do estudo:

- variáveis independentes, como tipo de entrada, representação dos dados ou algoritmo;
- variáveis dependentes, como AUPRC, AUROC, sensibilidade, especificidade, F1-score ou calibração;
- critérios de inclusão e exclusão;
- divisão entre treinamento, validação e teste;
- método de validação, como *cross-validation* ou *leave-one-out*, quando apropriado;
- baseline e modelos de comparação;
- hiperparâmetros e procedimentos de ajuste;
- instrumentos, bibliotecas, versões e ambiente de execução;
- ameaças à validade de conclusão, interna, de constructo e externa.

O planejamento deve ser definido antes da análise dos resultados sempre que possível, reduzindo decisões orientadas pelos resultados e tornando a avaliação mais transparente.

### 3. Operação

Executar o protocolo e registrar o processo de forma rastreável:

- versão do dataset e origem dos dados;
- etapas de limpeza, transformação e pré-processamento;
- código executado e configurações utilizadas;
- sementes aleatórias e condições de execução;
- logs, erros, advertências e alterações realizadas;
- amostras efetivamente utilizadas em cada etapa;
- valores produzidos pelo treinamento, validação e teste.

A operação deve gerar não apenas o modelo final, mas também os dados, logs e registros necessários para compreender como os resultados foram obtidos.

### 4. Análise e interpretação

Analisar os dados de acordo com as perguntas e métricas definidas no planejamento:

- apresentar estatísticas descritivas e a distribuição das classes;
- calcular as medidas de desempenho selecionadas;
- comparar o baseline e as alternativas propostas;
- apresentar tabelas, gráficos e médias de desempenho;
- discutir variabilidade, incerteza e possíveis diferenças entre os resultados;
- interpretar os achados considerando o contexto clínico e as ameaças à validade;
- distinguir claramente resultados observados, interpretações e limitações.

A análise não deve se limitar a informar qual modelo obteve a maior métrica. É necessário explicar o que os resultados significam, em que condições são válidos e quais conclusões não podem ser sustentadas pelo estudo.

### 5. Apresentação e empacotamento

Apresentar o estudo de forma científica e preparar um **pacote de replicação** contendo, conforme permitido pelo dataset:

- relatório ou artigo científico;
- README com instruções de execução;
- notebook demonstrativo;
- código-fonte;
- especificação das dependências;
- configuração dos experimentos;
- links para as versões do dataset e do código;
- resultados, tabelas e gráficos gerados;
- limitações, ameaças à validade e decisões metodológicas.

Assim, a ESE conecta o problema de pesquisa, o planejamento experimental, a implementação computacional, a análise dos resultados e a comunicação científica.

## Documentação do Projeto de Aplicação

### Parte 1 — Documentação (`../README.md`)

O README deve permitir que uma pessoa compreenda o estudo e saiba como reproduzi-lo. Ele deve conter:

- **Motivação e objetivo**
    - problema investigado;
    - relevância para a área da saúde;
    - objetivo geral e perguntas de pesquisa;
    - definição GQM, quando aplicável.
- **Descrição do dataset**
    - origem e versão dos dados;
    - população, atributos e desfecho;
    - critérios de inclusão e exclusão;
    - etapas de preparação e pré-processamento;
    - limitações e possíveis vieses;
    - link para a versão disponibilizada do dataset.
- **Modelo de aprendizado de máquina**
    - formulação matemática;
    - algoritmo e justificativa da escolha;
    - baseline e modelos de comparação;
    - método de validação;
    - hiperparâmetros;
    - medidas de desempenho.
- **Avaliação**
    - amostras usadas para treinamento, validação e teste;
    - protocolo experimental;
    - resultados obtidos;
    - tabelas, gráficos e comparação entre modelos;
    - interpretação dos achados;
    - ameaças à validade e limitações.
- **Conclusão**
    - resposta às perguntas de pesquisa;
    - principais contribuições;
    - implicações práticas;
    - possibilidades de trabalhos futuros.

### Parte 2 — Demonstração (notebook)

O notebook deve demonstrar o fluxo completo de execução, incluindo:

- dependências do ambiente de execução;
- versão de Python, R ou MATLAB, conforme a implementação;
- bibliotecas utilizadas;
- funções de apoio;
- carregamento e pré-processamento do dataset;
- definição dos conjuntos de treinamento, validação e teste;
- hiperparâmetros utilizados;
- treinamento e validação dos modelos;
- execução das métricas;
- exibição dos valores e gráficos de interação, como perdas ou acurácia por iteração;
- exibição dos valores e gráficos das médias de desempenho;
- comparação com o baseline;
- conclusão reproduzível a partir dos resultados gerados.

## Checklist de Reprodutibilidade

### Definição e desenho do estudo

- Problema, objetivo e perguntas de pesquisa definidos.
- GQM preenchido, quando aplicável.
- Objeto, propósito, foco de qualidade, perspectiva e contexto descritos.
- Hipóteses ou expectativas registradas, quando aplicável.
- Variáveis independentes e dependentes definidas.
- Protocolo experimental documentado.

### Dataset

- Datasets descritos.
- Dados e atributos descritos.
- Critérios de inclusão e exclusão registrados.
- Etapas de preparação e pré-processamento documentadas.
- Possíveis vieses e limitações discutidos.
- Método de avaliação definido, como *cross-validation* ou *leave-one-out*.
- Link para a versão disponibilizada do dataset incluído.

### Algoritmo

- Formulação matemática, algoritmo e modelo descritos.
- Justificativa da escolha do modelo apresentada.
- Baseline e modelos de comparação definidos.
- Premissas avaliadas.
- Hiperparâmetros registrados.
- Análise de complexidade realizada quando pertinente.

### Codificação e operação

- Dependências do ambiente de execução especificadas.
- Versões das bibliotecas e ferramentas registradas.
- Código-fonte organizado e versionado.
- Sementes aleatórias e configurações de execução registradas.
- Logs, erros e alterações relevantes documentados.
- Link para a versão disponibilizada do código incluído.

### Resultados experimentais

- Amostras de treinamento, validação e teste identificadas.
- Ausência de sobreposição indevida ou vazamento de dados verificada.
- Hiperparâmetros informados.
- Indicadores de desempenho definidos antes da análise, sempre que possível.
- Resultados brutos e agregados preservados.
- Tabelas e gráficos reproduzíveis.
- Limitações e ameaças à validade discutidas.

## Implementação

As linguagens utilizadas poderão ser:

- Python.
- R.
- MATLAB.

Como parte do Projeto de Aplicação, serão propostas implementações de algoritmos de aprendizado de máquina utilizando bases públicas de dados clínicos.

A implementação deverá combinar três dimensões:

1. **Implementação computacional:** desenvolvimento do código, do pré-processamento, do treinamento e da avaliação dos modelos.
2. **Investigação empírica:** definição de perguntas, protocolo, métricas, coleta de evidências, análise e interpretação dos resultados.
3. **Reprodutibilidade:** documentação das decisões, versionamento do código, registro do ambiente e empacotamento dos materiais necessários para repetir o estudo.

Portanto, o projeto não deve ser apresentado apenas como uma aplicação de um algoritmo a um dataset. Ele deve ser conduzido como um estudo empírico de aprendizado de máquina aplicado à saúde, no qual as decisões são justificadas, os resultados são avaliados sistematicamente e as conclusões são sustentadas pelas evidências produzidas.