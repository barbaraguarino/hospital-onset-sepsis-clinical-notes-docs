# Apêndice B — Matriz de Literatura

**Versão**: 0.3 | **Data**: 02/10/2026 | **Fase**: Todas (documento de apoio)

**Como usar este documento:**

- Uso interno: não vai para o artigo. É daqui que saem a síntese comparativa (ver Definição do Estudo), a comparação com a literatura (ver Análise e Interpretação do Estudo) e todo número atribuído a outro estudo.
- Cada referência tem um ID fixo (L01, L02...). O ID liga a ficha à entrada completa no documento Referências; nos demais documentos, a citação continua sendo (AUTOR, ANO).
- Escreva os resumos **com suas palavras**. Trecho literal só entre aspas, com página (ou seção, quando o artigo não tiver páginas). Todo número tirado de um artigo vem com a página, tabela ou figura de onde saiu.
- Só registre uma referência depois de confirmar na fonte primária que ela existe (autores, ano, periódico, DOI), principalmente se foi sugerida por outra IA.
- A versão começa em **0.1** quando o documento ganha o primeiro conteúdo e sobe 0.1 a cada revisão fechada (fim de um chat de revisão, não a cada pequena edição). O documento vira **1.0** na entrega final (04/12/2026). A Data é a da última edição do documento.
- Marque só o que falta preencher com **[A decidir]**. Datas no formato DD/MM/AAAA.

## Fichas

