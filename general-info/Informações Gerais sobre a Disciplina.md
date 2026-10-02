# Informações Gerais sobre a Disciplina

| Disciplina | Introdução ao Aprendizado de Máquina para Saúde |
| --- | --- |
| Foco da disciplina | Compreensão, desenvolvimento, avaliação crítica e comunicação de soluções de aprendizado de máquina aplicadas a problemas de saúde. |

## Objetivos de aprendizagem

Ao final da disciplina, espera-se que os estudantes sejam capazes de:

- Compreender os fundamentos de aprendizado de máquina e suas principais aplicações em saúde.
- Desenvolver soluções de aprendizado de máquina para problemas clínicos e biomédicos.
- Avaliar criticamente desempenho técnico, validade clínica, riscos e limitações metodológicas.
- Comunicar resultados de forma clara, responsável e tecnicamente fundamentada.
- Considerar viabilidade de implementação, aspectos éticos e regulatórios e impacto no cuidado ao paciente.

## Ementa

- [ ]  **Fundamentos de IA e aprendizado de máquina em saúde**: evolução histórica; predição diagnóstico, prognósticos, triagem, recomendação e decisão clínica.
- [ ]  **Dados clínicos, qualidade e interoperabilidade**: EHR, imagens, sinais, notas clínicas, dados ômicos, determinantes sociais, missingness, leakage, governança, HL7 FHIR, OMOP, LOINC e SNOMED CT.
- [ ]  **Desenho de estudos e ciclo de vida de modelos**: população, desfecho, janelas temporais, particionamento, validação, calibração, curvas de decisão e subgrupos.
- [ ]  **Aprendizado supervisionado e não supervisionado**: classificação, regressão, árvores, ensembles, SVM, redes neurais, clustering, redução de dimensionalidade e fenotipagem.
- [ ]  **Aprendizado profundo para dados biomédicos**: redes convolucionais e transformers para imagens, sinais e séries temporais; transferência de aprendizado e avaliação por paciente e instituição.
- [ ]  **NLP biomédico, modelos de linguagem e multimodais**: extração de informação, embeddings, transformers, sumarização, RAG, alucinação, segurança, privacidade e uso responsável.
- [ ]  **Sobrevivência, inferência causal e evidência do mundo real**: riscos competitivos, censura, ensaios-alvo, confundimento, DAGs, propensity score e limites dos dados observacionais.
- [ ]  **Apoio à decisão clínica e implementação**: integração ao fluxo de trabalho, usabilidade, fadiga de alertas, interação humano-IA, segurança do paciente e avaliação prospectiva.
- [ ]  **Explicabilidade, equidade, privacidade e segurança**: SHAP/LIME, saliency, viés algorítmico, LGPD, anonimização, robustez e explicações clinicamente úteis.
- [ ]  **Regulação, relato científico e monitoramento**: SaMD, RDC, ANVISA 657/2022, FDA, TRIPOD+AI, CONSORT-AI, SPRINT-AI, DECIDE-AI, drift, MLOps e governança contínua.

## Metodologia de ensino

A disciplina combina aulas integradas, seminários, análise de estudos de caso reais e desenvolvimento de um miniprojeto prático. O objetivo é aproximar os conceitos teóricos de situações concretas de uso de aprendizado de máquina em saúde.

As atividades práticas poderão utilizar bases como MIMIC-IV, PhysioNet, imagens públicas ou dados sintéticos, sempre que houver restrições éticas, legais ou de acesso aos dados reais.

## Avaliação

A avaliação considera a participação nas aulas e discussões, os trabalhos práticos e relatórios, o projeto final e sua apresentação.

- **Participação e discussão**: perguntas, contrapontos e contribuição para a aprendizagem coletiva.
- **Trabalhos práticos e relatórios**: capacidade de formular, analisar, justificar e comunicar escolhas metodológicas e técnicas.
- **Projeto final + apresentação**: integração entre problema, método, evidência, risco e implementação.

A média da disciplina é calculada por:

$$
Média = Artigos \times 0.4 + Atividades \times 0.1 + Projeto \times 0.5
$$

### Apresentação de artigos científicos

**Entrega**

- Apresentação de no mínimo 10 minutos.
- Slides.
- Resumo de até 4 páginas contendo: (1) Motivação, (2) Objetivo, (3) Metodologia, (4) Resultados e (5) Oportunidades de Pesquisa.

**Critérios de avaliação**

- Clareza na explicação técnica.
- Contextualização adequada.
- Discussão crítica dos resultados e limitações.

### Atividades práticas

As atividades práticas abrangem os seguintes temas:

1. Estatística descritiva.
2. Aprendizado supervisionado.
3. Aprendizado não supervisionado.
4. Comparação entre modelos de aprendizado supervisionado.
5. Classificação de imagens e Grad-CAM.
6. Análise de sobrevivência.
7. Aprendizado por reforço.
8. Séries temporais.

**Entrega**

Arquivos em Jupyter Notebook ou R Markdown comentado.

### Projeto de aplicação

**Entrega**

- Relatório final, com no máximo 12 páginas, no formato de artigo científico.
- Jupyter Notebook comentado.
- Apresentação oral de 15 minutos, seguida de 5 minutos de perguntas.

**Critérios de avaliação**

