# Planejamento do Estudo

Versão: X.X | Data: DD/MM/AAAA | Fase: Planejamento

**Como usar este documento:**

- Este documento é fechado **antes** de ver qualquer resultado no conjunto de teste, para que as decisões não sejam guiadas pelos resultados. A versão **1.0** é congelada depois da execução-piloto e antes da execução completa: a partir dela, o documento não é mais editado e, por isso, a Data do cabeçalho fica sendo a data do congelamento. Mudanças posteriores são registradas como desvio do plano no documento Operação do Estudo.
- A versão começa em **0.1** quando o documento ganha o primeiro conteúdo e sobe 0.1 a cada revisão fechada (fim de um chat de revisão, não a cada pequena edição). A Data é a da última edição do documento.
- Marque só o que falta decidir com **[A decidir]**. O que não tem marcação já está decidido.
- Todo número, percentual ou estatística vem com a fonte ao lado, no formato (AUTOR, ANO). A referência completa fica só no documento Referências.
- Todo termo clínico ou técnico novo é definido no Apêndice C – Glossário e Fundamentação.
- Para remeter a outro documento, cite o documento inteiro (ex.: "ver Definição do Estudo"), nunca uma seção pelo nome.

## 7. Classificação da Pesquisa (opcional)

> Comum em TCCs e eventos brasileiros, rara em artigos internacionais. Classifique a pesquisa em quatro dimensões e justifique cada uma em uma frase:
>
> - **Natureza:** aplicada (resolve um problema prático) ou básica (amplia o conhecimento sem aplicação imediata)
> - **Abordagem:** quantitativa, qualitativa ou mista (uma análise quantitativa com uma análise qualitativa complementar, como a leitura de casos, pode ser classificada como mista)
> - **Objetivo:** exploratória, descritiva ou explicativa
> - **Procedimento:** experimental, estudo de caso, documental, *ex post facto* etc.
>
> ⚠️ Em estudos com dados retrospectivos, a manipulação acontece **no modelo** (o que entra nele, como é treinado), não nos pacientes, que não recebem nenhuma intervenção. Deixe claro em relação a quê cada classificação vale: o estudo pode ser experimental quanto aos modelos e observacional quanto aos pacientes. Pelo mesmo motivo, "explicativa" aqui se refere ao efeito de uma escolha de modelagem sobre o desempenho, nunca a causas clínicas.
>
> *Exemplo (ilustrativo, não é deste estudo):* "Pesquisa aplicada, de abordagem quantitativa e objetivo explicativo quanto ao efeito do método de preenchimento de valores ausentes sobre o desempenho do modelo, conduzida como experimento computacional sobre dados retrospectivos de prontuário eletrônico, sem intervenção nos pacientes."
>

## 8. Seleção do Contexto

> Torna concreto o contexto caracterizado na Definição do Estudo. Descreva:
>
>
> **O dataset**, em nível de descrição (os detalhes de extração vêm mais adiante neste documento):
>
> - Origem: instituição, país e período em que os dados foram registrados
> - Que pacientes e cenários de cuidado ele cobre (ex.: adultos e crianças, UTI clínica e cirúrgica)
> - Que tipos de dado contém (estruturados, texto, imagem, sinais) e como foram desidentificados
> - Versão usada e forma de acesso
>
> **As quatro dimensões de contexto** de Wohlin et al. (2012), cada uma com justificativa. Como elas foram pensadas para experimentos com pessoas, use a leitura adaptada:
>
> - **Offline vs. online:** o estudo usa dados já registrados, sem interferir no cuidado (offline), ou roda em tempo real no ambiente clínico (online)?
> - **Estudantes vs. profissionais:** sem participantes humanos, indique quem conduz o estudo e, se houver avaliação humana (ex.: leitura de casos), quem a faz e com que formação
> - **Problema de brinquedo vs. real:** dados reais de pacientes reais ou dados sintéticos/simplificados? Uma tarefa com relevância clínica real ou um exercício?
> - **Específico vs. geral:** os resultados valem para um hospital, um período e uma população específicos, ou para um cenário amplo?
>
> O ambiente técnico (máquinas, versões, bibliotecas) é descrito mais adiante neste documento, junto com os instrumentos.
>
> *Exemplo (ilustrativo, não é deste estudo):* "Banco público de radiografias de tórax de um único hospital, desidentificado pelos mantenedores e com acesso mediante cadastro. Offline: imagens já arquivadas, sem uso no atendimento. Conduzido por um estudante de graduação; a revisão dos casos de erro é feita pelo próprio estudante, sem formação clínica, o que é declarado como limitação. Problema real: exames reais com rótulos extraídos de laudos. Contexto específico: um hospital e uma população."
>

