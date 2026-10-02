# Definição do Estudo

**Versão**: 0.4 | **Data**: 02/10/2026 | **Fase**: Definição

**Como usar este documento:**

* Marque só o que falta decidir com **\[A decidir]**. O que não tem marcação já está decidido.
* A versão **1.0** é congelada depois da execução-piloto e antes da execução completa: a partir dela, o documento não é mais editado e, por isso, a Data do cabeçalho fica sendo a data do congelamento. Mudanças posteriores são registradas como desvio do plano no documento Operação do Estudo.
* A versão começa em **0.1** quando o documento ganha o primeiro conteúdo e sobe 0.1 a cada revisão fechada (fim de um chat de revisão, não a cada pequena edição). A Data é a da última edição do documento.
* Todo número, percentual ou estatística vem com a fonte ao lado, "no formato (AUTOR, ANO), com et al. quando há vários autores. A referência completa fica só no documento Referências.
* Todo termo clínico ou técnico novo é definido no Apêndice C – Glossário e Fundamentação.
* Para remeter a outro documento, cite o documento inteiro (ex.: "ver Planejamento do Estudo"), nunca uma seção pelo nome.

## 1\. Motivação e Problema

A sepse é definida, pelo consenso Sepsis-3, como uma disfunção orgânica com risco de vida causada por uma resposta desregulada do hospedeiro a uma infecção (SINGER et al., 2016). Operacionalmente, a disfunção orgânica é identificada quando um paciente com infecção suspeita ou confirmada apresenta um aumento agudo de pelo menos 2 pontos no escore SOFA (*Sequential Organ Failure Assessment*) em relação a um valor basal (SINGER et al., 2016). Este estudo trata da sepse de início hospitalar (*hospital-onset sepsis*, HOS), em que a infecção e a disfunção orgânica se desenvolvem mais de 48 horas após a admissão hospitalar, distinta da sepse comunitária (*community-onset sepsis*, COS), já presente na admissão (GINESTRA et al., 2024). As definições dos termos clínicos e técnicos usados nesta seção, incluindo a composição do SOFA, estão no Apêndice C – Glossário e Fundamentação.

O reconhecimento precoce é prioritário: mesmo uma disfunção orgânica modesta no momento em que se suspeita da infecção está associada a mortalidade hospitalar superior a 10% (SINGER et al., 2016). Na sepse comunitária, a melhoria no reconhecimento e na intervenção oportuna reduziu significativamente a mortalidade nas últimas duas décadas, mas os desfechos da HOS permanecem comparativamente piores (GINESTRA et al., 2024). Em comparação com pacientes com sepse comunitária, os pacientes com HOS têm duas vezes mais chance de necessitar de ventilação mecânica e de internação em Unidade de Terapia Intensiva (UTI), tempo de internação mais que duas vezes maior, tanto na UTI quanto no hospital, e duas vezes mais chance de óbito (GINESTRA et al., 2024), além de maior custo hospitalar (PAGE et al., 2015). Na UTI, o peso é particularmente alto: segundo uma revisão sistemática com meta-análise, 48,7% dos casos de sepse com disfunção orgânica tratados em UTI têm origem hospitalar (intervalo de confiança de 95%, IC 95%: 38,3–59,3%), com mortalidade de aproximadamente 52,3% nesse grupo (IC 95%: 43,4–61,1%) (MARKWART et al., 2020). Parte dos fatores de risco da HOS, no entanto, pode ser modificável: pacientes com HOS têm menor probabilidade de receber investigação e tratamento da infecção em tempo oportuno do que os com sepse comunitária (GINESTRA et al., 2024).