- Relevância clínica e originalidade.
- Correção metodológica.
- Qualidade da implementação técnica.
- Clareza e objetividade na comunicação oral e escrita.
- Discussão crítica de resultados e limitações.

## Projeto de aplicação

O projeto de aplicação integra teoria e prática e permite que os estudantes desenvolvam competências essenciais para o uso de modelos de aprendizado de máquina em saúde.

A proposta promove a **aprendizagem ativa**: o estudante deixa de ser apenas receptor de conhecimento e passa a atuar como protagonista do processo, aplicando os conceitos discutidos em sala a problemas reais ou simulados da área da saúde.

Essa estratégia:

1. Integra pesquisa e prática profissional.
2. Fomenta o pensamento crítico e científico.
3. Estimula a interdisciplinaridade.
4. Prepara para a produção acadêmica e científica.

### Ciclo do projeto de aplicação

1. Tema.
2. Dataset.
3. Método.
4. Avaliação.
5. Artigo.

### Documentação do projeto de aplicação

**Parte 1 — Documentação (README.md)**

- Motivação e objetivo.
- Descrição do dataset:
    - descrição dos dados;
    - etapas de preparação dos dados ou pré-processamento;
    - link para a versão disponibilizada do dataset.
- Modelo de aprendizado de máquina:
    - formalização matemática;
    - método de validação;
    - medidas de desempenho.
- Avaliação:
    - amostras usadas para treinamento, validação e teste;
    - medidas de desempenho.
- Conclusão.

**Parte 2 — Demonstração (Notebook)**

- Dependências do ambiente de execução.
- Etapas de execução:
    - bibliotecas utilizadas;
    - funções de apoio;
    - carregamento e pré-processamento do dataset;
    - hiperparâmetros utilizados.
- Execução:
    - exibição dos valores e gráficos de interação, como perdas ou acurácia por interação;
    - exibição dos valores e gráficos das médias de desempenho.

### Checklist de reprodutibilidade

**Dataset**

- Descrição dos datasets.
- Descrição dos dados.
- Etapas de preparação dos dados ou pré-processamento.
- Método de avaliação (cross-validation, leave-one-out etc.).
- Link para a versão disponibilizada do dataset.

**Algoritmo**

- Descrição da formulação matemática, do algoritmo e do modelo.
- Avaliação das premissas.
- Análise de complexidade.

**Codificação**

- Especificação das dependências do ambiente de execução.
- Link para a versão disponibilizada do código.

**Resultados experimentais**

- Alocação das amostras usadas para treinamento, validação e teste.
- Hiperparâmetros.
- Definição dos indicadores de desempenho.

### Implementação

As linguagens utilizadas serão:

- Python.
- R.
- Matlab.

Como parte do Projeto de Aplicação, será proposta a implementação de algum algoritmo de ML utilizando uma base pública de dados clínicos.

### Entrega

- Relatório final, com no máximo 12 páginas, no formato de artigo científico.
- Jupyter Notebook comentado.
- Apresentação oral de 15 minutos, seguida de 5 minutos de perguntas.

### Critérios de avaliação

- Relevância clínica e originalidade.
- Correção metodológica.
- Qualidade da implementação técnica.
- Clareza e objetividade na comunicação oral e escrita.
- Discussão crítica de resultados e limitações.

### Datas dos entregáveis

| Entregável | Data | Conteúdo |
| --- | --- | --- |
| Artigo Relacionado 1 | 25 de setembro de 2026 |   • Apresentação de no mínimo 10 minutos
• Slides
• Resumo de até 4 páginas, contendo: (1) Motivação, (2) Objetivo, (3) Metodologia, (4) Resultados, (5) Oportunidades de Pesquisa |
| Artigo Relacionado 2 | 13 de novembro de 2026 |   • Apresentação de no mínimo 10 minutos
• Slides
• Resumo de até 4 páginas, contendo: (1) Motivação, (2) Objetivo, (3) Metodologia, (4) Resultados, (5) Oportunidades de Pesquisa |
| Apresentação e Entrega Final | 04 de dezembro de 2026 |   • Relatório final, com no máximo 12 páginas, no formato de artigo científico.
• Jupyter Notebook comentado
• Apresentação oral de 15 minutos + 5 de perguntas. |

## Bibliografia

#### Fundamentos

- JAMES, G. et al. **An Introduction to Statistical Learning: with Applications in Python**. Cham: Springer, 2023.
- SHORTLIFFE, E. H.; CIMINO, J. J.; CHIANG, M. F. (Ed.). **Biomedical Informatics: Computer Applications in Health Care and Biomedicine**. 5. ed. Cham: Springer, 2021.

#### Dados e Evidência

- BENSON, T.; GRIEVE, G. **Principles of Health Interoperability: FHIR, HL7 and SNOMED CT**. 4. ed. Cham: Springer, 2021.
- HERNÁN, M. A.; ROBINS, J. M. **Causal Inference: What If**. Boca Raton: Chapman & Hall/CRC, 2020.

#### Prática Responsável

- WORLD HEALTH ORGANIZATION (WHO). **Ethics and governance of artificial intelligence for health: WHO guidance**. Genebra: World Health Organization, 2021.
- COLLINS, G. S. et al. TRIPOD+AI statement: updated guidance for reporting clinical prediction models that use regression or machine learning methods. **The BMJ**, Londres, v. 385, p. e078378, abr. 2024.