## 9. Hipóteses

> Só as QPs **confirmatórias** (ver Definição do Estudo) viram hipóteses. As exploratórias não têm hipótese formal.
>
>
> Cada QP confirmatória vira um par: **H0** (nula, "não há diferença") e **H1** (alternativa, "há diferença"). Os dados só permitem **rejeitar ou não rejeitar** H0, nunca provar que ela é verdadeira.
>
> - **Bicaudal (padrão):** H1 diz apenas que existe diferença
> - **Unicaudal:** H1 indica a direção da diferença. Só use com justificativa da literatura, definida **antes** de ver os resultados
>
> Em ML, a hipótese costuma comparar uma **métrica de desempenho** entre modelos avaliados nos mesmos dados, e não a média de um grupo de participantes. Escreva qual métrica e qual comparação; o teste estatístico que faz essa comparação é definido mais adiante neste documento.
>
> Use IDs ligados às QPs (H0-1 e H1-1 para a QP1) para manter a rastreabilidade.
>
> *Exemplo (ilustrativo, não é deste estudo), QP1:*
>
> - H0-1: AUROC_B = AUROC_A (o modelo com dados de admissão + sinais vitais (B) não difere, em AUROC, do modelo só com dados de admissão (A))
> - H1-1: AUROC_B ≠ AUROC_A (os dois modelos diferem em AUROC)

## 10. Variáveis

> Cuidado com a palavra "variável": ela tem dois sentidos neste documento. No sentido **experimental** (Wohlin et al., 2012), são os fatores, as variáveis controladas e as dependentes do estudo. No sentido de **ML**, são as entradas do modelo (*features*) e o que ele prevê (rótulo). Por isso esta seção tem duas partes.
>
>
> **Parte 1 — Variáveis do experimento**
>
> - **Fatores (variáveis independentes):** o que você manipula. Cada valor de um fator é um **tratamento**. Em ML, um tratamento normalmente é uma configuração de modelo: um conjunto de entradas, um algoritmo ou uma técnica de pré-processamento
> - **Variáveis controladas:** mantidas iguais em todos os tratamentos para não interferir no resultado (ex.: coorte, divisão treino/teste, algoritmo, sementes aleatórias, procedimento de ajuste de hiperparâmetros)
> - **Variáveis dependentes:** o que você mede, normalmente as métricas de desempenho. Cada uma precisa de **métrica** e **escala** (nominal, ordinal, intervalar ou razão). A escala define quais testes estatísticos poderão ser usados. Indique qual é a métrica principal (a do teste de hipótese) e quais são secundárias
>
> **Parte 2 — Especificação da tarefa de predição**
>
> - **Unidade de predição:** para o que o modelo gera uma predição (um paciente, uma internação, uma janela de horas)
> - **Rótulo (desfecho):** o que é previsto, com a **definição operacional**, isto é, o critério concreto nos dados que marca um caso como positivo. A definição conceitual (o que a condição é) fica no Apêndice C – Glossário e Fundamentação
> - **Entradas (*features*):** que grupos de dados são usados, de onde vêm e como são resumidos
> - **Janelas de tempo:** a janela de observação (de que período vêm os dados de entrada) e o horizonte de predição (com quanta antecedência o evento é previsto)
>
> ⚠️ Nenhuma entrada pode conter informação registrada **depois** do momento da predição. Isso é vazamento de dados (*data leakage*): o modelo pareceria ótimo no estudo e seria inútil na prática.
>
> *Exemplo (ilustrativo, não é deste estudo):*
>
> - Fator: conjunto de entradas. Tratamentos: só dados de admissão (A); dados de admissão + sinais vitais (B)
> - Controladas: coorte, divisão treino/teste, algoritmo, sementes e busca de hiperparâmetros iguais para A e B
> - Dependente principal: AUROC no conjunto de teste (valor contínuo entre 0 e 1; escala de razão)
> - Unidade de predição: internação. Rótulo: nova internação do mesmo paciente em até 30 dias após a alta. Entradas: idade, diagnósticos da admissão, média e mínimo dos sinais vitais. Janela de observação: da admissão até a alta; horizonte: 30 dias após a alta