O reconhecimento é justamente onde a prática atual encontra dificuldade. O paciente que desenvolve uma infecção durante a internação frequentemente já apresenta alterações fisiológicas causadas pela doença que motivou a internação, o que dificulta distinguir sinais novos dos antigos, e pode apresentar com menos frequência os sinais típicos de infecção, o que contribui para incerteza diagnóstica e atrasos no reconhecimento e no tratamento (GINESTRA et al., 2024). Os mesmos autores apontam que esses pacientes podem se beneficiar de ferramentas de apoio ao diagnóstico e à decisão, que o volume de dados registrados no prontuário eletrônico do paciente (PEP) antes, durante e depois de um episódio de HOS torna o tema uma oportunidade de pesquisa, e listam, entre as prioridades de pesquisa, a incorporação das características específicas da HOS no desenvolvimento de sistemas de alerta precoce e a padronização da identificação de casos (GINESTRA et al., 2024). O PEP reúne tanto dados estruturados, como sinais vitais e exames laboratoriais, quanto notas clínicas em texto livre (YAN et al., 2022). A maioria dos modelos de predição de sepse baseados no PEP usa apenas dados estruturados (AMROLLAHI et al., 2020), em parte pela complexidade de processar texto livre (YAN et al., 2022), mas há evidência de que as notas clínicas carregam informação complementar à dos dados estruturados para a predição precoce de sepse em pacientes de UTI (AMROLLAHI et al., 2020). O uso pretendido de um modelo desse tipo é o de ferramenta de apoio à decisão clínica, na forma de alerta de risco, sem substituir o julgamento clínico. Em um cenário futuro de aplicação, não avaliado neste estudo, os beneficiários potenciais seriam os pacientes de UTI, com possível redução de morbimortalidade; a equipe assistencial, com alerta precoce para apoio à decisão; e o sistema de saúde, com possível redução de custo e de tempo de internação.

Estudos anteriores, entre eles uma revisão sistemática, já examinaram o ganho do texto clínico sobre os dados estruturados na predição de sepse em geral (AMROLLAHI et al., 2020; YAN et al., 2022), mas, nos trabalhos revisados, esse ganho não foi avaliado para a sepse de início hospitalar como entidade distinta, com marco temporal na admissão hospitalar — e, por consequência, também não se sabe em quais casos específicos de HOS a informação textual altera a predição do modelo. O detalhamento dessa lacuna vem adiante, na discussão da literatura.

## 2. Trabalhos Relacionados

**Estratégia de busca.** Não houve busca sistemática. Os trabalhos foram reunidos por pesquisa exploratória no Google Acadêmico, com combinações informais de palavras-chave que não foram registradas, sem data de busca e sem critérios de inclusão e exclusão definidos de antemão. Os artigos encontrados foram avaliados um a um, à medida que surgiam, e não houve snowballing. Cada trabalho mantido no conjunto foi conferido na fonte primária em 27/09/2026 (ver Apêndice B – Matriz de Literatura).

A cobertura mais ampla do conjunto vem das duas revisões. Para a predição de sepse com texto clínico, é a de YAN et al. (2022), cuja busca terminou em 3 de setembro de 2021 (YAN et al., 2022). Para a predição de sepse em UTI em geral, é a de MOOR et al. (2021), cuja busca foi até 20 de julho de 2020 (MOOR et al., 2021). Os estudos posteriores entram apenas porque foram lidos individualmente (CHEN et al., 2022; WANG et al., 2022; FREY et al., 2026; HAQ et al., 2026). Por isso, a afirmação de novidade feita adiante vale só para a literatura revisada.

**Síntese comparativa.** As duas revisões descrevem uma área dominada por dados estruturados. MOOR et al. (2021) revisaram 22 estudos de aprendizado de máquina para a predição do início da sepse em UTI e encontraram o seguinte:

- os tipos de dado relatados são sinais vitais, exames laboratoriais, dados demográficos e comorbidades, sem menção a texto clínico;
- 12 dos 22 estudos usaram o MIMIC-II ou o MIMIC-III;
- só 3 fizeram validação externa;
- a heterogeneidade na definição de sepse, nas janelas de predição e no alinhamento entre casos e controles impediu uma meta-análise.

Os mesmos autores recomendam relatar a AUPRC em desfechos de baixa prevalência (MOOR et al., 2021). YAN et al. (2022) revisaram especificamente o uso de texto clínico na identificação, na detecção precoce e na predição da sepse. Concluíram que poucos estudos usam texto e incluíram 9, também heterogêneos demais para uma meta-análise (YAN et al., 2022).

Dos estudos primários do conjunto, quatro combinam notas clínicas e dados estruturados na predição de sepse: AMROLLAHI et al. (2020), QIN et al. (2021), WANG et al. (2022) e HAQ et al. (2026). CHEN et al. (2022) usa só dados estruturados e entra na comparação como contraste. A tabela a seguir resume os cinco estudos e este.