### L01 — AMROLLAHI et al., 2020

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + PubMed Central (https://pmc.ncbi.nlm.nih.gov/articles/PMC8075484/)
- Resumo e análise:
  - Dataset: MIMIC-III (p. 198).
  - População: 40.175 pacientes de UTI de 18 a 89 anos, com permanência na UTI entre 8 h e 1 mês. Desses, 2.805 (cerca de 7%) tiveram sepse. Foram excluídos os pacientes com sepse antes da admissão na UTI ou nas primeiras 4 h de UTI (p. 198; p. 200).
  - Definição do desfecho: Sepsis-3, com horário de início definido por método de trabalho anterior dos autores (p. 198).
  - Dados de entrada: 40 variáveis estruturadas do desafio PhysioNet 2019 (sinais vitais, exames laboratoriais, dados demográficos) e notas médicas e de enfermagem, em janelas horárias (p. 198–199).
  - Modelo: LSTM (p. 199).
  - Métrica principal: AUROC, com especificidade a 0,85 de sensibilidade (Tab. 2, p. 201).
  - Validação: interna, com 80% para treino e 20% para teste (p. 198).
  - Marco temporal: admissão na UTI, com predições horárias que usam só os dados disponíveis até o momento da predição (p. 198).
  - Horizonte: não informado pelo próprio artigo. É de 4 h antes do início segundo YAN et al. (2022), a partir de comunicação com os autores (YAN et al., 2022, Fig. 5, p. 569; Tab. 4, nota h, p. 570).
  - Representação do texto: ClinicalBERT. O vetor de 768 dimensões da nota é a média das representações das frases (40 primeiros tokens, últimas 4 camadas) e é concatenado às 40 variáveis. Ajuste fino não relatado. A alternativa testada foi tf-idf sobre 2.187 termos extraídos por ferramenta comercial (p. 198–199).
  - Ganho do texto: AUROC de 0,81 só com dados estruturados contra 0,84 com estruturados + ClinicalBERT. Estruturados + tf-idf: 0,82. Só notas: 0,74 (Tab. 2, p. 201).

### L02 — APOSTOLOVA; VELEZ, 2017

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + ACL Anthology (https://aclanthology.org/W17-2332/)
- Resumo e análise: **[A decidir]**

### L03 — CHEN et al., 2022

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + editor BMC (https://doi.org/10.1186/s12911-022-02090-3) + PubMed (https://pubmed.ncbi.nlm.nih.gov/36581881/)
- Resumo e análise: **[A decidir]**

### L04 — COLLINS et al., 2024

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + PubMed Central (https://pmc.ncbi.nlm.nih.gov/articles/PMC11019967/)
- Resumo e análise: **[A decidir]**

### L05 — FREY et al., 2026

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + editor IOS Press (https://doi.org/10.3233/SHTI260327) + PubMed (https://pubmed.ncbi.nlm.nih.gov/42175001/)
- Resumo e análise: **[A decidir]**

### L06 — GINESTRA et al., 2024

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + editor Elsevier (https://doi.org/10.1016/j.chest.2024.01.028)
- Resumo e análise: **[A decidir]**

### L07 — HAQ; KHAN; WAHLA, 2026

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + IEEE Xplore (https://ieeexplore.ieee.org/document/11424392/)
- Resumo e análise: **[A decidir]**
### L08 — JOHNSON et al., 2016

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + editor Nature (https://doi.org/10.1038/sdata.2016.35) + PubMed Central (https://pmc.ncbi.nlm.nih.gov/articles/PMC4878278/)
- Resumo e análise: 
  - Dataset: MIMIC-III v1.4 (p. 49487).
  - População: pacientes de UTI. Critérios de inclusão e tamanho da coorte não encontrados no texto ⚠️; as características estão na Tab. 2 (p. 49488).
  - Definição do desfecho: Sepsis-3. A infecção suspeita segue SEYMOUR et al. (2016), e a disfunção é um aumento de pelo menos 2 pontos no SOFA, numa janela de 48 h antes a 24 h depois da suspeita (p. 49487; Fig. 1). Os rótulos são horários, por método de outro trabalho citado pelos autores (p. 49488).
  - Dados de entrada: sinais vitais, exames laboratoriais e dados demográficos em intervalos de 1 h, e notas da tabela NOTEEVENTS anteriores ao início da sepse, sem sumários de alta (p. 49488–49489).
  - Modelo: *Time Series Transformer* com bloco convolucional (p. 49489–49490).
  - Métrica principal: AUROC de 0,95, com acurácia de 0,93 e especificidade de 0,91 (p. 49483; p. 49493).
  - Validação: divisão dos dados não relatada no texto.
  - Marco temporal: UTI, com rótulo horário durante a internação na UTI (p. 49488).
  - Horizonte: 4, 6 e 12 h antes do início (Fig. 6, p. 49493–49494).
  - Representação do texto: cada nota é resumida pelo GPT-4.0 e o resumo é codificado pelo ClinicalBERT. A média dos embeddings por paciente é concatenada às variáveis de cada hora (p. 49489–49490; Alg. 1 e 3).
  - Ganho do texto: não relatado ⚠️. As comparações são só com escores clínicos e outros modelos (Fig. 5 e Tab. 4, p. 49493; Fig. 6, p. 49494).
  - Outros pontos citados na Definição: os autores reconhecem que o resumo é tratado como contexto fixo do paciente na janela de predição, sem evolução temporal (p. 49494).

### L09 — MARKWART et al., 2020

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + PubMed Central (https://pmc.ncbi.nlm.nih.gov/articles/PMC7381455/)
- Resumo e análise: **[A decidir]**

### L10 — MOOR et al., 2021

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + PubMed (https://pubmed.ncbi.nlm.nih.gov/34124082/)
- Resumo e análise: **[A decidir]**

### L11 — PAGE; DONNELLY; WANG, 2015

- Verificação na fonte primária: 27/09/2026 — PDF do projeto (manuscrito do autor, PMC) + PubMed (https://pubmed.ncbi.nlm.nih.gov/26110490/) + editor Wolters Kluwer (https://doi.org/10.1097/CCM.0000000000001164)
- Resumo e análise: **[A decidir]**

### L12 — QIN et al., 2021

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + arXiv (https://arxiv.org/abs/2107.11094)
- Resumo e análise: 
  - Dataset: MIMIC-III (p. 2, 4).
  - População: 49.168 pacientes de UTI, 1.991 (4,05%) com sepse. Foram excluídos 2.145 pacientes sem variáveis relevantes, 8.082 admitidos na UTI com sepse e 2.137 com sepse nas primeiras 6 h de UTI (p. 5).
  - Definição do desfecho: Sepsis-3 na versão mais restritiva usada no desafio PhysioNet 2019 (p. 4).
  - Dados de entrada: 9 variáveis numéricas (sinais vitais, SpO2, glicose e PaCO2), mais variáveis derivadas de tendência e de ausência (p. 4–6). Notas de enfermagem (duas categorias), médicas, de radiologia e respiratórias, concatenadas por hora (p. 5).
  - Modelo: XGBoost (p. 6).
  - Métrica principal: *Utility Score* do PhysioNet 2019. A AUROC é calculada sobre as horas do conjunto de teste (p. 6–7).
  - Validação: interna, com teste fixo de 7.376 pacientes (299 com sepse) e 5 partições aleatórias de treino e validação (p. 6).
  - Marco temporal: UTI. Cada hora de UTI é um exemplo, e são positivas as 6 h anteriores ao início (p. 5).
  - Horizonte: 0 a 6 h antes do início (Tab. 1, p. 8).
  - Representação do texto (p. 3; p. 7):
      - embeddings do ClinicalBERT concatenados às variáveis numéricas, com as notas fundidas (BERTM) ou separadas (BERTS);
      - probabilidade dada por um ClinicalBERT com ajuste fino (FBERTM, FBERTS);
      - tf-idf;
      - entidades extraídas pelo Comprehend Medical.
  - Ganho do texto (Tab. 1, p. 8):
      - FBERTS contra o modelo numérico: *Utility Score* 42,73 → 48,80 e AUROC 86,42 → 89,31;
      - sem ajuste fino: AUROC 86,24 (BERTM) e 86,51 (BERTS), *Utility Score* 42,93 e 43,24.
  - Outros pontos citados na Definição: na importância das variáveis pelo SHAP, o texto aparece em terceiro lugar (Fig. 4, p. 8).

### L13 — RHEE et al., 2019

- Verificação na fonte primária: 27/09/2026 — PDF do projeto (manuscrito do autor, PMC) + PubMed Central (https://pmc.ncbi.nlm.nih.gov/articles/PMC6697188/) + editor Wolters Kluwer (https://doi.org/10.1097/CCM.0000000000003817)
- Resumo e análise: **[A decidir]**
### L14 — SEYMOUR et al., 2016

- Verificação na fonte primária: 27/09/2026 — PDF do projeto (manuscrito do autor, PMC) + PubMed (https://pubmed.ncbi.nlm.nih.gov/26903335/)
- Resumo e análise: **[A decidir]**
### L15 — SINGER et al., 2016

- Verificação na fonte primária: 27/09/2026 — PDF do projeto (manuscrito do autor, PMC) + PubMed Central (https://pmc.ncbi.nlm.nih.gov/articles/PMC4968574/)
- Resumo e análise: **[A decidir]**
### L16 — WANG et al., 2022

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + arXiv (https://arxiv.org/abs/2203.14469)
- Resumo e análise: 
  - Dataset: MIMIC-III e eICU-CRD, analisados separadamente (p. 7–8).
  - População: internações de UTI de pacientes admitidos pelo pronto-socorro, excluídas as com registro de menos de 12 h. No MIMIC-III, 18.625 internações, 6.970 positivas (p. 7; Tab. 1, p. 8).
  - Definição do desfecho: critérios de Angus (CID-9-MC), aplicados aos diagnósticos finais (p. 8).
  - Dados de entrada: 40 variáveis no MIMIC-III (dados demográficos, sinais vitais, exames laboratoriais) nas primeiras T horas, com T de 12, 18, 24, 30 ou 36 (p. 7). Notas das primeiras T horas após a admissão na UTI, sem as frases que contêm "sepsis" ou "septic" (p. 8).
  - Modelo: Transformer multimodal, que combina um módulo de séries temporais com o ClinicalBERT por concatenação (p. 4–7; Fig. 1).
  - Métrica principal: AUROC, com F1, precisão e revocação (p. 9).
  - Validação: interna, com divisão aleatória 80/20 em cada base, 20% do treino para validação e 5 sementes (p. 8–9; Tab. 4, p. 11).
  - Marco temporal: admissão. O texto diz "após a admissão na UTI" para as notas (p. 8) e "após a admissão do paciente" para as séries (p. 7).
  - Horizonte: não definido, porque o rótulo vem de diagnósticos finais sem horário de início (p. 8).
  - Representação do texto: ClinicalBERT pré-treinado, com a saída [CLS] passada a uma rede feedforward (p. 5). Ajuste fino não explicitado.
  - Ganho do texto (MIMIC-III, Tab. 5a, p. 12):
      - só séries: AUROC 0,827 (12 h) a 0,846 (36 h);
      - modelo completo: 0,902 a 0,928;
      - só notas: 0,790 a 0,831.
  - Outros pontos citados na Definição: estudos de caso com a atenção do ClinicalBERT sobre notas de dois pacientes e com os valores fisiológicos de dois pacientes classificados corretamente pelo modelo completo e incorretamente pelo modelo só com notas (Fig. 2–3; p. 11–13).

### L17 — YAN; GUSTAD; NYTRØ, 2022

- Verificação na fonte primária: 27/09/2026 — PDF do projeto + editor Oxford Academic (https://doi.org/10.1093/jamia/ocab236) + PubMed (https://pubmed.ncbi.nlm.nih.gov/34897469/)
- Resumo e análise: **[A decidir]**

### L18 — JOHNSON; POLLARD; MARK, 2016

- Verificação na fonte primária: 27/09/2026 — página oficial do MIMIC-III Clinical Database v1.4 no PhysioNet, citação pedida pelos mantenedores (https://physionet.org/content/mimiciii/1.4/)
- Resumo e análise: **[A decidir]**

### L19 — POLLARD et al., 2026

- Verificação na fonte primária: 27/09/2026 — editor Nature (https://doi.org/10.1038/s44360-026-00096-z); citação padrão pedida pelo PhysioNet na página do MIMIC-III v1.4. Sem PDF no projeto.
- Resumo e análise: **[A decidir]**

### L22 — WOHLIN et al., 2012

- Verificação na fonte primária: 02/10/2026 — página oficial da editora Springer (https://doi.org/10.1007/978-3-642-29044-2): autores, editora, ano, DOI e ISBN impresso 978-3-642-29043-5. Sem PDF no projeto; conteúdo do livro não acessado.
- Resumo e análise: **[A decidir]**

### L24 — BASILI; CALDIERA; ROMBACH, 1994

- Verificação na fonte primária: 02/10/2026 — PDF dos autores na Universidade de Maryland (https://www.cs.umd.edu/~mvz/handouts/gqm.pdf), sem dados de publicação impressos; as páginas citadas são as desse PDF (1–10). Ano e obra (*Encyclopedia of Software Engineering*, Wiley, ed. J. J. Marciniak) vêm de fontes secundárias, incluindo a lista de referências de WOHLIN et al. (2012) na Springer, que cita a obra com outro título ("Goal Question Metrics paradigm", p. 528–532). Página da Wiley não conferida. Sem PDF no projeto.
- Resumo e análise: **[A decidir]**