## 11. Unidades de Análise

> Substitui a seção "Sujeitos" dos templates de Wohlin, porque não há participantes humanos. Descreva:
>
> - **Unidade de análise:** o que é contado e avaliado (paciente, internação, estadia na UTI, janela de tempo) e o que acontece quando um mesmo paciente tem várias internações (entra só a primeira? entram todas, mantendo o paciente inteiro no mesmo lado da divisão treino/teste?)
> - **População-alvo:** a quem os resultados se destinariam (ex.: adultos internados em UTI)
> - **População de estudo:** a parte dessa população que existe no dataset
> - **Critérios de inclusão e exclusão:** na ordem em que são aplicados, cada um com justificativa
> - **Amostragem:** em datasets retrospectivos, normalmente entram todas as unidades elegíveis. Em relação à população-alvo, isso é uma amostra por conveniência (um hospital, um período); declare isso como ameaça à validade externa
> - **Tamanho esperado:** número de unidades e, principalmente, de **casos positivos**, que limitam o que o modelo consegue aprender e a precisão das métricas. Estimativas feitas antes da extração precisam de fonte
>
> As contagens reais de cada etapa da seleção (quantas unidades entram e quantas saem por qual critério) só existem depois da extração: são registradas na Operação do Estudo e viram o fluxograma da coorte.
>
> *Exemplo (ilustrativo, não é deste estudo):* "Unidade: internação; pacientes com várias internações entram com todas elas, mas cada paciente fica inteiro no treino ou no teste. População-alvo: adultos que recebem alta hospitalar após internação por insuficiência cardíaca. Inclusão: idade ≥ 18 anos; diagnóstico principal de insuficiência cardíaca. Exclusão: óbito durante a internação (não há readmissão possível); transferência para outro hospital (desfecho não observável). Amostragem: todas as internações elegíveis do dataset."
>

## 12. Design Experimental

> Descreva o design e justifique cada escolha:
>
> - **O design:** quantos fatores e tratamentos (ex.: um fator com dois tratamentos)
> - **Pareado ou independente:** os termos *within-subjects* (cada sujeito recebe todos os tratamentos) e *between-subjects* (cada sujeito recebe um só) vêm de experimentos com pessoas. Em ML, a leitura é: **pareado** quando todos os modelos são avaliados nas mesmas unidades do conjunto de teste, e cada unidade recebe uma predição de cada modelo; **independente** quando cada modelo é avaliado em unidades diferentes. O pareado compara com mais precisão, porque a diferença entre os modelos não se mistura com a diferença entre os pacientes
> - **Estratégia de validação:** como os dados são divididos (treino, validação e teste, ou validação cruzada); qual é a unidade da divisão (ex.: por paciente, para que o mesmo paciente não apareça no treino e no teste); e quando o conjunto de teste é usado (uma única vez, no final, com todo ajuste feito sem ele)
> - **Os três princípios**, adaptados:
>     - **Aleatorização:** onde a divisão e o treino usam aleatoriedade, e qual semente é registrada
>     - **Bloqueio:** qual fator de incômodo é controlado e como (ex.: estratificar a divisão pelo desfecho, para que treino e teste tenham a mesma proporção de positivos)
>     - **Balanceamento:** no sentido de Wohlin, cada tratamento é avaliado no mesmo número de unidades; no design pareado isso é automático. ⚠️ Não confundir com o balanceamento de classes (reamostrar para igualar positivos e negativos), que é uma técnica de pré-processamento; se for usada, é descrita junto com o pré-processamento, mais adiante neste documento
> - **Referências (*baselines*):** modelos ou escores usados como comparação, e se entram no teste formal de hipótese ou servem só como referência descritiva
>
> *Exemplo (ilustrativo, não é deste estudo):* "Um fator (conjunto de entradas) com dois tratamentos, em design pareado: A e B são treinados com as mesmas unidades e avaliados no mesmo conjunto de teste. Divisão 80/20 por paciente, estratificada pelo desfecho, com semente 42. Hiperparâmetros ajustados por validação cruzada de 5 partições dentro do treino; o teste é usado uma única vez. Um escore clínico simples é reportado como referência descritiva, fora do teste formal."
>

## 13. Instrumentação