| Estudo | Dataset | População | Definição do desfecho | Dados de entrada | Modelo | Métrica principal | Validação | Marco temporal (tempo zero) | Horizonte de predição | Representação do texto | Ganho do texto relatado |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| AMROLLAHI et al., 2020 | MIMIC-III | 40.175 pacientes de UTI de 18 a 89 anos, 2.805 com sepse; excluídos os com sepse antes da UTI ou nas primeiras 4 h de UTI | Sepsis-3 | 40 variáveis estruturadas (sinais vitais, exames laboratoriais, dados demográficos) + notas médicas e de enfermagem | LSTM | AUROC | Interna (80% treino, 20% teste) | Admissão na UTI | 4 h antes do início (YAN et al., 2022) | ClinicalBERT, média das representações das frases; ajuste fino não relatado | AUROC 0,81 → 0,84 |
| QIN et al., 2021 | MIMIC-III | 49.168 pacientes de UTI, 1.991 com sepse; excluídos os admitidos na UTI com sepse e os com início nas primeiras 6 h de UTI | Sepsis-3, versão restritiva do desafio PhysioNet 2019 | 9 variáveis numéricas e derivadas + notas de enfermagem, médicas, de radiologia e respiratórias | XGBoost | *Utility Score* do PhysioNet 2019 | Interna (teste de 7.376 pacientes; 5 partições de treino e validação) | Admissão na UTI (predição horária) | 0 a 6 h antes do início | Embeddings do ClinicalBERT concatenados às variáveis numéricas, com e sem ajuste fino; tf-idf; entidades do Comprehend Medical | Com ajuste fino: AUROC 86,42 → 89,31, *Utility Score* 42,73 → 48,80; sem ajuste fino: AUROC 86,24 e 86,51 |
| WANG et al., 2022 | MIMIC-III e eICU-CRD, analisados separadamente | MIMIC-III: 18.625 internações de UTI de pacientes admitidos pelo pronto-socorro, 6.970 positivas | Critérios de Angus (códigos CID-9-MC dos diagnósticos finais) | Séries temporais de 40 variáveis (sinais vitais, exames laboratoriais, dados demográficos) + notas das primeiras 12 a 36 h | Transformer multimodal | AUROC | Interna, em cada base | Admissão na UTI (janelas de 12 a 36 h) | Não definido: rótulo por diagnósticos finais, sem horário de início | ClinicalBERT pré-treinado (representação [CLS]) | MIMIC-III: AUROC 0,827 → 0,902 (12 h) e 0,846 → 0,928 (36 h) |
| HAQ et al., 2026 | MIMIC-III v1.4 | 5.592 pacientes adultos, descritos na tabela de características como casos de sepse; controles não descritos | Sepsis-3, com rótulo horário | 47 variáveis estruturadas por hora (15 sinais vitais e parâmetros ventilatórios, 29 exames laboratoriais, 3 demográficas) + notas… | *Time Series Transformer* | AUROC | Não relatado | UTI (rótulo horário durante a internação na UTI) | 4, 6 e 12 h antes do início | Resumos das notas gerados pelo GPT-4.0, codificados pelo ClinicalBERT e promediados por paciente | Não relatado |
| CHEN et al., 2022 | MIMIC-III v1.4 + base privada de outro hospital + uso real | MIMIC-III: 6.891 pacientes de UTI, 1.057 com sepse; controles sem sepse em toda a internação na UTI | Sepsis-3 | 78 variáveis estruturadas | LightGBM e MLP, combinados após aprendizado por transferência | AUROC | Interna, externa e em uso real | Admissão na UTI | 1 a 5 h antes do início | Não usa texto | Não se aplica |
| Este estudo | MIMIC-III v1.4 | Adultos cuja primeira passagem pela UTI acontece nas primeiras 48 h da internação hospitalar, sem sepse iniciada na janela de observação | HOS pelos critérios do Sepsis-3 | Idade, sexo e pior valor das variáveis dos seis componentes do SOFA na janela + notas até o fim da janela | XGBoost | AUPRC | Interna | Admissão hospitalar (predição única ao fim das primeiras 48 h) | Variável por paciente | Embeddings do ClinicalBERT pré-treinado, sem ajuste fino, concatenados às variáveis estruturadas | A medir (QP1) |

