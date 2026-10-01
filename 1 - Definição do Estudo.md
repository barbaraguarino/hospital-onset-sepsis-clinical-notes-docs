# Definição do Estudo

**Versão**: 0.1 | **Data**: 28/09/2026 | **Fase**: Definição

**Como usar este documento:**

* Marque só o que falta decidir com **\[A decidir]**. O que não tem marcação já está decidido.
* A versão **1.0** é congelada depois da execução-piloto e antes da execução completa: a partir dela, o documento não é mais editado e, por isso, a Data do cabeçalho fica sendo a data do congelamento. Mudanças posteriores são registradas como desvio do plano no documento Operação do Estudo.
* A versão começa em **0.1** quando o documento ganha o primeiro conteúdo e sobe 0.1 a cada revisão fechada (fim de um chat de revisão, não a cada pequena edição). A Data é a da última edição do documento.
* Todo número, percentual ou estatística vem com a fonte ao lado, no formato (AUTOR, ANO). A referência completa fica só no documento Referências.
* Todo termo clínico ou técnico novo é definido no Apêndice C – Glossário e Fundamentação.
* Para remeter a outro documento, cite o documento inteiro (ex.: "ver Planejamento do Estudo"), nunca uma seção pelo nome.

## 1\. Motivação e Problema

A sepse é definida, pelo consenso Sepsis-3, como uma disfunção orgânica com risco de vida causada por uma resposta desregulada do hospedeiro a uma infecção (SINGER et al., 2016). Operacionalmente, a disfunção orgânica é identificada quando um paciente com infecção suspeita ou confirmada apresenta um aumento agudo de pelo menos 2 pontos no escore SOFA (*Sequential Organ Failure Assessment*) em relação a um valor basal (SINGER et al., 2016). Este estudo trata da sepse de início hospitalar (*hospital-onset sepsis*, HOS), em que a infecção e a disfunção orgânica se desenvolvem mais de 48 horas após a admissão hospitalar, distinta da sepse comunitária (*community-onset sepsis*, COS), já presente na admissão (GINESTRA et al., 2024). As definições dos termos clínicos e técnicos usados nesta seção, incluindo a composição do SOFA, estão no Apêndice C – Glossário e Fundamentação.

O reconhecimento precoce é prioritário: mesmo uma disfunção orgânica modesta no momento em que se suspeita da infecção está associada a mortalidade hospitalar superior a 10% (SINGER et al., 2016). Na sepse comunitária, a melhoria no reconhecimento e na intervenção oportuna reduziu significativamente a mortalidade nas últimas duas décadas, mas os desfechos da HOS permanecem comparativamente piores (GINESTRA et al., 2024). Em comparação com pacientes com sepse comunitária, os pacientes com HOS têm duas vezes mais chance de necessitar de ventilação mecânica e de internação em Unidade de Terapia Intensiva (UTI), tempo de internação mais que duas vezes maior, tanto na UTI quanto no hospital, e duas vezes mais chance de óbito (GINESTRA et al., 2024), além de maior custo hospitalar (PAGE; DONNELLY; WANG, 2015). Na UTI, o peso é particularmente alto: segundo uma revisão sistemática com meta-análise, 48,7% dos casos de sepse com disfunção orgânica tratados em UTI têm origem hospitalar (intervalo de confiança de 95%, IC 95%: 38,3–59,3%), com mortalidade de aproximadamente 52,3% nesse grupo (IC 95%: 43,4–61,1%) (MARKWART et al., 2020). Parte dos fatores de risco da HOS, no entanto, pode ser modificável: pacientes com HOS têm menor probabilidade de receber investigação e tratamento da infecção em tempo oportuno do que os com sepse comunitária (GINESTRA et al., 2024).

O reconhecimento é justamente onde a prática atual encontra dificuldade. O paciente que desenvolve uma infecção durante a internação frequentemente já apresenta alterações fisiológicas causadas pela doença que motivou a internação, o que dificulta distinguir sinais novos dos antigos, e pode apresentar com menos frequência os sinais típicos de infecção, o que contribui para incerteza diagnóstica e atrasos no reconhecimento e no tratamento (GINESTRA et al., 2024). Os mesmos autores apontam que esses pacientes podem se beneficiar de ferramentas de apoio ao diagnóstico e à decisão, que o volume de dados registrados no prontuário eletrônico do paciente (PEP) antes, durante e depois de um episódio de HOS torna o tema uma oportunidade de pesquisa, e listam, entre as prioridades de pesquisa, a incorporação das características específicas da HOS no desenvolvimento de sistemas de alerta precoce e a padronização da identificação de casos (GINESTRA et al., 2024). O PEP reúne tanto dados estruturados, como sinais vitais e exames laboratoriais, quanto notas clínicas em texto livre (YAN et al., 2022). A maioria dos modelos de predição de sepse baseados no PEP usa apenas dados estruturados (AMROLLAHI et al., 2020), em parte pela complexidade de processar texto livre (YAN et al., 2022), mas há evidência de que as notas clínicas carregam informação complementar à dos dados estruturados para a predição precoce de sepse em pacientes de UTI (AMROLLAHI et al., 2020). O uso pretendido de um modelo desse tipo é o de ferramenta de apoio à decisão clínica, na forma de alerta de risco, sem substituir o julgamento clínico. Em um cenário futuro de aplicação, não avaliado neste estudo, os beneficiários potenciais seriam os pacientes de UTI, com possível redução de morbimortalidade; a equipe assistencial, com alerta precoce para apoio à decisão; e o sistema de saúde, com possível redução de custo e de tempo de internação.