> Liste tudo que será usado, em quatro grupos, com o **status** de cada item (rascunho, testado ou final):
>
> - **Objetos (dados):** o dataset (origem, versão, licença e termos de uso, motivo da escolha) e quais tabelas ou arquivos dele são usados
> - **Procedimentos:** no lugar dos guias e treinamentos para participantes, descreva em nível de plano as etapas do pipeline: extração (ex.: consultas SQL), pré-processamento (limpeza, valores ausentes, valores fisiologicamente impossíveis, normalização, tratamento de texto ou imagem, balanceamento de classes, se houver) e modelos (algoritmos, bibliotecas). O que foi efetivamente executado fica registrado na Operação do Estudo
> - **Instrumentos de medição:** o código que calcula as métricas (biblioteca e função) e, se houver análise qualitativa, a ficha de registro com as categorias definidas antes
> - **Ambiente e recursos computacionais:** máquina (CPU, GPU, memória), sistema operacional, versões da linguagem, das bibliotecas e do banco de dados, IDE, controle de versão e se algo gera custo
>
> Faça uma **execução-piloto** antes da execução completa: rode o pipeline inteiro em uma amostra pequena para verificar se tudo funciona, **sem olhar resultados no conjunto de teste**.
>
> *Exemplo (ilustrativo, não é deste estudo):*
>
> - Objetos: banco público de prontuário eletrônico, versão X, acesso sob termo de uso; tabelas de admissões, diagnósticos e sinais vitais
> - Procedimentos: consultas SQL de extração; remoção de valores fisiologicamente impossíveis; preenchimento de valores ausentes pela mediana do treino; dois algoritmos de classificação do scikit-learn
> - Medição: função `roc_auc_score` do scikit-learn; ficha de revisão de erros com quatro categorias definidas antes da análise
> - Ambiente: notebook pessoal, 16 GB de RAM, sem GPU; Python 3.12; PostgreSQL; sem custo
> - Status: consultas testadas; execução-piloto prevista com 1% das internações

## 14. Plano de Análise

> Defina **antes** de ver os resultados no conjunto de teste, para evitar *fishing* (testar várias coisas até algo dar significativo). Para cada hipótese, registre:
>
> - **Estatística descritiva:** o que será reportado sobre a coorte (ex.: características por desfecho) e sobre os modelos (métricas com intervalo de confiança)
> - **Teste previsto:** qual teste compara os tratamentos e por que ele serve para a métrica e o design escolhidos. Em ML com design pareado, os mais comuns são:
>     - *bootstrap* pareado: reamostra as unidades de teste para estimar a variação da diferença entre as métricas; serve para qualquer métrica
>     - teste de DeLong: compara duas AUROCs calculadas nas mesmas unidades
>     - teste de McNemar: compara os acertos e erros de dois classificadores nas mesmas unidades
> - **Alternativa** caso as premissas do teste falhem
> - **Nível de significância (α)** e, se houver mais de uma hipótese, se haverá **correção para comparações múltiplas**
> - **O que será reportado:** o p-valor exato (não só "p < 0,05") e o **tamanho de efeito**. Em ML, o tamanho de efeito normalmente é a própria diferença entre as métricas, com intervalo de confiança. Se possível, defina antes qual diferença seria relevante na prática
> - **Limiar de decisão:** se alguma análise classificar cada predição como positiva ou negativa (ex.: métricas como sensibilidade, seleção de casos de acerto e erro), qual probabilidade separa as duas classes e como esse limiar é escolhido. A escolha é feita sem o conjunto de teste (ex.: no conjunto de validação)
> - **Critério para valores extremos e dados problemáticos**, também definido antes
> - **Análises exploratórias** (QPs exploratórias, explicabilidade, subgrupos, leitura de casos): o método previsto e o aviso de que os resultados serão apresentados como exploratórios. Para a leitura de casos, registre também o critério de seleção (ex.: todos os casos em que os modelos discordam, ou uma amostra aleatória deles), quantos casos serão lidos e a ficha de categorias usada
> - **Análises de sensibilidade:** repetições da análise principal trocando uma escolha discutível (ex.: outra definição do desfecho, outro tratamento de valores ausentes), para verificar se a conclusão se mantém. Liste-as antes e reporte-as separadamente da análise principal
> - **Ferramentas** (ex.: Python, com bibliotecas gratuitas)
>
> Confira no checklist TRIPOD+AI (Collins et al., 2024) quais medidas de desempenho e análises ele pede para relatar.
>
> *Exemplo (ilustrativo, não é deste estudo), H0-1:* "Características da coorte por desfecho (mediana e intervalo interquartil; proporções). AUROC de A e B no teste, com IC de 95%. Diferença AUROC_B − AUROC_A com IC de 95% por *bootstrap* pareado (1.000 reamostragens por paciente); p-valor exato; α = 0,05, bicaudal. Limiar de decisão: o que atinge sensibilidade de 80% no conjunto de validação. Análises exploratórias: diferença por faixa etária; leitura dos casos do teste em que B acertou e A errou (todos, até 40; acima disso, sorteio com semente 42), com a ficha de quatro categorias. Sensibilidade: repetir a comparação com readmissão em 90 dias. Python com scikit-learn e NumPy."
>