O que os quatro estudos com notas têm em comum:

- todos usam a base MIMIC-III e a população de UTI;
- todos representam as notas com o ClinicalBERT, aplicado diretamente às notas ou, em HAQ et al. (2026), a resumos gerados por um modelo de linguagem de grande porte;
- os três que compararam o modelo combinado com um modelo só com dados estruturados relataram ganho de AUROC com as notas em ao menos uma configuração (AMROLLAHI et al., 2020; QIN et al., 2021; WANG et al., 2022).

Divergem em quase todo o resto: modelo, definição do desfecho, métrica principal, horizonte e forma de representar e combinar o texto. Duas divergências importam para este estudo.

A primeira é que o ganho depende da representação. Em QIN et al. (2021), os embeddings do ClinicalBERT sem ajuste fino concatenados às variáveis numéricas, que é a configuração adotada neste estudo, tiveram AUROC e *Utility Score* próximos aos do modelo só numérico. O ganho apareceu com a versão com ajuste fino. AMROLLAHI et al. (2020) obtiveram ganho sem relatar ajuste fino, mas com outro modelo e outra forma de obter a representação da nota.

A segunda é o marco temporal, que em todos os estudos é a UTI:

- AMROLLAHI et al. (2020) e QIN et al. (2021) excluem a sepse iniciada antes da UTI ou nas primeiras 4 e 6 h dela, respectivamente;
- HAQ et al. (2026) rotulam a sepse hora a hora durante a internação na UTI;
- WANG et al. (2022) usam janelas fixas a partir da admissão na UTI e um rótulo derivado dos diagnósticos finais, sem horário de início e sem exclusão relatada da sepse já presente na admissão.

Nenhum distingue a sepse pelo momento de início em relação à admissão hospitalar. WANG et al. (2022) é o estudo mais próximo deste na estrutura temporal, com janela de observação fixa e predição única, mas não no desfecho. CHEN et al. (2022), só com dados estruturados, também ancora a predição na UTI e é o único do conjunto com validação externa e avaliação em uso real.

Os estudos de extração de informação das notas não constroem modelos de predição de sepse. APOSTOLOVA e VELEZ (2017) classificaram notas de enfermagem do MIMIC-III quanto à presença de sinais de infecção. FREY et al. (2026) compararam métodos baseados em regras, em modelos de linguagem de grande porte e híbridos para extrair das notas do MIMIC-III 19 medidas dos critérios SOFA, qSOFA e SIRS. Os dois apontam a combinação com dados estruturados como trabalho posterior (APOSTOLOVA; VELEZ, 2017; FREY et al., 2026). Indicam que as notas registram sinais de infecção e medidas de disfunção orgânica, os dois componentes do critério Sepsis-3, mas não medem o valor dessa informação para a predição.

A lacuna tem duas partes.

- **Desfecho e marco temporal.** Nenhum dos estudos primários revisados, e nenhum dos listados nas tabelas das duas revisões, define o desfecho como HOS (YAN et al., 2022; MOOR et al., 2021). Nos estudos primários, o marco temporal é sempre a admissão na UTI. A literatura sobre HOS, por sua vez, registra que a maior parte da pesquisa em sepse, inclusive os maiores ensaios clínicos, tratou da sepse comunitária. Recomenda incorporar as características da HOS no desenvolvimento de sistemas de alerta precoce e descrever e justificar o tempo zero adotado (GINESTRA et al., 2024).
- **Análise caso a caso.** Análises de casos já existem. WANG et al. (2022) visualizam a atenção do modelo sobre notas de dois pacientes e examinam dois pacientes classificados corretamente pelo modelo combinado e incorretamente pelo modelo só com notas. CHEN et al. (2022) ilustram as predições de quatro pacientes. QIN et al. (2021) e CHEN et al. (2022) relatam a importância global das variáveis pelo SHAP. Nenhum examina os pacientes em que acrescentar as notas muda a predição em relação ao modelo só com dados estruturados.

**Contribuição pretendida.** São dois tipos.