Estudos anteriores, entre eles uma revisão sistemática, já examinaram o ganho do texto clínico sobre os dados estruturados na predição de sepse em geral (AMROLLAHI et al., 2020; YAN et al., 2022), mas, nos trabalhos revisados, esse ganho não foi avaliado para a sepse de início hospitalar como entidade distinta, com marco temporal na admissão hospitalar — e, por consequência, também não se sabe em quais casos específicos de HOS a informação textual altera a predição do modelo. O detalhamento dessa lacuna vem adiante, na discussão da literatura.

## 2. Trabalhos Relacionados

> Não precisa ser uma revisão sistemática completa. O objetivo é mostrar a relevância do tema, justificar a contribuição e evitar afirmar uma novidade que não existe, que é o ponto em que avaliadores costumam atacar.
>
>
> Organize em três partes:
>
> **Estratégia de busca.** Permite que outra pessoa refaça a busca e delimita até onde vale a afirmação de novidade. Registre:
>
> - Bases consultadas (ex.: PubMed, IEEE Xplore, ACM Digital Library, Scopus, Google Scholar)
> - Termos usados (combinações de termos da condição clínica, do tipo de dado e do método)
> - Data da busca
> - Critérios de inclusão e exclusão
> - *Snowballing*, se usado: seguir as referências dos artigos encontrados (*backward*) ou os artigos que os citam (*forward*)
>
> **Síntese comparativa.** Organizada por tema, não como um resumo por artigo: o que existe, o que os estudos têm em comum, onde divergem e qual é a lacuna. Uma tabela ajuda. Colunas típicas em ML para saúde: estudo (AUTOR, ANO), dataset, população, definição do desfecho, dados de entrada, modelo, métrica principal e tipo de validação (interna, no mesmo dataset, ou externa, em outro).
>
> O resumo de cada artigo fica no Apêndice B – Matriz de Literatura; aqui entra só a comparação. Antes de citar um artigo, confirme na fonte primária que ele existe (autores, ano e periódico), principalmente se foi sugerido por outra IA.
>
> **Contribuição pretendida.** Tipo e justificativa. Tipos comuns em ML para saúde:
>
> - Recorte de população ou desfecho ainda não estudado
> - Nova combinação de fontes de dados (ex.: dados estruturados + texto, dados estruturados + imagem)
> - Replicação ou validação em outro dataset
> - Nova forma de avaliação ou análise (ex.: análise de erro, análise por subgrupo)
> - Outro
>
> Escreva a novidade como "não encontrada na literatura revisada", nunca como "inédita": a afirmação só vale até onde a busca alcançou.
>
> *Exemplo (ilustrativo, não é deste estudo):* **Tipo:** replicação em outro dataset. **Justificativa:** os modelos de predição de readmissão revisados foram avaliados apenas no hospital de origem; este estudo avalia um deles em uma base de outro país, com população e forma de registro diferentes.
>

## 3. Definição do Objetivo

> Preencha o template de definição de objetivo (Wohlin et al., 2012). Se houver mais de um objetivo, repita o template. Cada Questão de Pesquisa deve ser rastreável a um objetivo.
>
>
> Analisar **<objeto de estudo: o que é analisado, ex.: um modelo, uma fonte de dados, um método>**
> com o propósito de **<avaliar, comparar, caracterizar, prever...>**
> com respeito a **<foco de qualidade: o aspecto medido, ex.: desempenho preditivo, interpretabilidade>**
> do ponto de vista de **<perspectiva: para quem o resultado importa, ex.: pesquisador, equipe clínica>**
> no contexto de **<ambiente: onde o estudo acontece, ex.: dataset, população, cenário de cuidado>**
>
> *Exemplo (ilustrativo, não é deste estudo):* Analisar **modelos de classificação de radiografias de tórax** com o propósito de **compará-los** com respeito à **capacidade de distinguir exames com e sem pneumonia** do ponto de vista do **pesquisador** no contexto de **exames retrospectivos de adultos de um banco de imagens público**.
>