## 15. Ameaças à Validade

> Para cada ameaça, registre o **tipo** (conclusão, interna, construto ou externa), a **descrição**, **como afeta** o estudo, a **mitigação** e o **risco residual** (baixo, médio ou alto). Preencha no planejamento. A reavaliação depois da execução e da análise é feita em Análise e Interpretação do Estudo; esta lista permanece como estava na versão 1.0.
>
>
> Toda exclusão da delimitação do estudo (ver Definição do Estudo) que restrinja a generalização entra aqui como ameaça externa.
>
> *Exemplos (ilustrativos, não são deste estudo):*
>
> - **Interna, vazamento de dados:** entradas registradas depois do momento da predição, ou o mesmo paciente no treino e no teste, inflam o desempenho. Mitigação: divisão por paciente e corte de todas as entradas no momento da predição, com verificação no código. Risco residual: baixo.
> - **Construto, rótulo imperfeito:** o desfecho é identificado por códigos de cobrança, que nem sempre refletem a condição clínica real. Mitigação: usar um critério clínico reconhecido como definição operacional e comparar com os códigos. Risco residual: médio.
> - **Conclusão, poucos casos positivos:** com poucos positivos no teste, os intervalos de confiança ficam largos e diferenças reais podem não ser detectadas. Mitigação: design pareado e relato do intervalo de confiança da diferença. Risco residual: médio.
> - **Externa, um único hospital:** o dataset vem de uma instituição e de um período, e o desempenho pode cair em outro hospital. Mitigação: declarar a limitação e descrever a população para permitir comparação. Risco residual: alto.

## 16. Ética e Gestão de Dados

> Mesmo sem participantes, o estudo usa dados de pacientes reais. Descreva:
>
> - **Aprovação ética:** se o uso secundário de dados desidentificados precisa ser apreciado pelo **Comitê de Ética em Pesquisa (CEP)** da sua instituição. Pesquisas na área da saúde seguem, em geral, a Resolução CNS 466/2012; a Resolução CNS 510/2016 trata de Ciências Humanas e Sociais. Confirme com a instituição com antecedência e registre a resposta. Registre também a aprovação ética de origem do dataset e a justificativa para a dispensa de consentimento dos pacientes, como descrita pelos mantenedores
> - **Acesso e termos de uso:** como o acesso foi obtido (cadastro, treinamento exigido, termo de uso assinado) e o que os termos proíbem (ex.: redistribuir os dados, tentar reidentificar pacientes, enviar dados a serviços externos como APIs de IA online). Confira o que o termo do seu dataset diz
> - **Proteção dos dados:** os dados já chegam desidentificados; descreva como evitar reidentificação e exposição, sem registros individuais nem trechos de texto clínico em nada que seja publicado (notebooks, figuras, README). Considere a LGPD para dados brasileiros e as regras do país de origem e do termo de uso para dados estrangeiros
> - **Armazenamento:** onde os dados ficam, quem tem acesso, como a máquina é protegida, credenciais do banco fora do código e por quanto tempo os dados são mantidos
> - **Publicação do pacote:** o que pode ser publicado (código, consultas SQL, notebook sem saídas com dados individuais) e onde (ex.: GitHub, Zenodo), e o que não pode (os dados em si, que ficam com os mantenedores)
>
> *Exemplo (ilustrativo, não é deste estudo):* "Uso secundário de banco público desidentificado; o CEP da instituição informou por e-mail que não há necessidade de apreciação. Acesso obtido após curso de ética em pesquisa e assinatura do termo de uso, que proíbe redistribuição e tentativa de reidentificação. Dados em PostgreSQL local, em disco criptografado, acessíveis só à pesquisadora; credenciais em arquivo fora do repositório (listado no `.gitignore`). Repositório público com código e consultas; notebook publicado sem saídas que mostrem registros individuais; dados não publicados."
>