**Tipo: recorte de população ou desfecho ainda não estudado.** Na tabela, os estudos que avaliaram o ganho das notas ancoram a predição na UTI e não distinguem o início da sepse em relação à admissão hospitalar. Este estudo avalia esse ganho para a HOS, com marco temporal na admissão hospitalar e predição ao fim das primeiras 48 h. Esse recorte não foi encontrado na literatura revisada.

**Tipo: nova forma de avaliação ou análise.** Inspecionar casos não é, em si, novidade, porque estudos de caso e importância de variáveis já aparecem em WANG et al. (2022), CHEN et al. (2022) e QIN et al. (2021). O que não foi encontrado na literatura revisada é a inspeção dos pacientes cuja predição muda quando as notas são acrescentadas ao modelo só com dados estruturados, que é o objeto da QP2.

Os outros tipos não se aplicam:

- **Nova combinação de fontes:** a combinação de notas e dados estruturados já foi estudada (AMROLLAHI et al., 2020; QIN et al., 2021; WANG et al., 2022; HAQ et al., 2026).
- **Replicação:** apesar de usar a mesma base de AMROLLAHI et al. (2020) e QIN et al. (2021), o estudo muda coorte, desfecho e marco temporal, e os resultados não são comparáveis em números.
- **Método:** a representação e a fusão do texto seguem QIN et al. (2021) e não são contribuição.

## 3. Definição do Objetivo

O objetivo geral do estudo é avaliar o valor incremental da informação extraída de notas clínicas, em relação aos dados clínicos estruturados, para a predição de HOS em pacientes adultos de UTI, comparando um modelo baseado em dados estruturados com um modelo combinado (dados estruturados + notas clínicas), e caracterizar os casos específicos em que essa informação textual altera a predição do modelo.

Formulado segundo o template de definição de objetivo de WOHLIN et al. (2012), derivado do GQM (*Goal-Question-Metric*), o objetivo fica:

Analisar **modelos preditivos de HOS construídos a partir de dados clínicos estruturados**
com o propósito de **avaliar o valor incremental agregado por notas clínicas**
com respeito ao **desempenho preditivo, medido pela área sob a curva de precisão–revocação (AUPRC), e à mudança de predição caso a caso**
do ponto de vista do **pesquisador em aprendizado de máquina aplicado à saúde**
no contexto de **pacientes adultos admitidos na UTI nas primeiras 48 horas da internação hospitalar e sem sepse nesse período (janela de observação), tendo como desfecho o desenvolvimento de HOS após essa janela, na base MIMIC-III (*Medical Information Mart for Intensive Care III*)**.

Cada parte do objetivo corresponde a uma das questões de pesquisa formuladas a seguir. A QP1 responde ao propósito de avaliar o valor incremental com respeito ao desempenho preditivo (AUPRC), que é a primeira parte do objetivo geral: a comparação entre o modelo combinado e o modelo só com dados estruturados. A QP2 responde ao segundo aspecto do foco, a mudança de predição caso a caso, que é a segunda parte do objetivo geral: a caracterização dos casos em que a informação textual altera a predição.

## 4. Questões de Pesquisa

As duas questões derivam do objetivo do estudo e servem de ponte para as hipóteses, formalizadas no Planejamento do Estudo.

**QP1:** Em pacientes adultos de UTI sem sepse presente no período inicial de observação, qual é o valor incremental da informação extraída das notas clínicas, em relação aos dados clínicos estruturados, para a predição de sepse de início hospitalar?

**Classificação: confirmatória.** A QP1 testa a expectativa descrita a seguir, definida antes de ver os dados, e por isso recebe hipótese formal (nula e alternativa) no Planejamento do Estudo. Ela é respondida pela AUPRC no conjunto de teste, comparando o modelo combinado com o modelo que usa só os dados estruturados. Os dois modelos usam o mesmo algoritmo e são avaliados nos mesmos pacientes.