## 4. Questões de Pesquisa

> Derivam do objetivo e servem de ponte para as hipóteses, formalizadas no Planejamento do Estudo.
>
>
> Classifique cada QP:
>
> - **Confirmatória:** testa uma expectativa definida antes de ver os dados. Recebe hipótese formal (nula e alternativa) no Planejamento do Estudo.
> - **Exploratória:** investiga um padrão sem hipótese formal. Os resultados são apresentados como exploratórios, sem conclusão de causa nem de generalização.
>
> **Regra prática:** cada QP precisa ser respondível com dados. Para a QP confirmatória, deve ser possível imaginar a métrica e a comparação que a respondem; para a exploratória, o tipo de análise (ex.: inspeção de casos, análise por subgrupo). Se não dá para imaginar, a QP ainda está vaga.
>
> *Exemplos (ilustrativos, não são deste estudo):*
>
> - QP1 (confirmatória): "Acrescentar os sinais vitais registrados ao longo da internação aos dados de admissão melhora a predição de readmissão em 30 dias?"
> - QP2 (exploratória): "Em quais grupos de pacientes os dois modelos mais discordam?"

## 5. Caracterização do Contexto

> Wohlin et al. (2012) classificam o estudo cruzando a quantidade de **sujeitos** (quem aplica o tratamento) e a de **objetos** (sobre o que o tratamento é aplicado):
>
>
>
> |  | 1 objeto | Vários objetos |
> | --- | --- | --- |
> | **1 sujeito** | Objeto único | Variação multiobjeto |
> | **Vários sujeitos** | Teste múltiplo dentro do objeto | Bloqueado sujeito-objeto |
>
> Essa classificação foi pensada para experimentos com pessoas. Em um estudo computacional, sem participantes humanos, os papéis precisam ser adaptados, e a adaptação precisa ficar explícita. Uma forma possível (adaptação, não definida por Wohlin):
>
> - **Tratamento:** cada configuração comparada (ex.: o modelo com e sem uma fonte de dados)
> - **Sujeito:** quem ou o que aplica os tratamentos (ex.: o pipeline de treino e avaliação)
> - **Objeto:** o conjunto de dados sobre o qual os tratamentos são aplicados
>
> Registre a classificação escolhida, o mapeamento usado e a justificativa.
>
> As quatro dimensões de contexto (offline vs. online, estudantes vs. profissionais, problema de brinquedo vs. real, específico vs. geral) ficam no Planejamento do Estudo.
>
> *Exemplo (ilustrativo, não é deste estudo):* um estudo que compara dois algoritmos em três bases públicas de eletrocardiograma, todos executados pelo mesmo pipeline, seria uma variação multiobjeto (um sujeito, vários objetos).
>

## 6. Delimitação do Estudo

> Deixe explícito o que **está dentro** e o que **fica fora** do estudo, com uma justificativa curta para cada exclusão. Dimensões para pensar em ML para saúde:
>
> - **Tarefa e desfecho:** qual condição é predita e com qual definição; quais outras definições ou desfechos ficam de fora
> - **População:** quais pacientes e cenários de cuidado entram (ex.: adultos, UTI), em nível geral. Os critérios detalhados ficam no Planejamento do Estudo
> - **Dados:** quais fontes e modalidades são usadas (estruturados, texto, imagem, sinais) e quais não
> - **Métodos:** quais famílias de modelos e técnicas são comparadas, e quais variações ficam de fora
> - **Avaliação:** o que é medido e o que deliberadamente não é (ex.: validação em outro hospital, custo-efetividade)
> - **Uso:** estudo retrospectivo com dados já coletados vs. teste em uso clínico real
> - **Tempo:** período coberto pelos dados e horizonte da predição (com quanta antecedência o evento é previsto)
>
> Toda exclusão que restrinja a generalização reaparece como ameaça à validade externa no Planejamento do Estudo. Exclusões motivadas por prazo ou viabilidade também entram no Apêndice A – Registro de Decisões.
>
> *Exemplo (ilustrativo, não é deste estudo):*
>
> **Dentro do escopo:** predição de readmissão em 30 dias após a alta de pacientes adultos com insuficiência cardíaca, usando dados estruturados do prontuário eletrônico de um dataset público e comparando dois algoritmos de classificação em avaliação retrospectiva.
>
> **Fora do escopo:**
>
> - Notas clínicas e imagens: exigiriam pipelines próprios de processamento e mais tempo do que o viável em um estudo individual
> - Outros desfechos (mortalidade, tempo de internação): mudariam a tarefa estudada e exigiriam outro rótulo e outra avaliação
> - Validação em outro hospital: não há segunda base disponível no prazo
> - Uso clínico real: exigiria estudo prospectivo e aprovação ética própria, fora de um estudo retrospectivo