**Expectativa.** Espera-se que o modelo combinado supere, em AUPRC, o modelo apenas com dados estruturados. A expectativa se apoia em dois resultados da literatura. AMROLLAHI et al. (2020) mostraram que incorporar representações de notas clínicas melhorou a predição precoce de sepse em pacientes de UTI do MIMIC-III. A revisão sistemática de YAN et al. (2022), com 9 estudos incluídos, concluiu que a maioria deles indica que combinar texto clínico e dados estruturados melhora a identificação e a detecção precoce da sepse em relação aos dados estruturados isolados. A heterogeneidade entre os estudos, porém, impediu uma meta-análise e a comparação direta dos resultados entre eles (YAN et al., 2022). Há, porém, um resultado contrário para a configuração adotada neste estudo: em QIN et al. (2021), os embeddings do ClinicalBERT sem ajuste fino, concatenados às variáveis numéricas, tiveram AUROC próxima à do modelo sem texto, e o ganho só apareceu com ajuste fino. Um resultado sem diferença entre os dois modelos seria, portanto, compatível com parte da literatura revisada.

O resultado de AMROLLAHI et al. (2020) corresponde a predições feitas 4 horas antes do início da sepse, horizonte informado por YAN et al. (2022) a partir de comunicação com os autores. A mesma revisão sugere que o texto clínico contribui mais nas predições feitas com 48 a 12 horas de antecedência, e os dados estruturados, nas feitas a menos de 12 horas do início (YAN et al., 2022). Essa observação, contudo, apoia-se em poucos estudos que compararam modelos com e sem texto nesse intervalo, heterogêneos entre si em população, desfecho e definição de sepse (YAN et al., 2022). Ela é lida aqui como indício a verificar, e não como resultado estabelecido, de que o texto pode ser mais útil quando o início da sepse está distante do momento da predição.

**QP2:** Em quais casos específicos essa informação textual modifica a predição do modelo?

**Classificação: exploratória.** A QP2 investiga um padrão sem expectativa prévia e, por isso, não recebe hipótese formal. O tipo de análise é a inspeção de casos: a leitura qualitativa dos pacientes do conjunto de teste em que a predição do modelo combinado difere da do modelo só com dados estruturados. Os resultados são apresentados como exploratórios, sem conclusão de causa nem de generalização.

## 5. Caracterização do Contexto

WOHLIN et al. (2012) classificam um experimento pelo número de sujeitos, que aplicam o tratamento, e pelo número de objetos, sobre os quais o tratamento é aplicado. A classificação foi pensada para experimentos com pessoas. Como este estudo é computacional e não tem participantes humanos, os papéis foram adaptados assim (adaptação deste estudo, não definida por WOHLIN et al., 2012):

- **Tratamentos:** os dois níveis da modalidade de entrada, isto é, o modelo só com dados estruturados e o modelo combinado (dados estruturados + notas clínicas). A regressão logística e o qSOFA são referências descritivas, fora do teste de hipótese, e não contam como tratamentos (ver Planejamento do Estudo).
- **Sujeito:** o pipeline único de treino e avaliação, que aplica os dois tratamentos com o mesmo código, o mesmo algoritmo, a mesma busca de hiperparâmetros e a mesma semente aleatória.
- **Objeto:** a coorte de pacientes extraída de uma única base, o MIMIC-III, versão 1.4.

Com um sujeito e um objeto, o estudo é classificado como de **objeto único** (*single object study*). Os dois tratamentos passam pelo mesmo pipeline e são avaliados nos mesmos pacientes do conjunto de teste, de modo que a única diferença entre eles é a presença das notas clínicas, como pede a QP1. A base também é uma só, de um único hospital. As outras classificações não se aplicam. Tratar cada paciente ou cada partição dos dados como um objeto confundiria unidades de análise, ou partes de uma mesma base, com objetos independentes. Tratar cada modelo como um sujeito confundiria quem aplica o tratamento com o próprio tratamento. Os pacientes, portanto, não ocupam o papel de sujeito: são as unidades de análise da coorte (ver Planejamento do Estudo). A participação humana no estudo, que inclui a inspeção de casos da QP2, feita pela autora, é descrita no Planejamento do Estudo.

## 6. Delimitação do Estudo

**Tarefa e desfecho.** O estudo prediz, por classificação binária, se o paciente desenvolve HOS, definida pelos critérios do Sepsis-3 (SINGER et al., 2016) operacionalizados com base em SEYMOUR et al. (2016). Cada paciente recebe uma única predição, feita ao fim da janela de observação. A QP2 complementa essa predição com a inspeção dos casos em que as notas clínicas alteram a predição do modelo. Fica fora do escopo:

- **Outras definições de sepse** (critérios de SIRS das versões anteriores do consenso, diagnósticos codificados, *Adult Sepsis Event* do CDC): o Sepsis-3 é o consenso vigente e foi proposto para substituir as definições anteriores (SINGER et al., 2016). É também a definição usada por AMROLLAHI et al. (2020), resultado em que se apoia a expectativa da QP1.
- **Outros desfechos** (infecção hospitalar sem disfunção orgânica, choque séptico, mortalidade): o objetivo trata só da HOS, e cada desfecho adicional exigiria outro rótulo e outra avaliação. A mortalidade hospitalar aparece apenas na descrição da coorte (ver Planejamento do Estudo).
- **Estratificação por foco da infecção** (respiratório, urinário, abdominal etc.): a sepse é tratada de forma agregada, porque os critérios do Sepsis-3 não incluem o foco (SINGER et al., 2016).
- **Análise de sobrevivência** (tempo até a HOS): a classificação binária é mais compatível com o escopo e o prazo do projeto e segue os trabalhos de predição de sepse revisados, que tratam o desfecho como classificação (AMROLLAHI et al., 2020; QIN et al., 2021; WANG et al., 2022; HAQ et al., 2026).

**População.** Pacientes adultos (18 anos ou mais) cuja primeira passagem pela UTI acontece nas primeiras 48 horas da internação hospitalar, que completam a janela de observação e não tiveram sepse iniciada nela. Entra uma internação por paciente. Os critérios detalhados estão no Planejamento do Estudo. Fica fora do escopo:

- **Pacientes com menos de 18 anos:** o Sepsis-3 foi elaborado para adultos, e seus autores reconhecem que populações pediátricas precisam de definições próprias, que levem em conta a variação dos valores fisiológicos normais com a idade (SINGER et al., 2016).
- **Pacientes sem passagem pela UTI:** o MIMIC-III reúne pacientes internados em unidades de cuidados críticos (JOHNSON et al., 2016).
- **Pacientes cuja primeira passagem pela UTI acontece depois das primeiras 48 horas:** a admissão na UTI precisa ser conhecida no momento da predição. Admitir passagens posteriores faria a entrada no estudo depender de eventos que podem ser consequência do próprio desfecho.
- **Internações hospitalares posteriores do mesmo paciente:** a exclusão evita pseudorreplicação.
- **Pacientes que morrem ou recebem alta antes do fim da janela de observação:** os dados de entrada precisam vir de uma janela completa.
- **Pacientes com sepse iniciada na janela de observação, inclusive a já presente na admissão:** eles não se enquadram na definição de HOS, que exige início mais de 48 horas após a admissão (GINESTRA et al., 2024). Sem essa exclusão, seriam rotulados como negativos.

**Dados.** Entram dados estruturados e notas clínicas em texto livre, em inglês, todos do MIMIC-III, versão 1.4. Os dados estruturados são idade, sexo e valores brutos das variáveis dos seis componentes do SOFA, agregados pelo pior valor na janela de observação. As notas são as disponíveis até o fim da janela. Fica fora do escopo:

- **Outras variáveis estruturadas** (como medicamentos e comorbidades): o conjunto estruturado se restringe às variáveis do critério de disfunção orgânica, cuja extração já é necessária para construir o rótulo. Ampliá-lo exigiria mapear outras fontes da base dentro do prazo do projeto.
- **Diagnósticos codificados:** costumam ser registrados dias ou meses depois do evento, em geral após a alta (YAN et al., 2022), e trariam para a predição informação que ainda não existia ao fim da janela.
- **Imagens e sinais fisiológicos contínuos:** o objetivo compara só dados estruturados e notas clínicas. Além disso, no MIMIC-III os sinais contínuos foram obtidos apenas para parte dos pacientes (JOHNSON et al., 2016).
- **Notas em português:** a base só tem notas em inglês. Estender o estudo exigiria outra base e outro modelo de linguagem.
- **Padronização por terminologias como SNOMED CT e LOINC:** o estudo usa uma única base, cujas variáveis são identificadas pelos dicionários da própria base, sem integração com dados de outras fontes.

**Métodos.** Os dois tratamentos usam o mesmo algoritmo, o XGBoost. No modelo combinado, as notas são representadas por *embeddings* do ClinicalBERT pré-treinado, executado localmente e sem ajuste fino, concatenados às variáveis estruturadas, como em QIN et al. (2021). A regressão logística e o qSOFA entram apenas como referências descritivas, e a explicabilidade usa SHAP. Fica fora do escopo:

- **Comparação entre algoritmos:** não responde às QPs. Além disso, se o algoritmo mudasse junto com a modalidade de entrada, a diferença de desempenho não isolaria o efeito das notas.
- **Ajuste fino (*fine-tuning*) do modelo de linguagem:** o termo de uso da base impede enviar os dados a serviços externos. O ajuste fino teria, portanto, de ser feito localmente, com custo computacional e tempo incompatíveis com o prazo do projeto.
- **Outras representações do texto e outras formas de fusão:** cada alternativa seria um tratamento a mais, com nova extração e nova busca de hiperparâmetros, fora do prazo. A conclusão sobre o valor das notas vale para a representação adotada.
- **Rebalanceamento de classes:** alteraria as probabilidades estimadas, que o estudo também avalia. O desbalanceamento é tratado pela métrica principal e pela estratificação das partições (ver Planejamento do Estudo).
- **Modelos de linguagem acessados por serviços externos:** o termo de uso da base proíbe compartilhar os dados com terceiros, inclusive por APIs (ver Planejamento do Estudo).

**Avaliação.** A QP1 é respondida pela AUPRC no conjunto de teste, com intervalo de confiança de 95% por *bootstrap* pareado, acompanhada de métricas secundárias de discriminação e de calibração. A QP2 é respondida pela inspeção de casos. A validação é interna, toda dentro do MIMIC-III (ver Planejamento do Estudo). Fica fora do escopo:

- **Validação externa** (em outra base ou outro hospital): não há, no prazo do projeto, segunda base com notas clínicas comparáveis às do MIMIC-III (ver Planejamento do Estudo).
- **Validação temporal:** as datas da base foram deslocadas na desidentificação (JOHNSON et al., 2016), o que impede separar treino e teste por período.
- **Desempenho por subgrupo e técnicas de equidade:** o número esperado de casos de HOS tornaria instáveis as estimativas por subgrupo.
- ***Utility Score* do desafio PhysioNet 2019:** a métrica pressupõe predições horárias avaliadas em relação ao início da sepse, e este estudo faz uma única predição por paciente.
- **Segunda revisão independente na inspeção de casos:** não há segundo avaliador disponível no escopo do projeto.
- **Impacto clínico e custo-efetividade:** o modelo não é usado no cuidado, e não há efeito sobre pacientes ou custos a medir.

**Uso.** Estudo retrospectivo e observacional, com dados históricos já coletados. O uso como apoio à decisão clínica, na forma de alerta de risco, é o objetivo de aplicação de longo prazo, não o estado atual do modelo. Fica fora do escopo:

- **Validação prospectiva e integração com sistemas clínicos reais:** exigiriam um estudo prospectivo, com aprovação ética própria e acesso a um ambiente clínico, fora do alcance de um estudo retrospectivo.

**Tempo.** Os dados vêm de internações entre 2001 e 2012 (JOHNSON et al., 2016), com datas deslocadas na desidentificação. A janela de observação vai da admissão hospitalar até 48 horas depois, e a predição é feita ao fim dela. A HOS pode começar em qualquer momento entre o fim da janela e a alta ou o óbito, de modo que o horizonte de predição não é fixo e varia de paciente para paciente. Se e como o horizonte será relatado: **\[A decidir]**. Fica fora do escopo:

- **Outras janelas de observação:** a janela coincide com o corte de 48 horas da definição de HOS (GINESTRA et al., 2024). Outra duração mudaria a fronteira entre a sepse excluída da coorte e a sepse rotulada como HOS.
- **Horizonte fixo e predições repetidas ao longo da internação:** o marco temporal na admissão hospitalar e a predição única ao fim da janela seguem a definição de HOS. Em troca, o estudo é menos comparável, em números, com trabalhos que ancoram a predição na UTI e definem o horizonte em relação ao início da sepse (ver Planejamento do Estudo).