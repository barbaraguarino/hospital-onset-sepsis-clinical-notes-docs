# Apêndice C — Glossário e Fundamentação

**Versão**: 0.4 | **Data**: 02/10/2026 | **Fase**: Todas (documento de apoio)

**Como usar este documento:**

- É o guia dos conceitos do estudo: quase uma fundamentação teórica, só que mais simples. É escrito aos poucos, conforme os termos aparecem nos outros documentos ou nas leituras; não precisa estar completo desde o início.
- **Conceitos do Domínio** = o que se estuda: a condição clínica, os termos clínicos e as siglas, e os construtos medidos. **Conceitos Metodológicos** = como se estuda: ML, estatística, processamento de texto e métodos de pesquisa. Na dúvida, pergunte: "isso existiria mesmo sem ML?" Se sim, é do domínio.
- Entradas em ordem alfabética dentro de cada seção. Siglas aparecem por extenso no título da entrada (ex.: "UTI — Unidade de Terapia Intensiva").
- Escreva com suas palavras. É material de estudo: a explicação não precisa de fonte. Fonte só quando a entrada trouxer número ou afirmação que vá para o artigo, e então de uma referência já registrada em Referências ou de um material da disciplina. Não se buscam referências novas para o Glossário.
- A versão começa em **0.1** quando o documento ganha o primeiro conteúdo e sobe 0.1 a cada revisão fechada (fim de um chat de revisão, não a cada pequena edição). O documento vira **1.0** na entrega final (04/12/2026). A Data é a da última edição do documento.
- Para indicar onde o termo aparece, cite o documento inteiro, nunca uma seção pelo nome.
## Conceitos do Domínio

**Apoio à decisão clínica** (*clinical decision support*)

Apoio à decisão clínica é o uso de sistemas no computador que juntam informações clínicas e dados do próprio paciente para ajudar a decidir sobre o cuidado. Como o nome diz, o sistema apoia a decisão: organiza a informação e sinaliza o que merece atenção, mas quem decide é o profissional. Os modelos de predição em saúde são o exemplo mais típico, porque esse é o uso principal deles. Eles ajudam a decidir se o paciente deve fazer mais exames, se precisa ser acompanhado mais de perto por risco de piora ou se um tratamento deve começar (COLLINS et al., 2024, p. 1).

No caso da sepse de início hospitalar, GINESTRA et al. (2024, p. 1423) defendem pesquisar quais pacientes e quais formas de apresentação geram mais dúvida no diagnóstico e poderiam se beneficiar de ferramentas de apoio ao diagnóstico e à decisão. Para eles, só dá para confiar clinicamente nessas ferramentas se antes se entender como a HOS se manifesta. É nesse papel que a Definição do Estudo coloca o uso pretendido do modelo: um alerta de risco que apoia o julgamento clínico, sem substituí-lo.

Aparece em: Definição do Estudo.

**CID — Classificação Internacional de Doenças** (*International Classification of Diseases*, ICD)

A CID é um sistema de categorias. Cada caso de doença é colocado numa categoria segundo critérios fixos. As categorias cobrem todas as condições num número que dá para manejar e são agrupadas para facilitar o registro de mortes. Quem produz a CID é a Organização Mundial da Saúde. Os Estados Unidos mantêm versões ampliadas, as Modificações Clínicas (*Clinical Modifications*, CM), usadas para registrar adoecimento e para epidemiologia. O número depois da sigla indica a revisão: CID-9 é a nona revisão, CID-10 é a décima (SINGER et al., 2016, p. 5). Cada diagnóstico vira um código. No MIMIC-III, por exemplo, o código 038.9 da CID-9 quer dizer "septicemia não especificada" (JOHNSON et al., 2016, p. 3). O Sepsis-3 considera "septicemia" um termo estreito demais (SINGER et al., 2016, p. 5), o que mostra que os códigos nem sempre acompanham as definições atuais.

A CID é uma classificação, e não uma terminologia de referência. Classificações agrupam casos em categorias úteis para estatística e administração. Terminologias de referência, como o SNOMED CT, representam conceitos clínicos com mais detalhe e com relações formais entre eles (A04 – Interoperabilidade e padrões clínicos, 2026, p. 3). Pense num arquivo de gavetas: ele serve para guardar e contar casos, não para descrever cada caso em detalhe.

Para pesquisa com prontuário, os códigos da CID têm duas limitações.

1. **Tempo.** Médicos ou codificadores profissionais registram os códigos para faturamento, com atraso de dias a meses (YAN et al., 2022, Tabela 2, p. 564). No MIMIC-III, eles fazem parte dos dados registrados principalmente para cobrança e administração (JOHNSON et al., 2016, Tabela 3, p. 4) e ficam na tabela `DIAGNOSES_ICD` (JOHNSON et al., 2016, Tabela 4, p. 7).
2. **Significado.** Um código administrativo pode refletir faturamento, suspeita ou regras locais, e não o estado clínico final do paciente (Atividade 04 – Tarefa rótulo coorte tempo vazamento, 2026, p. 5). Na sepse, o Sepsis-3 aponta que cada estudo escolhia os códigos da CID-9 e da CID-10 de um jeito, o que piorou a confusão entre definições (SINGER et al., 2016, p. 5).
   Mesmo assim, três dos nove estudos revisados por YAN et al. (2022, p. 561) usaram códigos da CID para selecionar a coorte.

Na Definição do Estudo, os "diagnósticos codificados" são os códigos da CID. Eles ficam fora do escopo como definição de sepse e como dado de entrada, pelos motivos registrados na Definição do Estudo. Também não são usados para identificar disfunção orgânica anterior à infecção (Desenho do Estudo).

Aparece em: Definição do Estudo.

**COS — Sepse Comunitária** (*Community-Onset Sepsis*)

A sepse comunitária é a que o paciente já traz quando chega ao hospital. A infecção começou fora dele, e o diagnóstico costuma ser feito no pronto-socorro (GINESTRA et al., 2024, p. 1421–1422). É o tipo de sepse mais estudado. A maior parte da pesquisa sobre tratamento da sepse, incluindo os maiores ensaios clínicos, foi feita com pacientes com COS. Nas últimas duas décadas, reconhecer e tratar mais cedo esses pacientes reduziu bastante a mortalidade (GINESTRA et al., 2024, p. 1422). Nos estudos com COS, o horário da triagem no pronto-socorro costuma servir de "tempo zero", o momento em que o episódio começa a contar. Esse recurso não existe para quem adoece já internado (GINESTRA et al., 2024, p. 1425).

A COS também é diferente da HOS no tipo de infecção. Pneumonia, infecção urinária e infecção de pele e partes moles são mais comuns na COS. Já infecção na corrente sanguínea e infecção dentro do abdome são mais comuns na HOS (GINESTRA et al., 2024, p. 1422). A fronteira entre as duas nem sempre é clara: quem chega com infecção pode só receber o diagnóstico de sepse depois de 48 horas de internação, porque a doença piorou ou porque o diagnóstico atrasou (GINESTRA et al., 2024, p. 1422).

Aparece em: Definição do Estudo.

**Disfunção orgânica** (*organ dysfunction*)

Disfunção orgânica é quando um órgão ou sistema do organismo deixa de funcionar como deveria. O SOFA avalia seis desses sistemas, cada um por uma variável própria: a oxigenação do sangue no sistema respiratório; as plaquetas na coagulação; a bilirrubina no fígado; a pressão arterial e a dose de medicamentos para mantê-la no sistema cardiovascular; a Escala de Coma de Glasgow, que mede o nível de consciência, no sistema nervoso central; e a creatinina e o volume de urina nos rins (SINGER et al., 2016, Tabela 1, p. 23). Mesmo quando é grave, a disfunção orgânica da sepse não vem acompanhada de morte de muitas células (SINGER et al., 2016, p. 5). O consenso entende que ela resulta de defeitos no funcionamento das células, que aparecem como alterações fisiológicas e bioquímicas nos órgãos (SINGER et al., 2016, p. 7).

**Definição conceitual.** No Sepsis-3, o que separa a sepse de uma infecção comum é a resposta desregulada do organismo somada à disfunção orgânica. Essa disfunção pode passar despercebida, e por isso qualquer disfunção orgânica sem explicação deve fazer pensar numa infecção por trás dela (SINGER et al., 2016, Box 2, p. 19). Na prática, o consenso reconhece a disfunção orgânica por um aumento agudo de 2 pontos ou mais no SOFA total, causado pela infecção. O aumento é medido a partir do SOFA basal, o valor de antes da infecção. Esse basal deve ser considerado zero, a não ser que se saiba que o paciente já tinha disfunção orgânica, aguda ou crônica, antes da infecção começar (SINGER et al., 2016, p. 8 e Box 3, p. 20). O limite de 2 pontos pesa no prognóstico. Em pacientes internados com suspeita de infecção, SOFA de 2 ou mais corresponde a um risco geral de morte de cerca de 10%. Dependendo do risco que o paciente já tinha, esse risco de morrer é de 2 a 25 vezes maior do que o de quem tem SOFA abaixo de 2 (SINGER et al., 2016, p. 8).

Essa definição deixa duas lacunas que importam para este estudo. A primeira é que os autores do consenso não explicam como saber se havia disfunção antes da infecção, e por isso cada estudo aplica o basal de um jeito (GINESTRA et al., 2024, p. 1425). A segunda é que nenhuma das medidas avaliadas separa disfunção crônica de aguda nem verifica se a disfunção tem outra causa além da infecção. Também não se sabe qual é a melhor janela de tempo para medir a variação do SOFA (SEYMOUR et al., 2016, p. 12).

**Definição operacional.** O SOFA é calculado de hora em hora numa janela de avaliação que vai de 48 horas antes a 24 horas depois do início da infecção suspeita. Em cada hora, cada componente entra com o pior valor registrado nas 24 horas anteriores. É a mesma janela do estudo que validou os critérios do Sepsis-3. Os autores a escolheram porque a disfunção orgânica pode aparecer antes, perto ou depois do momento em que a infecção é reconhecida (SEYMOUR et al., 2016, p. 4). Há disfunção orgânica quando o SOFA sobe 2 pontos ou mais entre o menor valor horário da janela e um valor posterior dentro dela. Esse valor posterior precisa ter sido registrado depois do fim da janela de observação, ou seja, mais de 48 horas após a admissão no hospital. Sem medida anterior ao aumento, o basal é zero, a não ser que as próprias medidas da janela mostrem disfunção anterior. Diagnósticos codificados não são usados para isso (Desenho do Estudo). Alguns detalhes da extração continuam abertos: a tolerância de tempo para parear cada PaO₂ com uma FiO₂, a regra da Escala de Glasgow em pacientes intubados, de onde vem o peso usado nas doses de vasopressor e os limites de valores impossíveis do ponto de vista fisiológico: **[A decidir]** (Metodologia).

Aparece em: Definição do Estudo.

**HOS — Sepse de Início Hospitalar** (*Hospital-Onset Sepsis*)

A sepse de início hospitalar é a que começa durante a internação. O paciente foi internado por outro motivo e, já no hospital, pega uma infecção que evolui para sepse. Até um quarto dos casos de sepse surge assim (GINESTRA et al., 2024, p. 1421). O desfecho desses pacientes é pior: a mortalidade hospitalar é de 35% na HOS e de 25% na COS (GINESTRA et al., 2024, p. 1422). É esse o desfecho que o modelo deste estudo tenta prever.

GINESTRA et al. (2024) defendem estudar a HOS como uma entidade clínica própria, e não como uma sepse que por acaso começou no hospital. Os pacientes com HOS costumam ter mais doenças crônicas, e as infecções vêm de outros lugares, com mais casos na corrente sanguínea e no abdome (p. 1422). Eles mostram menos os sinais típicos de infecção, como respiração e batimentos acelerados, febre e glóbulos brancos altos. Em compensação, pressão baixa, troca de gases prejudicada nos pulmões e temperatura normal ou baixa são mais comuns (p. 1422–1423). Reconhecer a HOS é difícil porque o paciente internado muitas vezes já tem alterações causadas pela doença que o levou ao hospital, e fica difícil separar os sinais novos dos antigos (p. 1423).

**Definição conceitual.** Pelos critérios dos Centers for Disease Control and Prevention (CDC), é a sepse em que tanto a infecção quanto a disfunção orgânica aparecem mais de 48 horas depois da admissão no hospital. Na prática, HOS e COS podem se sobrepor (GINESTRA et al., 2024, p. 1422). Os critérios de vigilância usados para identificar casos em dados de prontuário, o Sepsis-3 e o *Adult Sepsis Event* do CDC, foram feitos para epidemiologia e contam o tempo em dias do calendário, não em horas (GINESTRA et al., 2024, p. 1425).

**Definição operacional.** O rótulo y vale 1 quando algum episódio de infecção suspeita cumpre o critério de disfunção orgânica e, nesse episódio, o antibiótico e a cultura acontecem os dois depois do fim da janela de observação e antes da alta ou do óbito. O fim da janela é 48 horas após a admissão no hospital. O início da HOS é o começo do primeiro episódio que cumpre o critério. O antibiótico tem que ter sido iniciado depois da janela; não vale um tratamento que só continuou. O corte usa 48 horas contínuas, e não dias do calendário, porque é mais simples de implementar sempre do mesmo jeito. Pacientes cuja sepse começou dentro da janela de observação ficam fora da coorte, para não serem rotulados como negativos (Desenho do Estudo). Como diferenciar um antibiótico novo da renovação de uma receita já em uso: **[A decidir]** (Desenho do Estudo).

Aparece em: Definição do Estudo.

**Infecção hospitalar** (*hospital-acquired infection*, também *healthcare-associated infection*)

Infecção hospitalar é qualquer infecção que o paciente adquire dentro de uma instituição de saúde. Também é chamada de infecção nosocomial ou infecção associada aos cuidados de saúde.

Infecção hospitalar e HOS não são a mesma coisa. Toda HOS começa com uma infecção que surge no hospital, mas só vira sepse quando há disfunção orgânica (ver as entradas de sepse e de HOS, neste glossário). GINESTRA et al. (2024, p. 1426) mostram a relação nos dois sentidos:

- **Da infecção para a HOS.** Um em cada quatro pacientes com infecção hospitalar de notificação obrigatória (*reportable*) desenvolve HOS. Entre os que têm infecção da corrente sanguínea associada a cateter central, são mais de um em cada dois.
- **Da HOS para a infecção.** Essas infecções de notificação obrigatória explicam só 14% das infecções que levam à HOS. Das demais, 43% são pneumonias, e 35% dessas estão associadas à ventilação mecânica.
  A infecção hospitalar também atrapalha o reconhecimento da HOS. Quando um paciente internado piora, a causa pode ser uma infecção adquirida no hospital. Mas também pode ser a progressão de uma doença não infecciosa, a piora de uma doença crônica ou uma complicação do próprio tratamento (GINESTRA et al., 2024, p. 1423).

Não confundir com infecção suspeita. Infecção suspeita é a forma de identificar uma infecção nos dados, pela combinação de antibiótico e cultura (ver a entrada de infecção suspeita, neste glossário).

Na Definição do Estudo, a infecção hospitalar sem disfunção orgânica está entre os desfechos fora do escopo, pelo motivo registrado na Definição do Estudo.

Aparece em: Definição do Estudo.

**Infecção suspeita** (*suspected infection*)

Infecção suspeita é quando a equipe desconfia de uma infecção e passa a agir como se ela existisse: colhe material, como sangue ou urina, para exame de cultura e começa um antibiótico. Tudo isso acontece antes de haver confirmação. Resultados de laboratório levam dias para ficar disponíveis no prontuário (YAN et al., 2022, Tabela 2, p. 564), e tratar logo pode melhorar o desfecho dos pacientes com sepse (SINGER et al., 2016, p. 4).

**Definição conceitual.** O Sepsis-3 trata a infecção como o gatilho da sepse, mas não se propôs a redefinir o que é infecção (SINGER et al., 2016, p. 4). O consenso reconhece que a infecção quase nunca está confirmada por exame quando o tratamento começa. Mesmo depois de concluídos os exames, só 30% a 40% dos casos de sepse têm cultura positiva. Por isso, os estudos epidemiológicos precisam de indicadores indiretos, como o início de antibiótico ou a probabilidade de infecção estimada pela equipe (SINGER et al., 2016, p. 13). Para pesquisas com dados de prontuário, o consenso sugere identificar a infecção suspeita pela combinação de antibiótico, oral ou parenteral (injetável), com cultura de fluidos do corpo, como sangue, urina, líquor e líquido do abdome, dentro de um prazo definido (SINGER et al., 2016, Tabela 2, nota b, p. 24). O estudo que validou os critérios do Sepsis-3 usou exatamente essa combinação, contando só antibióticos não profiláticos, isto é, não usados apenas para prevenir (SEYMOUR et al., 2016, Tabela 2, p. 22). Ele também fixou a ordem e o prazo entre os dois eventos. Se o antibiótico veio primeiro, a cultura precisa ter sido colhida em até 24 horas. Se a cultura veio primeiro, o antibiótico precisa ter sido prescrito em até 72 horas. O início da infecção é o horário do primeiro dos dois (SEYMOUR et al., 2016, p. 4). Os autores avisam que só estudaram pacientes em que já havia suspeita de infecção. O estudo não trata de como diagnosticar infecção quando a disfunção orgânica é o primeiro sinal (SEYMOUR et al., 2016, p. 11).

**Definição operacional.** O estudo usa a mesma combinação e os mesmos prazos: antibiótico registrado na tabela `PRESCRIPTIONS` e cultura de fluido corporal registrada na tabela `MICROBIOLOGYEVENTS`. A cultura conta pela coleta, seja qual for o resultado. O início da infecção é o primeiro dos dois eventos (Desenho do Estudo; Dados). A tabela `PRESCRIPTIONS` só registra a data de início do antibiótico, sem hora, e parte das culturas também só tem data. Nesses casos, usa-se 00h00 da data registrada. Essa convenção é conservadora para a HOS porque adianta o episódio: um antibiótico ou uma cultura só conta como posterior à janela se a data for depois do dia em que a janela termina (Desenho do Estudo). Três mapeamentos continuam abertos e serão fixados antes de olhar as contagens do desfecho: quais medicamentos contam como antibiótico, quais vias contam como oral ou parenteral e quais tipos de amostra contam como fluido corporal: **[A decidir]** (Dados).

Aparece em: Definição do Estudo.

**LOINC — Identificadores Lógicos de Observação, Nomes e Códigos** (*Logical Observation Identifiers Names and Codes*; nome em tradução livre)

O LOINC é uma base de identificadores universais para resultados de exames de laboratório e de outras medidas clínicas. Ele serve para facilitar a troca e a junção desses resultados entre instituições, no cuidado, na gestão de desfechos e na pesquisa. É produzido pelo Regenstrief Institute. Cada observação é descrita por atributos: o componente medido, a propriedade, o tempo, o sistema, a escala e o método (A04 – Interoperabilidade e padrões clínicos, 2026, p. 4).

Junto com o SNOMED CT, o LOINC fornece conceitos e códigos para a interoperabilidade semântica, que é a preservação do significado do dado quando ele passa de um sistema para outro (A04 – Interoperabilidade e padrões clínicos, 2026, p. 3). Terminologias grandes como o LOINC têm manutenção e formatos próprios (Apostila 01 – Interoperabilidade em Saúde e HL7 e FHIR, 2026, p. 21).

Funciona como o código de barras de um produto. Cada laboratório pode dar ao mesmo exame um nome ou uma abreviação diferente, mas o código identifica o exame do mesmo jeito em qualquer lugar. Converter os nomes locais em códigos, porém, não é automático. Mapear um vocabulário em outro exige governança e análise de perda de significado (A04 – Interoperabilidade e padrões clínicos, 2026, p. 4).

No MIMIC-III, cada medida é identificada por um código local, o `ITEMID`. O nome do conceito fica em tabelas de dicionário, como `D_ITEMS` e `D_LABITEMS` (JOHNSON et al., 2016, p. 6 e Tabela 4, p. 7). Pesquisadores da National Library of Medicine mapearam para o LOINC os exames de laboratório do MIMIC-II, a versão anterior da base, e os autores relatam outros esforços de mapeamento para dicionários padronizados (JOHNSON et al., 2016, p. 5).

Na Definição do Estudo, a padronização por LOINC fica fora do escopo, pelo motivo registrado na Definição do Estudo.

Aparece em: Definição do Estudo.

**MIMIC-III — Base de dados MIMIC-III** (*Medical Information Mart for Intensive Care III*)

O MIMIC-III é uma grande base de dados de terapia intensiva vinda de um único centro. Reúne informações de pacientes internados nas unidades de cuidados críticos de um grande hospital. Entre os dados estão sinais vitais, medicamentos, exames de laboratório, observações e notas escritas pelos profissionais, balanço de líquidos, códigos de procedimentos e de diagnósticos, laudos de exames de imagem, tempo de internação e sobrevida (JOHNSON et al., 2016, p. 1). Os dados vêm do Beth Israel Deaconess Medical Center, em Boston, e chegam desidentificados, ou seja, sem informação que identifique o paciente. Pesquisadores de qualquer país podem acessá-los depois de assinar um acordo de uso. O nome antigo da base era *Multiparameter Intelligent Monitoring in Intensive Care* e foi trocado para refletir o uso mais amplo que ela passou a ter (JOHNSON et al., 2016, p. 2). A base cobre adultos, que nela são as pessoas com 16 anos ou mais, internados em unidades de cuidados críticos entre 2001 e 2012. São 38.597 pacientes adultos distintos e 49.785 internações hospitalares (JOHNSON et al., 2016, p. 3).

A desidentificação seguiu os padrões da HIPAA (*Health Insurance Portability and Accountability Act*), dos Estados Unidos. Para cada paciente, as datas foram empurradas para o futuro por um deslocamento aleatório, aplicado do mesmo jeito em todos os registros dele. Assim os intervalos entre eventos se mantêm, e as internações aparecem entre os anos 2100 e 2200. A hora do dia, o dia da semana e a estação do ano aproximada foram preservados. Pacientes com mais de 89 anos aparecem com idade acima de 300 anos. Nos textos livres, as informações identificáveis foram retiradas por um sistema baseado em dicionários e padrões de texto (JOHNSON et al., 2016, p. 6). A base é relacional, com 26 tabelas ligadas por identificadores: `SUBJECT_ID` identifica o paciente, `HADM_ID` a internação hospitalar e `ICUSTAY_ID` a passagem pela UTI (JOHNSON et al., 2016, p. 6). As notas clínicas ficam na tabela `NOTEEVENTS`, que reúne notas de enfermagem e notas médicas, laudos de eletrocardiograma e de radiologia e resumos de alta (JOHNSON et al., 2016, Tabela 4, p. 7).

Para ter acesso, o pesquisador precisa concluir um curso sobre proteção de participantes de pesquisa que inclua as exigências da HIPAA e assinar um acordo de uso que proíbe tentar identificar pacientes. A base é distribuída em arquivos CSV, junto com scripts para importá-la em sistemas como o PostgreSQL (JOHNSON et al., 2016, p. 7). O projeto foi aprovado pelos comitês de ética do hospital e do MIT. O consentimento individual dos pacientes foi dispensado porque o projeto não interferiu no cuidado e os dados foram desidentificados (JOHNSON et al., 2016, p. 5). A Tabela 4 do artigo descreve a versão 1.3. A versão registrada nas Referências é a 1.4 (JOHNSON; POLLARD; MARK, 2016).

Na Definição do Estudo, o MIMIC-III é a base de onde vem a população do estudo e onde fica o contexto do objetivo.

Aparece em: Definição do Estudo.

**Morbimortalidade** (*morbidity and mortality*)

Morbimortalidade é uma palavra composta que junta morbidade, o quanto uma população adoece, e mortalidade, o quanto ela morre. Morbidade é a proporção de pacientes com uma doença em certo período, para cada unidade de população. Mortalidade é o total de mortes registradas em uma população. É um conceito estatístico, que não deve ser confundido com a morte de uma pessoa.

Na literatura sobre sepse, as duas ideias costumam aparecer juntas para mostrar o peso da doença. GINESTRA et al. (2024, p. 1421), por exemplo, descrevem a sepse como uma síndrome ligada a alta morbidade, alta mortalidade e altos custos. A Definição do Estudo usa a palavra nesse sentido amplo, quando cita a redução da morbimortalidade como um benefício possível de um alerta precoce, benefício que este estudo não avalia.

Aparece em: Definição do Estudo.

**Mortalidade hospitalar** (*hospital mortality*, também *in-hospital mortality*)

Mortalidade hospitalar mede quantos pacientes internados morrem, por qualquer causa, antes da alta. Por ser uma estatística, ela descreve um grupo, não uma pessoa. Uma mortalidade hospitalar de 20% quer dizer que 20 de cada 100 pacientes daquele grupo morreram durante a internação (exemplo inventado).

**Definição conceitual.** Além de ser uma medida de gravidade muito usada, a mortalidade hospitalar foi o desfecho principal usado para validar os critérios clínicos do Sepsis-3. Os autores a escolheram porque é objetiva, fácil de medir em hospitais diferentes, dentro e fora dos Estados Unidos, e mais comum em quem tem sepse do que em quem tem uma infecção sem complicação (SEYMOUR et al., 2016, p. 5). É também por ela que o consenso mede o peso de um SOFA alto (SINGER et al., 2016, p. 8) e que GINESTRA et al. (2024, p. 1422) comparam HOS e COS.

**Definição operacional.** Óbito durante a internação incluída no estudo, identificado pela hora de óbito (`DEATHTIME`) da tabela `ADMISSIONS`. Aparece na tabela que descreve a coorte, no total e separada por classe (com e sem HOS). Não é desfecho do modelo (Dados).

Aparece em: Definição do Estudo.

**Notas clínicas** (*clinical notes*)

Notas clínicas são os textos livres que os profissionais escrevem no prontuário durante o cuidado, como notas de evolução, notas de enfermagem, a queixa principal do paciente e o resumo de alta (YAN et al., 2022, p. 560). São escritas por enfermeiros, médicos e outros profissionais para registrar sintomas, sinais, diagnósticos, planos de tratamento, cuidados prestados, resultados de exames e laudos (YAN et al., 2022, p. 561 e 563). Cada nota cobre um período ou uma atividade e descreve eventos, hipóteses, intervenções e observações sob a responsabilidade de quem escreve. A forma da nota depende da função dela: pode ser uma prescrição, um plano, um laudo, um relato do que aconteceu, um recado para o próximo plantão ou um registro exigido por motivo legal ou administrativo (YAN et al., 2022, p. 563).

Quem escreve e para quê muda o conteúdo. As notas da enfermagem são diferentes das médicas: enfermeiros registram mais sobre o que o paciente consegue fazer sozinho. A documentação também varia de um hospital para outro. Por isso, o tipo de nota, o autor e a finalidade influenciam a forma de ler o texto (YAN et al., 2022, p. 563). O tempo também importa. Costuma haver atraso entre o estado real do paciente, a observação do profissional e o registro no prontuário (YAN et al., 2022, p. 563). As notas de evolução, por exemplo, costumam ser escritas uma vez por plantão, com atraso de 4 a 8 horas, e o resumo de alta só existe na alta ou dias depois (YAN et al., 2022, Tabela 2, p. 564). Para um modelo de predição, esse atraso é decisivo: ele só pode usar as notas que já existiam no momento da previsão, como prevê a regra de disponibilidade das notas (Dados).

Aparece em: Definição do Estudo.

**PEP — Prontuário Eletrônico do Paciente** (*Electronic Health Record*, EHR)

O prontuário eletrônico do paciente é o registro digital do que acontece com o paciente no hospital. Ele junta dois tipos de informação que modelos de aprendizado de máquina podem usar: dados estruturados, como idade, sinais vitais e exames de laboratório, e dados não estruturados, como as notas clínicas em texto livre (YAN et al., 2022, p. 560). A internação começa na admissão e termina na alta, e nesse período o prontuário acumula a queixa principal, a história clínica e o exame físico, as notas de evolução, os laudos de exames de imagem e de eletrocardiograma, os resultados de laboratório, os códigos de diagnóstico e o resumo de alta (YAN et al., 2022, p. 563 e Tabela 2, p. 564). Cada tipo de documento tem autor, frequência e atraso de registro próprios. Os códigos de diagnóstico, por exemplo, costumam ser registrados dias ou meses depois da alta (YAN et al., 2022, Tabela 2, p. 564).

Para a sepse de início hospitalar, o prontuário é especialmente valioso. Quando a HOS começa, o paciente já está internado há pelo menos 48 horas (GINESTRA et al., 2024, p. 1425). Por isso existe muito dado registrado antes, durante e depois do episódio, o que torna o tema uma boa oportunidade de pesquisa (GINESTRA et al., 2024, p. 1423). O MIMIC-III, a base usada neste estudo, é um conjunto público de dados de UTI, criado a partir dos registros do Beth Israel Deaconess Medical Center, em Boston, com dados de 2001 a 2012 (YAN et al., 2022, p. 561).

Aparece em: Definição do Estudo.

**qSOFA — SOFA rápido** (*quick SOFA*)

O qSOFA é um escore de beira de leito proposto pelo Sepsis-3. Ele ajuda a reconhecer, entre pacientes com suspeita de infecção, os que provavelmente vão evoluir mal. São três critérios (SINGER et al., 2016, Box 4, p. 21):

- frequência respiratória de 22 por minuto ou mais;
- alteração do estado mental;
- pressão arterial sistólica de 100 mmHg ou menos.
  O paciente é positivo quando cumpre pelo menos dois deles (SINGER et al., 2016, p. 3).

O escore nasceu de um modelo de regressão logística. Fora da UTI, quaisquer dois de três critérios previram a morte no hospital tão bem quanto o SOFA completo, com AUROC de 0,81 (SINGER et al., 2016, p. 8). Os critérios desse modelo eram Escala de Coma de Glasgow de 13 ou menos, pressão sistólica de 100 mmHg ou menos e frequência respiratória de 22 por minuto ou mais. A AUROC está explicada na entrada de AUPRC, neste glossário.

Na versão final, o critério de consciência virou "alteração do estado mental", que é qualquer valor da Escala de Glasgow abaixo de 15. A troca foi feita porque a capacidade de previsão não mudou e a medida ficou mais simples (SINGER et al., 2016, p. 9). A grande vantagem do qSOFA é não precisar de exame de laboratório: dá para avaliá-lo rápido e repetidas vezes. O consenso sugere usá-lo como sinal para a equipe investigar disfunção orgânica, começar ou intensificar o tratamento e considerar a UTI (SINGER et al., 2016, p. 9).

Na UTI, o qSOFA funciona pior. Em pacientes de UTI com suspeita de infecção, o SOFA previu a morte no hospital melhor que o modelo de três critérios: AUROC de 0,74 contra 0,66. A explicação provável é que vasopressores, sedativos e ventilação mecânica alteram os sinais medidos (SINGER et al., 2016, p. 9).

O consenso também deixa três avisos:

- nem o qSOFA nem o SOFA são, sozinhos, uma definição de sepse;
- não cumprir os critérios não deve atrasar a investigação nem o tratamento de uma infecção (SINGER et al., 2016, p. 12);
- como a análise inicial foi retrospectiva e usou sobretudo dados dos Estados Unidos, o qSOFA ainda precisa de validação prospectiva em vários países (SINGER et al., 2016, p. 11–12).
  O critério de sepse continua sendo o aumento de 2 pontos no SOFA (ver as entradas de SOFA e de Sepsis-3, neste glossário).

**Definição operacional.** O qSOFA é calculado ao fim da janela de observação, com o pior valor de cada critério na janela e sem treinamento (Desenho do Estudo):

$$s_i = \mathbb{1}[FR_i \ge 22] + \mathbb{1}[GCS_i \le 13] + \mathbb{1}[PAS_i \le 100]$$

Os símbolos significam:

- $s_i$: escore do paciente $i$, de 0 a 3;
- $FR_i$: maior frequência respiratória da janela, por minuto;
- $GCS_i$: menor valor da Escala de Coma de Glasgow na janela;
- $PAS_i$: menor pressão arterial sistólica da janela, em mmHg;
- $\mathbb{1}[\cdot]$: função indicadora, que vale 1 quando a condição entre colchetes é verdadeira e 0 quando é falsa (Metodologia).
  O critério de consciência usa Glasgow de 13 ou menos, como no modelo original (Desenho do Estudo). Nas métricas que não dependem de limiar, como a AUPRC, entra o escore de 0 a 3. Nas que dependem, entra o corte de 2 ou mais. Um critério sem nenhuma medida na janela conta como não cumprido. Como o escore não é uma probabilidade, o qSOFA fica fora da avaliação de calibração (Metodologia).

Exemplo (números inventados): um paciente com frequência respiratória máxima de 24 por minuto, Glasgow mínimo de 15 e pressão sistólica mínima de 95 mmHg tem $s = 1 + 0 + 1 = 2$. Ele é qSOFA positivo.

Na Definição do Estudo, o qSOFA é uma referência descritiva. Ele fica fora do teste de hipótese e não é um dos tratamentos comparados (ver Planejamento do Estudo).

Aparece em: Definição do Estudo.

**Sepse** (*sepsis*)

Em linguagem leiga, sepse é uma condição com risco de vida que surge quando a resposta do corpo a uma infecção machuca os próprios tecidos e órgãos (SINGER et al., 2016, Box 3, p. 20). Diante de uma infecção, a reação inflamatória do organismo muitas vezes é só uma resposta adequada e útil (SINGER et al., 2016, p. 7). Na sepse, essa resposta fica desregulada e passa a prejudicar os órgãos. E não é só inflamação: ao mesmo tempo, entram em ação mecanismos que aumentam e que diminuem a inflamação, e são afetados sistemas que não fazem parte da imunidade, como o cardiovascular, o nervoso, o hormonal, o metabólico e a coagulação (SINGER et al., 2016, p. 5). A sepse é a principal causa de morte por infecção, principalmente quando não é reconhecida e tratada rápido (SINGER et al., 2016, Box 2, p. 19).

A sepse não é uma doença específica. É uma síndrome, um conjunto de sinais e alterações que ainda não é totalmente entendido e que não tem um exame capaz de dar o diagnóstico definitivo (SINGER et al., 2016, p. 5). Ela também não depende de onde está a infecção: o conceito exige apenas que uma infecção seja o gatilho (SINGER et al., 2016, p. 4). Sinais de infecções específicas, como a consolidação no pulmão, a dor ao urinar ou a peritonite, ajudam a apontar onde a infecção provavelmente está e qual micro-organismo a causa (SINGER et al., 2016, p. 7). O local de origem é só um dos fatores que fazem os pacientes com sepse serem tão diferentes entre si, ao lado da idade, das doenças que já tinham, de cirurgias e dos medicamentos (SINGER et al., 2016, p. 5).

**Definição conceitual.** Pelo Sepsis-3, sepse é uma disfunção orgânica com risco de vida causada por uma resposta desregulada do hospedeiro a uma infecção. "Hospedeiro" aqui é o organismo do paciente (SINGER et al., 2016, p. 2). A definição destaca três ideias: a resposta do organismo que perde o equilíbrio, uma letalidade muito maior que a de uma infecção simples e a necessidade de reconhecer a sepse com urgência. Mesmo uma disfunção orgânica pequena no momento em que se suspeita da infecção já está ligada a mortalidade hospitalar acima de 10% (SINGER et al., 2016, p. 7). Nenhuma medida clínica atual capta diretamente a "resposta desregulada" (SINGER et al., 2016, p. 7). Por isso, o critério clínico junta dois elementos que dá para medir: infecção suspeita ou confirmada e aumento agudo de 2 pontos ou mais no SOFA (SINGER et al., 2016, Tabela 2, p. 24). O termo "sepse grave", das versões anteriores, foi abandonado. Pela nova definição, toda sepse já envolve disfunção orgânica, e o adjetivo ficou sem função (SINGER et al., 2016, p. 7).

**Definição operacional.** Neste estudo, sepse é um episódio de infecção suspeita que cumpre o critério de disfunção orgânica, os dois como definidos neste glossário. É o Sepsis-3 colocado em prática com base em SEYMOUR et al. (2016), com duas adaptações. Primeiro, todos os episódios de infecção suspeita depois da janela de observação são avaliados, e não só o primeiro. Segundo, o aumento do SOFA é medido a partir do menor valor horário da janela de avaliação, e o valor posterior precisa ter sido registrado depois do fim da janela de observação (Desenho do Estudo).

Aparece em: Definição do Estudo.

**Sepsis-3 — Terceiro Consenso Internacional para Definições de Sepse e Choque Séptico** (*Third International Consensus Definitions for Sepsis and Septic Shock*)

O Sepsis-3 é o consenso internacional que define hoje sepse e choque séptico. Foi elaborado por um grupo de 19 especialistas em terapia intensiva, doenças infecciosas, cirurgia e pneumologia. O grupo foi reunido pela Society of Critical Care Medicine e pela European Society of Intensive Care Medicine e trabalhou entre janeiro de 2014 e janeiro de 2015 (SINGER et al., 2016, p. 3). As definições saíram de reuniões, de consultas em rodadas aos especialistas (processos Delphi), de análises de grandes bases de prontuário eletrônico e de votações. Depois foram enviadas a sociedades profissionais de vários países, e 31 delas as apoiaram oficialmente (SINGER et al., 2016, p. 2), entre elas a sociedade brasileira de terapia intensiva (SINGER et al., 2016, p. 14). O resultado foi publicado em 2016.

O nome segue a lógica das versões de software. O grupo recomendou chamar a nova definição de Sepsis-3 e as de 1991 e 2001 de Sepsis-1 e Sepsis-2, para deixar claro que haverá outras versões (SINGER et al., 2016, p. 14). A Sepsis-1 nasceu da ideia de que a sepse era a resposta inflamatória do corpo à infecção (SINGER et al., 2016, p. 3). Ela definia sepse como infecção com pelo menos 2 dos 4 critérios da síndrome da resposta inflamatória sistêmica (SIRS, na sigla em inglês) (SINGER et al., 2016, p. 5). Esses critérios usam temperatura, frequência cardíaca, frequência respiratória e contagem de glóbulos brancos (SINGER et al., 2016, Box 1, p. 18). A Sepsis-2 ampliou a lista de critérios de diagnóstico, mas não propôs alternativas (SINGER et al., 2016, p. 3). O Sepsis-3 rompeu com esse modelo. O grupo considerou os critérios de SIRS pouco úteis: eles refletem uma inflamação que pode ser só uma resposta adequada e aparecem em muitos pacientes internados que nunca vão ter infecção (SINGER et al., 2016, p. 5–6). O grupo também deixou de lado a ideia enganosa de que a sepse avança em etapas, de sepse para sepse grave e depois para choque (SINGER et al., 2016, p. 2).

O consenso separa definição de critério clínico. A definição descreve o que a doença é. Os critérios são características que dá para medir em cada paciente para reconhecê-la (SINGER et al., 2016, p. 4). O consenso também define choque séptico, um subgrupo da sepse em que os problemas de circulação e de metabolismo são graves o bastante para aumentar muito a mortalidade (SINGER et al., 2016, Box 3, p. 20). Este estudo não usa esse conceito.

Aparece em: Definição do Estudo.

**Sinais fisiológicos contínuos (formas de onda)** (*physiological waveforms*)

São sinais que os monitores de beira de leito registram o tempo todo, desenhando uma curva, em vez de anotar um número de tempos em tempos. No MIMIC-III, formas de onda como eletrocardiogramas, curvas de pressão arterial, fotopletismogramas e pneumogramas de impedância foram obtidas dos monitores, mas só para parte dos pacientes (JOHNSON et al., 2016, p. 5). Na visão geral da base, elas aparecem no monitoramento à beira do leito, ao lado de sinais vitais, tendências e alarmes (JOHNSON et al., 2016, Figura 1, p. 2). Como o estudo não usa essas curvas, este glossário não detalha o que cada uma mede.

Não confundir com os sinais vitais registrados nas tabelas da base. Esses são números conferidos pela enfermagem e anotados mais ou menos de hora em hora, como frequência cardíaca, pressão arterial e frequência respiratória (JOHNSON et al., 2016, Tabela 3, p. 4). A forma de onda é como um vídeo, e o sinal vital anotado de hora em hora é como uma foto tirada de tempos em tempos. Os sinais vitais entram neste estudo, porque fazem parte das variáveis do SOFA. As formas de onda não entram.

Depender de medidas muito frequentes também limita onde um modelo pode ser usado. YAN et al. (2022, p. 570) observam que muitos métodos de detecção de sepse dependem de medidas contínuas de sinais vitais na UTI, o que dificulta levá-los para as enfermarias.

Na Definição do Estudo, os sinais fisiológicos contínuos ficam fora do escopo, pelos motivos registrados na Definição do Estudo.

Aparece em: Definição do Estudo.

**Sistema de alerta precoce** (*early warning system*)

No contexto da sepse, um sistema de alerta precoce é um mecanismo que avisa a equipe do hospital quando um paciente pode estar desenvolvendo a doença, para que ela seja reconhecida e tratada mais cedo. Esses alertas podem se basear em critérios clínicos fixos ou em modelos preditivos, inclusive de aprendizado de máquina, e os dois tipos têm limitações conhecidas (GINESTRA et al., 2024, p. 1423). Os alertas baseados nos critérios de SIRS (a síndrome da resposta inflamatória sistêmica, descrita junto ao Sepsis-3 neste glossário) são pouco específicos. Quase metade dos pacientes de enfermaria cumpre pelo menos 2 critérios de SIRS em algum momento da internação, o que torna esse alerta pouco prático e fora de sintonia com as definições atuais de sepse. Os modelos preditivos mais avançados tiveram efeito variado nos desfechos dos pacientes. A ferramenta preditiva mais usada não identificou a sepse em dois terços dos casos e gerou muitos falsos positivos, que são alertas disparados em pacientes sem sepse (GINESTRA et al., 2024, p. 1423).

Por isso, entre as prioridades de pesquisa sobre HOS, GINESTRA et al. (2024, Tabela 1, p. 1424) propõem três coisas. A primeira é levar em conta, ao desenvolver esses modelos, a forma como a HOS se apresenta e os riscos próprios dela. A segunda é voltar o uso para os pacientes e os momentos com mais risco de atraso no cuidado. A terceira é definir metas de tratamento que digam com quanta antecedência o alerta precisa disparar para ser útil clinicamente. É nessa linha que a Definição do Estudo coloca o problema.

Aparece em: Definição do Estudo.

**SNOMED CT — Nomenclatura Sistematizada de Medicina – Termos Clínicos** (*Systematized Nomenclature of Medicine – Clinical Terms*; nome em tradução livre)

O SNOMED CT é um vocabulário controlado de termos clínicos, produzido pela International Health Terminology Standards Development Organisation, IHTSDO. Ele organiza conceitos clínicos e as relações entre eles, e permite combinar conceitos para descrever situações com mais detalhe (A04 – Interoperabilidade e padrões clínicos, 2026, p. 4). É uma terminologia de referência: representa conceitos clínicos com mais detalhe e com relações formais. Isso o diferencia das classificações, como a CID, que agrupam casos em categorias para estatística e administração (A04 – Interoperabilidade e padrões clínicos, 2026, p. 3). Junto com o LOINC, fornece conceitos e códigos para a interoperabilidade semântica (A04 – Interoperabilidade e padrões clínicos, 2026, p. 3). Como as outras terminologias grandes, tem manutenção e formatos próprios (Apostila 01 – Interoperabilidade em Saúde e HL7 e FHIR, 2026, p. 21).

Se a CID é um arquivo de gavetas feito para contar casos, o SNOMED CT é um dicionário em que cada conceito aponta para outros. Um conceito de infecção pulmonar, por exemplo, ficaria ligado ao conceito mais geral de infecção (exemplo ilustrativo, sem códigos reais).

Levar dados locais para o SNOMED CT tem custo. Traduzir de um vocabulário para outro não é mecânico e exige governança e análise de perda de significado (A04 – Interoperabilidade e padrões clínicos, 2026, p. 4). As variáveis do MIMIC-III são identificadas por códigos locais (ver a entrada de LOINC, neste glossário). Os autores da base relatam esforços em andamento para mapear seus conceitos para ontologias clínicas padronizadas (JOHNSON et al., 2016, p. 8).

Na Definição do Estudo, a padronização por SNOMED CT fica fora do escopo, pelo motivo registrado na Definição do Estudo.

Aparece em: Definição do Estudo.

**SOFA — Avaliação Sequencial de Falência Orgânica** (*Sequential Organ Failure Assessment*)

O SOFA é um escore que mede o grau de disfunção dos órgãos. Ele dá de 0 a 4 pontos para cada um de seis sistemas do organismo (respiratório, coagulação, fígado, cardiovascular, sistema nervoso central e rins) e soma tudo, então o total vai de 0 a 24 (SINGER et al., 2016, Tabela 1, p. 23; SEYMOUR et al., 2016, Tabela 1, p. 21). Os pontos de cada sistema vêm de achados clínicos, de exames de laboratório ou dos tratamentos em uso (SINGER et al., 2016, p. 6). O componente cardiovascular, por exemplo, considera a dose dos medicamentos que sustentam a pressão arterial. Quanto maior o escore, maior a chance de morte. O nome original era *Sepsis-related Organ Failure Assessment*, e ele se tornou o escore de disfunção orgânica mais usado (SINGER et al., 2016, p. 6).

O Sepsis-3 escolheu o SOFA porque ele é mais conhecido e mais simples que a alternativa avaliada, com desempenho parecido (SINGER et al., 2016, p. 8). Mesmo assim, o consenso aponta limitações. As variáveis e os pontos de corte foram escolhidos por consenso, e o cálculo completo exige exames de laboratório, como PaO₂, plaquetas, creatinina e bilirrubina (SINGER et al., 2016, p. 6). Esses exames podem demorar a mostrar a disfunção de um órgão, e o componente cardiovascular pode ser alterado pelas próprias intervenções médicas. Em compensação, o escore pode ser calculado depois, à mão ou por sistemas automáticos, a partir de medidas feitas na rotina (SINGER et al., 2016, p. 8), e é isso que o torna viável em estudos com dados de prontuário como este. O consenso deixa claro que o SOFA não serve para decidir o tratamento, e sim para descrever clinicamente o paciente com sepse. Também diz que as próximas versões das definições devem trazer um SOFA atualizado (SINGER et al., 2016, p. 8).

A composição do escore está na tabela abaixo, tradução da Tabela 1 de SINGER et al. (2016, p. 23), que os autores adaptaram de Vincent et al. O cálculo usado neste estudo está na definição operacional de disfunção orgânica, neste glossário.

| Sistema | Variável | 0 | 1 | 2 | 3 | 4 |
| --- | --- | --- | --- | --- | --- | --- |
| Respiratório | PaO₂/FiO₂, mmHg (kPa) | ≥400 (53,3) | <400 (53,3) | <300 (40) | <200 (26,7) com suporte respiratório | <100 (13,3) com suporte respiratório |
| Coagulação | Plaquetas, ×10³/µL | ≥150 | <150 | <100 | <50 | <20 |
| Hepático | Bilirrubina, mg/dL (µmol/L) | <1,2 (20) | 1,2–1,9 (20–32) | 2,0–5,9 (33–101) | 6,0–11,9 (102–204) | >12,0 (204) |
| Cardiovascular | PAM ou catecolaminaᵃ | PAM ≥70 mmHg | PAM <70 mmHg | Dopamina <5 ou dobutamina (qualquer dose) | Dopamina 5,1–15 ou epinefrina ≤0,1 ou norepinefrina ≤0,1 | Dopamina >15 ou epinefrina >0,1 ou norepinefrina >0,1 |
| Sistema nervoso central | Escala de Coma de Glasgowᵇ | 15 | 13–14 | 10–12 | 6–9 | <6 |
| Renal | Creatinina, mg/dL (µmol/L) | <1,2 (110) | 1,2–1,9 (110–170) | 2,0–3,4 (171–299) | 3,5–4,9 (300–440) | >5,0 (440) |
| Renal | Débito urinário, mL/dia | — | — | — | <500 | <200 |

Abreviaturas: PaO₂, pressão parcial de oxigênio; FiO₂, fração inspirada de oxigênio; PAM, pressão arterial média. ᵃ Doses de catecolaminas em µg/kg/min, dadas por pelo menos 1 hora. ᵇ A escala vai de 3 a 15; quanto maior, melhor a função neurológica.

Aparece em: Definição do Estudo.

**Tempo de internação** (*length of stay*)

Tempo de internação é o período em que o paciente fica internado num hospital ou em outra instituição de saúde. Pode ser medido para a internação inteira no hospital ou só para o tempo na UTI, e a literatura sobre sepse usa as duas medidas.

**Definição conceitual.** Além de mostrar quanto o paciente usa os recursos do hospital, o tempo de internação indica gravidade. No estudo que validou os critérios do Sepsis-3, ficar 3 dias ou mais na UTI entrou, junto com o óbito no hospital, no desfecho secundário, porque é mais comum na sepse do que numa infecção sem complicação (SEYMOUR et al., 2016, p. 5). Comparados aos pacientes com COS, os pacientes com HOS ficam internados mais que o dobro do tempo, tanto na UTI quanto no hospital (GINESTRA et al., 2024, p. 1421).

**Definição operacional.** **[A decidir]**. A tabela que descreve a coorte inclui o tempo de internação, no total e por classe, mas os documentos não dizem se é o tempo no hospital ou na UTI, nem como ele é calculado (Dados).

Aparece em: Definição do Estudo.

**UTI — Unidade de Terapia Intensiva** (*Intensive Care Unit*, ICU)

A unidade de terapia intensiva é a parte do hospital que oferece vigilância contínua e cuidado a pacientes com doença aguda. O Sepsis-3 recomenda que pacientes com sepse recebam, em geral, mais monitoramento e mais intervenções, o que pode incluir a internação em terapia intensiva (SINGER et al., 2016, p. 7). Os pacientes com HOS vão para a UTI com mais frequência que os com COS (GINESTRA et al., 2024, p. 1423).

Reconhecer a sepse dentro da UTI tem dificuldades próprias. Muitas vezes o paciente já tinha disfunção orgânica antes da infecção, já recebeu tratamento antes de chegar e está recebendo suporte para os órgãos, como ventilação mecânica e medicamentos para a pressão, e tudo isso interfere nos escores clínicos (SEYMOUR et al., 2016, p. 11). Este estudo se passa na UTI porque o MIMIC-III é uma base de dados de UTI (YAN et al., 2022, p. 561). A população são adultos cuja primeira passagem pela UTI acontece nas primeiras 48 horas da internação (Desenho do Estudo).

Aparece em: Definição do Estudo.

**Ventilação mecânica** (*mechanical ventilation*)

A ventilação mecânica é uma forma de respiração artificial em que um aparelho, o ventilador, empurra o ar para dentro e para fora dos pulmões. Ela é usada em pessoas que pararam de respirar ou que têm insuficiência respiratória, para aumentar a entrada de oxigênio e a saída de gás carbônico.

Na literatura do estudo, a ventilação mecânica aparece de duas formas. Primeiro, como sinal de gravidade: pacientes com HOS precisam dela cerca de duas vezes mais que os com COS (GINESTRA et al., 2024, p. 1421 e 1423). Segundo, como uma intervenção que atrapalha as medidas clínicas: o Sepsis-3 observa que vasopressores, sedativos e ventilação mecânica alteram os sinais dos pacientes de UTI e, com isso, pioram o desempenho de escores simples feitos à beira do leito (SINGER et al., 2016, p. 9). Neste estudo, a ventilação mecânica não é medida como variável própria. O que entra nas variáveis e no componente respiratório do SOFA é o uso de suporte respiratório (Desenho do Estudo).

Aparece em: Definição do Estudo.

## Conceitos Metodológicos

**AUPRC — Área sob a Curva de Precisão–Revocação** (*Area Under the Precision-Recall Curve*)

A AUPRC resume num único número o quanto o modelo acerta a classe positiva, que neste estudo é a dos pacientes que desenvolvem HOS. Ela parte de duas medidas tiradas da matriz de confusão. A matriz separa os resultados em verdadeiros positivos (VP), falsos positivos (FP), verdadeiros negativos (VN) e falsos negativos (FN) (A06 – Avaliação de desempenho e validação, 2026, p. 3):

$$P = \frac{VP}{VP + FP} \qquad\qquad R = \frac{VP}{VP + FN}$$

$P$ é a **precisão**, também chamada de valor preditivo positivo. Ela responde: dos pacientes que o modelo apontou como positivos, quantos de fato eram? $R$ é a **revocação** (*recall*), que é a própria sensibilidade. Ela responde: dos pacientes que tinham a condição, quantos o modelo encontrou? A A06 define as duas fórmulas na p. 3. A apostila chama a curva de "precisão–recall" (p. 3–4) e diz que a medida F1 combina precisão e sensibilidade (p. 4), o que mostra que revocação e sensibilidade são o mesmo conceito.

Uma analogia: alguém procura moedas numa praia com um detector de metais. A praia é enorme e tem poucas moedas, assim como a HOS é rara entre os pacientes. A revocação é a fração das moedas da praia que o detector achou. A precisão é a fração dos bipes que eram moedas, e não tampinhas.

Para montar a curva, lembre que o modelo devolve uma probabilidade para cada paciente. Para transformar probabilidade em "positivo" ou "negativo", escolhe-se um limiar. Cada limiar gera um par $(R, P)$, e a curva liga esses pares. A AUPRC é a área sob essa curva:

$$AUPRC = \int_0^1 P(R)\, dR$$

$P(R)$ é a precisão quando a revocação vale $R$. A área vai de 0 a 1, e quanto maior, melhor. A AUPRC também é chamada de *average precision* (precisão média) (MOOR et al., 2021, p. 13). Nenhuma área sob curva escolhe sozinha o limiar que será usado na prática clínica, porque os custos dos erros e a capacidade de agir sobre os alertas ficam fora da métrica (A06 – Avaliação de desempenho e validação, 2026, p. 4).

Exemplo (números inventados): de 1.000 pacientes, 50 têm HOS. Num certo limiar, o modelo dispara 40 alertas, e 20 deles estão certos. Então $P = 20/40 = 0{,}50$ e $R = 20/50 = 0{,}40$. Esse é um ponto da curva. Outro limiar gera outro ponto.

A AUPRC é preferida quando a classe positiva é rara. A AUROC (área sob a curva ROC, que cruza a sensibilidade com a taxa de falsos positivos) também é afetada pela prevalência e informa menos quando as classes estão muito desbalanceadas. Ela pode ficar alta mesmo quando o modelo falha justamente na classe minoritária. A AUPRC também depende da prevalência, mas permite comparar o modelo com um classificador que apenas "chuta" (MOOR et al., 2021, p. 13). Por isso, a mesma revisão recomenda relatar a AUPRC quando o evento é raro (MOOR et al., 2021, p. 15).

**Definição operacional.** Na Definição do Estudo, a AUPRC no conjunto de teste é a métrica que responde à QP1. A AUROC entra como métrica secundária (Desenho do Estudo). Há dois jeitos comuns de calcular a área: pela precisão média, que soma degraus, ou pela regra do trapézio, que liga os pontos por retas. Qual deles será usado, com qual biblioteca e função: **[A decidir]** (Planejamento do Estudo).

Aparece em: Definição do Estudo.

**Calibração** (*calibration*)

A calibração mede se as probabilidades dadas pelo modelo batem com o que de fato acontece. A discriminação ordena os pacientes por risco. A calibração compara as probabilidades previstas com as frequências observadas (A06 – Avaliação de desempenho e validação, 2026, p. 4). O TRIPOD+AI define calibração como a concordância entre os desfechos observados e os valores estimados pelo modelo. A diretriz recomenda avaliá-la de preferência por gráfico, com as probabilidades estimadas no eixo x, os desfechos observados no eixo y e uma curva de calibração suavizada, calculada sobre os dados de cada paciente (COLLINS et al., 2024, Box 1, p. 4).

Pense na previsão do tempo. Se, em todos os dias em que o serviço anunciou 30% de chance de chuva, choveu em cerca de 30% deles, a previsão é bem calibrada. Se choveu em 60% desses dias, ela subestima a chuva, mesmo que acerte quais dias são mais chuvosos que outros.

Em símbolos, um modelo é bem calibrado quando, entre os pacientes que recebem probabilidade prevista $p$, a fração com o desfecho é $p$ (formalização proposta neste glossário a partir dessa definição):

$$P(Y = 1 \mid \hat{p} = p) = p$$

Os símbolos significam:

- $Y$: desfecho, que vale 1 com HOS e 0 sem HOS;
- $\hat{p}$: probabilidade prevista pelo modelo;
- $p$: um valor qualquer entre 0 e 1.
  A curva de calibração mostra, para cada valor de $p$, a fração observada. A calibração perfeita é a diagonal do gráfico.

Exemplo (números inventados): de 200 pacientes que o modelo coloca com cerca de 10% de risco, 20 desenvolvem HOS, ou seja, 10%. Nessa faixa, o modelo está calibrado. Se fossem 40 pacientes (20%), o modelo estaria subestimando o risco.

Discriminação e calibração são propriedades diferentes. Um modelo pode ordenar bem os pacientes e mesmo assim errar o tamanho do risco. A calibração importa quando as probabilidades orientam decisões sobre cada paciente, e ela pode piorar quando mudam a população, a incidência ou a prática clínica (A06 – Avaliação de desempenho e validação, 2026, p. 4). O TRIPOD+AI pede que o relato especifique as medidas usadas, inclusive as de calibração, e descreva qualquer recalibração feita depois da avaliação (COLLINS et al., 2024, Tabela 2, itens 12e e 12f, p. 6). Se for usada alguma técnica para classes desbalanceadas, a diretriz pede também a descrição dos métodos de recalibração aplicados em seguida (COLLINS et al., 2024, Tabela 2, item 13, p. 7).

**Definição operacional.** A calibração é avaliada no conjunto de teste pelo Brier Score e por uma curva de calibração suavizada, calculada sobre as predições de cada paciente, nos três modelos de aprendizado de máquina. Ela não é usada para escolher modelos. O qSOFA fica de fora, porque não produz probabilidade (Desenho do Estudo; Metodologia). Método de suavização da curva: **[A decidir]** (Metodologia). O Brier Score entra neste glossário quando aparecer nos documentos novos.

Na Definição do Estudo, a calibração está entre as métricas secundárias da QP1. A preservação das probabilidades estimadas é um dos motivos para não rebalancear as classes.

Aparece em: Definição do Estudo.

**Conjunto de teste** (*test set*)

O conjunto de teste é a parte dos dados guardada para a avaliação final do modelo. Treino, validação e teste têm papéis diferentes, e o teste precisa ficar independente de todas as escolhas feitas durante o desenvolvimento (A05 – Formulação do problema e ciclo de vida do modelo, 2026, p. 4). O uso permitido é uma única avaliação final, depois que o modelo estiver congelado. O teste fica contaminado se orientar mudanças no modelo ou se for consultado várias vezes (Atividade 04 – Tarefa rótulo coorte tempo vazamento, 2026, p. 3). Antes de abrir o teste, é preciso congelar a coorte, o rótulo, as variáveis, o pré-processamento, a arquitetura e o limiar. Se o teste levou a alguma mudança, ele passou a funcionar como validação, e é preciso um novo teste independente (Atividade 04 – Tarefa rótulo coorte tempo vazamento, 2026, p. 7).

É como a prova final de uma disciplina, com questões que ninguém viu. Se o aluno conhecia a prova antes, a nota deixa de medir o que ele aprendeu.

Na Definição do Estudo, a QP1 é respondida pela AUPRC no conjunto de teste, e a leitura de casos da QP2 é feita com pacientes desse mesmo conjunto. Pelo desenho registrado, 20% dos dados são separados logo no início, com a mesma proporção de HOS da coorte completa, e ficam intocados até a avaliação final. Os hiperparâmetros e o limiar são escolhidos por validação cruzada nos outros 80% (Desenho do Estudo).

Não confundir com conjunto de validação, que serve para fazer escolhas durante o desenvolvimento. A palavra "validação" é ambígua na literatura. Por isso, o TRIPOD+AI chama de "dados de avaliação" os dados usados para medir o desempenho (COLLINS et al., 2024, Box 1, p. 4).

Aparece em: Definição do Estudo.

**Dados estruturados** (*structured data*)

Dados estruturados são dados com formato fixo, como idade, sinais vitais e exames de laboratório. Como cada valor tem lugar e tipo definidos, eles são mais fáceis de pré-processar do que o texto (YAN et al., 2022, p. 560). Dá para imaginar uma planilha em que cada coluna tem um significado e uma unidade: idade em anos, frequência cardíaca em batimentos por minuto, creatinina em mg/dL. Um registro típico seria a creatinina de um paciente anotada como 1,8 mg/dL num horário específico (valor inventado). Nesse formato, o computador consegue comparar, ordenar e resumir os valores diretamente, sem precisar interpretar nada.

Essa facilidade tem limites. Na revisão de YAN et al. (2022, p. 571), os estudos usaram quase sempre o mesmo tipo de dado estruturado: dados demográficos, sinais vitais e exames de laboratório. Os exames são os que mais demoram a ficar prontos, com atraso de cerca de 1 a 2 horas nos exames de sangue. Muitos métodos também dependem de sinais vitais medidos o tempo todo na UTI, e por isso é difícil levá-los para as enfermarias (YAN et al., 2022, p. 559).

Na Definição do Estudo, os dados estruturados são uma das duas fontes de informação do prontuário cujo valor o estudo compara. Um modelo usa só esses dados, e o outro usa esses dados mais as notas clínicas (Desenho do Estudo). Não confundir com dados não estruturados, descritos na próxima entrada.

Aparece em: Definição do Estudo.

**Dados não estruturados (texto livre)** (*unstructured data, free text*)

Dados não estruturados são dados sem formato fixo. No prontuário, são principalmente as notas clínicas em texto livre, como notas de evolução, notas de enfermagem, a queixa principal e o resumo de alta, cheias de abreviações e de erros de gramática e de grafia (YAN et al., 2022, p. 560). Se os dados estruturados são uma planilha, o texto livre é um caderno de anotações: a informação está lá, mas cada pessoa escreve de um jeito, e é preciso ler e interpretar antes de transformá-la em algo que o computador consiga comparar.

Para um modelo usar esse texto, é preciso processamento de linguagem natural (NLP, *natural language processing*), o conjunto de técnicas que tira características do texto e o transforma numa forma que o computador entende. Muitas vezes isso exige a ajuda de especialistas clínicos. É um processo complexo e demorado, e esse esforço afasta parte dos pesquisadores (YAN et al., 2022, p. 560). As formas de representar o texto vão das mais simples, como a bolsa de palavras (*bag-of-words*), até os *embeddings*, que guardam a informação de ordem das palavras que a bolsa de palavras perde (YAN et al., 2022, p. 565 e 567). O esforço compensa porque o texto clínico guarda informação valiosa: em várias doenças, usar esse texto melhorou o desempenho dos modelos (YAN et al., 2022, p. 560).

Um exemplo seria uma nota de enfermagem que conta, cheia de abreviações, como o paciente piorou durante o plantão (exemplo inventado). Na Definição do Estudo, a dificuldade de processar texto livre é uma das razões para a maioria dos modelos de predição de sepse usar só dados estruturados. Não confundir com notas clínicas: as notas são o tipo de dado não estruturado usado neste estudo, não um sinônimo do termo.

Aparece em: Definição do Estudo.

**Equidade e análise por subgrupo** (*fairness*, *subgroup analysis*)

No TRIPOD+AI, equidade é a propriedade de um modelo preditivo que não discrimina pessoas ou grupos por atributos como idade, raça ou etnia, sexo ou gênero e condição socioeconômica (COLLINS et al., 2024, Box 1, p. 4). A análise por subgrupo é o principal jeito de verificar isso: em vez de olhar só o desempenho médio, calcula-se o desempenho de cada grupo. Uma média global pode esconder diferenças entre grupos. Por isso, a auditoria por subgrupo compara cobertura dos dados, prevalência, calibração e taxas de erro. Se aparecer disparidade, é preciso investigar os dados, a formulação do problema, o modelo e o uso, porque o viés pode surgir em qualquer dessas fases (A06 – Avaliação de desempenho e validação, 2026, p. 4).

A média de uma turma pode ser 7 com metade dos alunos tirando 9 e a outra metade tirando 5. A média esconde quem está ficando para trás.

Exemplo, com números hipotéticos tirados da Atividade 04. A sensibilidade de cada grupo é calculada assim:

$$Se_g = \frac{VP_g}{VP_g + FN_g}$$

Os símbolos significam:

- $Se_g$: sensibilidade no grupo $g$;
- $VP_g$: verdadeiros positivos do grupo;
- $FN_g$: falsos negativos do grupo (a matriz de confusão está descrita na entrada de AUPRC, neste glossário).
  Os resultados são (Atividade 04 – Tarefa rótulo coorte tempo vazamento, 2026, p. 4):

| Grupo | Cálculo | Sensibilidade |
| --- | --- | --- |
| Urbano | $85/(85+15)$ | $0{,}85$ |
| Rural | $4/(4+6)$ | $0{,}40$ |
| Total | $89/(89+21)$ | $\approx 0{,}81$ |

O número global descreve mal o grupo rural, que concentra proporcionalmente os falsos negativos (Atividade 04 – Tarefa rótulo coorte tempo vazamento, 2026, p. 7). O exemplo também mostra o problema dos grupos pequenos. Com 10 casos no grupo rural, cada caso a mais ou a menos muda a sensibilidade em 10 pontos percentuais ($1/10$).

O TRIPOD+AI dá destaque à equidade. Pede que o relato descreva as abordagens usadas para tratá-la e a justificativa delas (COLLINS et al., 2024, Tabela 2, item 14, p. 7). Pede também que o desempenho seja relatado com intervalos de confiança, inclusive em subgrupos importantes, como os sociodemográficos (COLLINS et al., 2024, Tabela 2, item 23a, p. 7). Os autores lembram que ter grupos bem representados nos dados é necessário, mas não garante equidade. Se os dados de avaliação não representam a população-alvo, as estimativas por subgrupo podem sair enviesadas (COLLINS et al., 2024, p. 9). Na HOS, GINESTRA et al. (2024, p. 1427) relatam taxas maiores de infecção hospitalar e de HOS em pacientes de minorias raciais e étnicas e apontam que faltam estudos sobre os desfechos da HOS nesses grupos.

Na Definição do Estudo, o desempenho por subgrupo e as técnicas de equidade ficam fora do escopo, pelo motivo registrado na Definição do Estudo. A ausência é declarada no relato, como pede o TRIPOD+AI, e registrada como limitação (Metodologia).

Aparece em: Definição do Estudo.

**Estudo retrospectivo e observacional** (*retrospective observational study*)

Os dois adjetivos respondem a perguntas diferentes.

- **Retrospectivo** diz quando os dados foram produzidos em relação ao estudo. O estudo olha para trás e tira conclusões de dados sobre características e acontecimentos do passado das pessoas estudadas. O oposto é o estudo prospectivo, que seleciona um grupo e o acompanha dali para a frente.
- **Observacional** diz se o pesquisador interfere. Num estudo observacional, os participantes podem receber exames e tratamentos, mas não é o pesquisador quem decide quem recebe o quê. Num estudo de intervenção, é ele quem decide.
  O estudo retrospectivo é como um historiador que lê documentos já escritos. O prospectivo é como um repórter que acompanha os fatos enquanto acontecem. Ser observacional é só anotar, sem interferir na história.

O MIMIC-III é exemplo das duas coisas. Os dados foram coletados durante o cuidado de rotina do hospital, sem trabalho extra para a equipe e sem interferir no atendimento (JOHNSON et al., 2016, p. 3). O consentimento individual dos pacientes foi dispensado porque o projeto não afetou o cuidado e os dados foram desidentificados (JOHNSON et al., 2016, p. 5).

Um estudo de aprendizado de máquina pode ser observacional e, ao mesmo tempo, comparar tratamentos. Os pacientes não recebem nenhuma intervenção. O que se manipula é o modelo, isto é, o que entra nele (enquadramento proposto neste glossário, coerente com a classificação de objeto único descrita mais adiante).

Na Definição do Estudo, o estudo é retrospectivo e observacional, com dados históricos já coletados. A validação prospectiva, que exigiria um estudo prospectivo, fica fora do escopo (ver a entrada de validação, neste glossário).

Aparece em: Definição do Estudo.

**GQM — Objetivo–Questão–Métrica** (*Goal Question Metric*)

O GQM é uma abordagem de medição que vai de cima para baixo. Primeiro se definem os objetivos. Depois eles são ligados aos dados que os tornam mensuráveis. Por fim, os dados são interpretados em relação aos objetivos (BASILI; CALDIERA; ROMBACH, 1994, p. 2). A abordagem nasceu para avaliar defeitos em projetos de software da NASA (BASILI; CALDIERA; ROMBACH, 1994, p. 2) e tem três níveis (BASILI; CALDIERA; ROMBACH, 1994, p. 3):

1. **Conceitual (objetivo):** define o que se quer medir, com que propósito, com respeito a qual aspecto de qualidade, de qual ponto de vista e em qual ambiente.
2. **Operacional (questões):** um conjunto de perguntas que caracteriza como o objetivo será avaliado.
3. **Quantitativo (métricas):** os dados que respondem a cada pergunta em números. Podem ser objetivos, quando não dependem de quem mede, ou subjetivos, quando dependem.
   O resultado tem forma de árvore: o objetivo é a raiz, as questões são os galhos e as métricas são as folhas (BASILI; CALDIERA; ROMBACH, 1994, Figura 1, p. 3–4). Um objetivo informa o propósito, o objeto, o aspecto de qualidade e o ponto de vista. No exemplo dos autores, o objetivo é *melhorar* (propósito) a *pontualidade* (aspecto) do *processamento de pedidos de mudança* (objeto) do *ponto de vista do gerente de projeto* (BASILI; CALDIERA; ROMBACH, 1994, p. 4).

Na Definição do Estudo, o objetivo foi escrito pelo template de WOHLIN et al. (2012), com cinco partes: analisar, com o propósito de, com respeito a, do ponto de vista de e no contexto de. O livro não está disponível para consulta, então não foi possível conferir se o template deriva do GQM nem em que trecho isso aparece: **[A decidir]**. Lido pelo GQM, o estudo teria o objetivo na raiz, a QP1 e a QP2 como questões, e a AUPRC e a mudança de predição caso a caso como métricas (enquadramento proposto neste glossário).

Aparece em: Definição do Estudo.

**H0/H1 — Hipótese nula e hipótese alternativa** (*null hypothesis*, *alternative hypothesis*)

O teste de hipótese nula compara duas afirmações. A hipótese nula (H0) diz que não há relação ou diferença. A hipótese alternativa (H1) diz que há. Os dados levam a rejeitar H0 ou a não rejeitá-la. O valor-p mostra o quanto os dados são incompatíveis com H0, dentro do teste usado. Ele não é a probabilidade de H0 ser verdadeira (Apostila 02 – Regressão Logística, 2026, p. 13). Quando a evidência não basta para rejeitar H0, isso não prova que a diferença não existe (Apostila 02 – Regressão Logística, 2026, p. 12). Significância estatística também não mostra, sozinha, importância clínica (Apostila 02 – Regressão Logística, 2026, p. 13).

Pense num tribunal. O réu é presumido inocente (H0). Provas fortes levam à condenação, o que equivale a rejeitar H0. Sem provas suficientes, o réu é absolvido, mas a absolvição não prova que ele é inocente.

O nível de significância α é o limite de erro aceito para rejeitar H0. Na Apostila 02, por exemplo, ele é de 5% (p. 12). O teste foi feito para *testar* hipóteses definidas antes de ver os dados, não para *gerar* hipóteses a partir deles. Além disso, um valor-p só pode ser interpretado quando se sabe quantos testes foram feitos.

A H1 pode dizer apenas que existe diferença (bicaudal) ou indicar a direção dela (unicaudal). Fonte para essa distinção: **[A decidir]**.

Na Definição do Estudo, só a QP1 recebe hipótese formal. No desenho registrado:

$$H_0:\ \delta \le 0 \qquad\qquad H_1:\ \delta > 0, \qquad \delta = AUPRC_{combinado} - AUPRC_{estruturado}$$

$\delta$ é a diferença de AUPRC entre os dois modelos no conjunto de teste. O critério de decisão é rejeitar H0 se o limite inferior do IC 95% de $\delta$, calculado por *bootstrap* pareado, for positivo (Desenho do Estudo). Manter a hipótese unicaudal ou passar a bicaudal: **[A decidir]** (Planejamento do Estudo).

Aparece em: Definição do Estudo.

**Horizonte de predição** (*prediction horizon*)

O horizonte de predição é a antecedência com que o modelo prevê o evento, isto é, o tempo entre o momento da predição e o início do desfecho. Uma tarefa de ML em saúde precisa definir o instante da previsão e o horizonte (A05 – Formulação do problema e ciclo de vida do modelo, 2026, p. 3). Na revisão de MOOR et al. (2021, p. 7), a "avaliação por horizonte" funciona assim: o modelo recebe todos os dados coletados até *n* horas antes do início da sepse e prevê com horizonte de *n* horas. O objetivo é saber com quanta antecedência ele reconhece a sepse. Quanto mais perto do início, mais fácil a tarefa costuma ficar (MOOR et al., 2021, Figura 3, p. 10).

É como a previsão do tempo: prever a chuva de amanhã é mais fácil que prever a da semana que vem. Exemplo (inventado): se o modelo prevê às 10h uma sepse que começa às 14h, o horizonte é de 4 horas.

Na Definição do Estudo, o horizonte aparece na Expectativa. Ali consta o horizonte de 4 horas do resultado de AMROLLAHI et al. (2020), informado por YAN et al. (2022), e a observação de que o texto contribuiria mais com 48 a 12 horas de antecedência (YAN et al., 2022). Pelo desenho registrado, a predição acontece no fim da janela de observação, e a HOS pode começar em qualquer momento depois disso até a alta (Desenho do Estudo). A antecedência, portanto, não é fixa e varia de paciente para paciente (enquadramento proposto neste glossário). Se e como o horizonte será relatado: **[A decidir]** (Definição do Estudo e Planejamento do Estudo).

Não confundir com janela de observação. A janela é o período *de onde vêm* os dados. O horizonte é a *distância* entre o fim dos dados e o evento.

Aparece em: Definição do Estudo.

**IC 95% — Intervalo de Confiança de 95%** (*95% confidence interval*, 95% CI)

O intervalo de confiança de 95% é uma faixa de valores calculada junto com uma estimativa para mostrar o quanto ela é incerta. Toda estimativa feita com uma amostra poderia sair um pouco diferente com outra amostra. O intervalo expressa essa incerteza, sempre dentro das hipóteses do método usado para calculá-lo (Apostila 02 – Regressão Logística, 2026, p. 12). Na leitura mais comum, chamada frequentista, os "95%" descrevem o método: se o estudo fosse repetido muitas vezes, os intervalos feitos desse jeito conteriam o valor verdadeiro em cerca de 95% das vezes (Apostila 02 – Regressão Logística, 2026, p. 13). Pense num pescador cujo jeito de lançar a rede pega o peixe em cerca de 95 de cada 100 lançamentos. Num lançamento qualquer, ele não sabe se o peixe ficou dentro. Os 95% falam do jeito de lançar, não daquela rede.

Um jeito comum de calcular o intervalo é a aproximação de Wald, que a apostila apresenta para o coeficiente de uma regressão logística (Apostila 02 – Regressão Logística, 2026, p. 12). Parte-se da estimativa e do seu erro-padrão, e os limites são:

$$IC_{95\%} \approx \left[\, b - 1{,}96 \times EP \;;\; b + 1{,}96 \times EP \,\right]$$

Aqui, $b$ é a estimativa, o melhor valor que os dados fornecem; $EP$ é o erro-padrão, que mede o quanto essa estimativa é incerta; e 1,96 é o valor da aproximação normal com dois lados usada para 95% de confiança. Com os números inventados da apostila, $b = 0{,}6931$ e $EP = 0{,}250$, a margem é $1{,}96 \times 0{,}250 = 0{,}49$. Os limites ficam em $0{,}6931 - 0{,}49 = 0{,}2031$ e $0{,}6931 + 0{,}49 = 1{,}1831$ (Apostila 02 – Regressão Logística, 2026, p. 12). A fórmula mostra que, quanto maior o erro-padrão, mais largo o intervalo e menos precisa a estimativa.

Na Definição do Estudo, o intervalo acompanha os números de MARKWART et al. (2020, p. 1536): 48,7% dos casos de sepse com disfunção orgânica tratados em UTI tiveram origem no hospital, com IC 95% de 38,3% a 59,3%. A leitura correta é que a melhor estimativa é 48,7% e que os dados são compatíveis com valores entre cerca de 38% e 59%. Um erro comum é achar que 95% dos pacientes estão entre esses limites. O intervalo fala da estimativa, não das pessoas (Apostila 02 – Regressão Logística, 2026, p. 13). O estudo também vai calcular intervalos de confiança para os próprios resultados, mas por outro método, o bootstrap, que entra neste glossário quando aparecer nos documentos novos.

Aparece em: Definição do Estudo.

**Inspeção de casos** (*case review*)

A inspeção de casos é uma análise qualitativa: em vez de olhar só números agregados, lê-se cada caso selecionado para entender por que o modelo acertou ou errou. APOSTOLOVA e VELEZ (2017, p. 259), por exemplo, pediram a uma profissional qualificada que revisasse 200 notas de enfermagem sorteadas. A análise dos erros mostrou que a maioria dos falsos negativos eram notas com baixo grau de suspeita de infecção. WANG et al. (2022, p. 13) examinaram pacientes classificados corretamente pelo modelo multimodal e incorretamente pelo modelo só com texto. Concluíram que uma única fonte de dados não contém toda a informação útil.

É como um professor que, além de olhar a média da turma, lê as provas em que dois corretores deram notas muito diferentes, para entender a origem da diferença.

**Definição conceitual.** A QP2 mede a *mudança de predição caso a caso*, isto é, os pacientes em que acrescentar o texto altera o que o modelo prevê (Definição do Estudo).

**Definição operacional.** Cada modelo é avaliado no seu próprio limiar de operação. Há discordância quando um modelo classifica o paciente como positivo e o outro como negativo. Também entram os casos em que as probabilidades previstas pelos dois modelos diferem mais que um valor de **[A decidir]**. Os casos são lidos nas duas direções: quando o texto corrige o modelo estruturado e quando o texto introduz erro. Se houver casos demais, lê-se uma amostra aleatória de tamanho **[A decidir]**. A leitura segue seis categorias definidas antes, mais "outros", e é feita por uma única pessoa (Metodologia). Os resultados são exploratórios, sem conclusão de causa nem generalização (Definição do Estudo).

Aparece em: Definição do Estudo.

**Janela de observação** (*observation window*)

A janela de observação é o período de onde vêm os dados de entrada do modelo. Ela contém só informações disponíveis até o instante da previsão. A janela de desfecho começa depois dela. Separar as duas impede que informação do futuro atravesse a fronteira da decisão (A05 – Formulação do problema e ciclo de vida do modelo, 2026, p. 4). Na revisão de MOOR et al. (2021, p. 7), ela aparece como *feature window*, a janela de atributos.

É como dirigir olhando só o retrovisor até o ponto onde você está: a decisão usa apenas o que já passou.

**Definição operacional.** Vai de 0 a 48 horas a partir da admissão hospitalar (`ADMITTIME`). As variáveis estruturadas e as notas clínicas usadas pelos modelos vêm desse período (Desenho do Estudo). A janela também decide quem entra na coorte e quando um episódio conta como HOS: ver as definições operacionais de HOS e de disfunção orgânica, neste glossário.

Não confundir com a janela de avaliação do SOFA, que vai de 48 horas antes a 24 horas depois do início da infecção suspeita e está descrita na entrada de disfunção orgânica.

Aparece em: Definição do Estudo.

**Meta-análise** (*meta-analysis*)

A meta-análise é uma técnica estatística que junta os resultados de vários estudos sobre a mesma pergunta num único resumo em número. Ela só é possível quando cada estudo informa sua estimativa de efeito e a variância dessa estimativa, isto é, o quanto ela é incerta. É uma das formas de síntese estatística, termo mais amplo que inclui outros métodos, como combinar os resultados de testes estatísticos ou contar quantos estudos apontam para cada lado. É como juntar as pesquisas de vários institutos num número-resumo, levando em conta a precisão de cada uma, em vez de confiar numa pesquisa só.

A meta-análise costuma fazer parte de uma revisão sistemática, mas não é obrigatória. Uma revisão pode não fazer síntese estatística, por exemplo quando só um estudo cumpre os critérios. Também pode não fazer porque os estudos não se comparam: foi o caso de YAN et al. (2022, p. 559), que não fizeram meta-análise porque as medidas dos 9 estudos incluídos não podiam ser comparadas. Já MARKWART et al. (2020, p. 1536) fizeram meta-análises de efeitos aleatórios, um tipo de modelo de meta-análise, para chegar a estimativas combinadas (*pooled*) da proporção, da incidência e da mortalidade da sepse de origem hospitalar. Eles relataram heterogeneidade significativa, ou seja, os resultados variaram muito de um estudo para outro. Isso pede cautela ao usar o número combinado como estimativa para um contexto específico.

Na Definição do Estudo, a meta-análise aparece na apresentação de MARKWART et al. (2020). Não confundir com revisão sistemática: a revisão é o processo de buscar, escolher e avaliar os estudos; a meta-análise é uma das formas de juntar estatisticamente os resultados deles.

Aparece em: Definição do Estudo.

**Modelo combinado (dados estruturados + texto)** (*combined model*, também *multimodal model*)

Um modelo combinado usa ao mesmo tempo dados estruturados e texto clínico. Nos estudos revisados por YAN et al. (2022, Figura 4, p. 567), o texto primeiro é pré-processado e transformado em números que o computador entende. Depois os dados estruturados são acrescentados, e o conjunto é usado para treinar o modelo. AMROLLAHI et al. (2020, p. 199) fizeram isso com representações das notas geradas pelo ClinicalBERT, coladas aos dados estruturados e passadas a uma rede LSTM. QIN et al. (2021, p. 3) colaram as representações do texto às variáveis numéricas e usaram um XGBoost (QIN et al., 2021, p. 6). Na literatura, esses modelos também são chamados de multimodais (WANG et al., 2022, p. 2).

É como um médico que olha os exames *e* lê as anotações da enfermagem antes de decidir, em vez de olhar só um dos dois.

A junção mais simples é a concatenação, que coloca os dois vetores lado a lado:

$$\mathbf{x}_{comb} = [\,\mathbf{x}_{estr}\ ;\ \mathbf{x}_{texto}\,]$$

$\mathbf{x}_{estr}$ é o vetor das variáveis estruturadas de um paciente. $\mathbf{x}_{texto}$ é o vetor de números que representa as notas dele (o *embedding*, explicado na entrada de dados não estruturados). $[\,;\,]$ indica que os dois vetores são emendados um no outro.

Na Definição do Estudo, o modelo combinado é comparado com o modelo só com dados estruturados, com o mesmo algoritmo, nos mesmos pacientes. Pelo desenho registrado, os dois são XGBoost. O combinado recebe também *embeddings* do ClinicalBERT pré-treinado, sem ajuste fino, concatenados às variáveis estruturadas (Desenho do Estudo).

Aparece em: Definição do Estudo.

**Modelo preditivo** (*prediction model*)

Um modelo preditivo em saúde estima, para cada pessoa, o valor de um desfecho ou o risco de ele acontecer. A maioria estima a chance de uma condição já estar presente, e aí o modelo é chamado de diagnóstico, ou de um desfecho acontecer no futuro, e aí é chamado de prognóstico (COLLINS et al., 2024, p. 1). O uso principal é apoiar decisões clínicas. Há exemplos conhecidos em várias áreas, como o escore de Framingham para doença cardiovascular e o EuroSCORE II para cirurgia cardíaca, e milhares de modelos são publicados todo ano (COLLINS et al., 2024, p. 1). A previsão do tempo é uma boa comparação: com as medidas de hoje, ela estima a chance de chover amanhã. Não garante a chuva, mas dá uma probabilidade que ajuda a decidir se vale levar guarda-chuva.

Dois termos acompanham qualquer modelo preditivo. O desfecho é o evento que se quer prever; em aprendizado de máquina costuma ser chamado de alvo ou rótulo. Os preditores são as características medidas de cada pessoa que entram no modelo, como idade ou pressão arterial, também chamadas de *features*, entradas ou variáveis independentes (COLLINS et al., 2024, Box 1, p. 4). O modelo pode devolver uma probabilidade ou uma classificação. Quando devolve uma classificação, é preciso explicar como foi escolhido o limite que separa as classes (COLLINS et al., 2024, Tabela 2, item 15, p. 7). Nos modelos de aprendizado de máquina, ao contrário da regressão tradicional, o resultado muitas vezes não é uma equação simples, o que exige mais cuidado ao relatar o modelo (COLLINS et al., 2024, p. 2). A mesma diretriz afirma que não existe "modelo validado" e prefere falar em avaliação do modelo (COLLINS et al., 2024, p. 3). Ela pede ainda que os dados de avaliação representem a população em que o modelo será usado (COLLINS et al., 2024, Box 1, p. 4).

Na Definição do Estudo, o modelo preditivo é a ferramenta cujo uso pretendido é apoiar a decisão clínica, na forma de alerta de risco. Aqui, o modelo estima a chance de o paciente desenvolver HOS depois da janela de observação. Pela classificação de COLLINS et al. (2024), isso corresponde a um modelo prognóstico (enquadramento proposto neste glossário).

Aparece em: Definição do Estudo.

**Objeto único e a classificação sujeito × objeto × tratamento** (*single object study*)

Segundo o registro da Definição do Estudo, WOHLIN et al. (2012) classificam um experimento pelo número de sujeitos e pelo número de objetos. Os sujeitos aplicam o tratamento, e os objetos são aquilo sobre o que o tratamento é aplicado. A classificação foi pensada para experimentos com pessoas (Definição do Estudo).

Como este estudo é computacional e não tem participantes humanos, os papéis foram adaptados. A adaptação é deste estudo e não foi definida por WOHLIN et al. (2012) (Definição do Estudo):

- **Tratamentos:** os dois níveis da modalidade de entrada, isto é, o modelo só com dados estruturados e o modelo combinado.
- **Sujeito:** o pipeline único de treino e avaliação.
- **Objeto:** a coorte extraída do MIMIC-III, versão 1.4.
  Com um sujeito e um objeto, o estudo é classificado como de **objeto único**. Os pacientes não são sujeitos: são as unidades de análise da coorte. As outras classificações não se aplicam pelos motivos registrados na Definição do Estudo.

Pense num único cozinheiro (sujeito) que testa duas versões de uma receita (tratamentos), diferentes só num ingrediente, com o mesmo lote de ingredientes (objeto), a mesma panela e o mesmo fogão. Se o sabor mudar, a causa é o ingrediente. No estudo, o cozinheiro é o pipeline, o lote é a coorte e o ingrediente são as notas clínicas.

O que o livro diz exatamente ainda precisa ser conferido: como ele define sujeito, objeto e tratamento, os nomes e critérios das demais categorias da classificação, e a página. **[A decidir]** (conferir em WOHLIN et al., 2012). As consequências de ter um único objeto para a generalização são tratadas no Planejamento do Estudo.

Aparece em: Definição do Estudo.

**Pipeline** (*pipeline*)

Pipeline é uma sequência fixa de etapas de processamento de dados, encadeadas de modo que a saída de uma etapa vira a entrada da seguinte. Na biblioteca scikit-learn, o objeto `Pipeline` junta várias etapas num só objeto, porque o processamento costuma seguir uma ordem fixa, como seleção de variáveis, normalização e classificação. Todas as etapas, menos a última, precisam transformar os dados. Juntar as etapas assim traz três vantagens:

- **Conveniência:** basta chamar o treino e a predição uma vez para a sequência inteira.
- **Busca conjunta:** dá para buscar os hiperparâmetros de todas as etapas ao mesmo tempo.
- **Segurança:** na validação cruzada, o pipeline evita que estatísticas dos dados de teste vazem para o modelo treinado, porque as mesmas amostras treinam as transformações e o modelo.
  Pense numa linha de montagem. Cada estação faz sempre a mesma tarefa, na mesma ordem, e passa a peça adiante. Se duas linhas idênticas recebem peças diferentes, a diferença no produto final vem das peças, não da montagem.

Exemplo da vantagem de segurança: na padronização dos dados, a média e o desvio-padrão devem ser aprendidos só no treino e depois aplicados à validação e ao teste (Atividade 04 – Tarefa rótulo coorte tempo vazamento, 2026, p. 7). Na disciplina, a regressão logística da Tarefa 02 é montada assim, com a padronização e o modelo encadeados num pipeline ajustado só no treino (Tarefa 02 – Regressão Logística, 2026, p. 1; Apostila 02 – Regressão Logística, 2026, p. 14).

Num sentido mais amplo, "pipeline" também nomeia toda a cadeia de código de um estudo, da extração dos dados até a avaliação. Ao pedir a disponibilidade do código de análise, o TRIPOD+AI cita exatamente essas etapas: limpeza dos dados, construção de variáveis, construção do modelo e avaliação (COLLINS et al., 2024, Tabela 2, item 18f e nota, p. 7).

Na Definição do Estudo, a palavra tem esse sentido amplo. O pipeline único de treino e avaliação é o sujeito do estudo. Ele aplica os dois tratamentos com o mesmo código, o mesmo algoritmo, a mesma busca de hiperparâmetros e a mesma semente aleatória, que é o número que fixa os sorteios do computador para que se repitam iguais (ver a entrada de objeto único, neste glossário). As bibliotecas usadas em cada etapa são definidas no Planejamento do Estudo.

Aparece em: Definição do Estudo.

**Pseudorreplicação** (*pseudoreplication*)

Pseudorreplicação é o uso de estatística inferencial para testar efeitos de tratamento com dados de experimentos em que acontece uma de duas coisas:

- os tratamentos não foram replicados, embora as amostras possam ter sido;
- as réplicas não são estatisticamente independentes.
  Réplica é cada unidade que recebe o mesmo tratamento. Independente quer dizer que uma unidade não carrega informação sobre a outra. Na linguagem da análise de variância, a pseudorreplicação é testar o efeito do tratamento com um termo de erro inadequado à hipótese. Na prática, o teste conta como informação nova o que é repetição da mesma fonte, o que tende a fazer a incerteza parecer menor do que é (enquadramento proposto neste glossário). O conceito vem de experimentos de campo em ecologia. A aplicação a dados de prontuário é feita aqui a partir do Desenho do Estudo.

É como perguntar a mesma coisa dez vezes à mesma pessoa e apresentar o resultado como uma pesquisa com dez pessoas.

Em dados de prontuário, o caso típico é o paciente com várias internações. As internações de uma mesma pessoa compartilham características dela, como idade e doenças crônicas, e por isso não são independentes. Tratá-las como observações independentes é pseudorreplicação (Desenho do Estudo).

Um problema vizinho, mas diferente, é o vazamento entre pacientes. Se internações da mesma pessoa caem uma no treino e outra no teste, o modelo pode memorizar características individuais. Por isso, o mesmo paciente não deve aparecer nos dois lados da divisão dos dados (A05 – Formulação do problema e ciclo de vida do modelo, 2026, p. 4; Atividade 04 – Tarefa rótulo coorte tempo vazamento, 2026, p. 7). A pseudorreplicação compromete o teste estatístico. O vazamento compromete a avaliação do modelo (enquadramento proposto neste glossário).

Na Definição do Estudo, as internações posteriores do mesmo paciente ficam fora da coorte para evitar pseudorreplicação. Com uma internação por paciente, a coorte tem uma linha por paciente, o que também impede que o mesmo paciente apareça no treino e no teste (Desenho do Estudo).

Aparece em: Definição do Estudo.

**Questão de pesquisa confirmatória e exploratória** (*confirmatory and exploratory research question*)

Uma questão é **confirmatória** quando testa uma expectativa definida antes de ver os dados. É **exploratória** quando usa os dados para descobrir padrões e gerar hipóteses. Essas duas formas de pesquisa também são chamadas de predição e pós-dição. Na predição, os dados são obtidos para testar uma ideia sobre o que vai acontecer. Na pós-dição, os dados já são conhecidos e servem para explicar por que algo aconteceu. Criar uma hipótese olhando os dados e depois avaliá-la com os mesmos dados é raciocínio circular. Isso gera confiança exagerada nos resultados. A exploração é valiosa para descobrir possibilidades, mas precisa ser apresentada como exploração. Separar uma parte dos dados e lacrá-la até o fim da exploração transforma ideias tiradas da primeira parte em predições testáveis na parte lacrada. É o papel do conjunto de teste neste estudo.

Uma analogia: o atirador que dispara contra a parede e depois pinta o alvo em volta do furo. A pintura não prova pontaria. Para provar, ele precisa pintar o alvo *antes* de atirar.

Na Definição do Estudo, a QP1 é confirmatória: tem expectativa definida antes dos dados e hipótese formal. A QP2 é exploratória: não tem expectativa prévia nem hipótese, e os resultados são apresentados como exploratórios.

Aparece em: Definição do Estudo.

**Revisão sistemática** (*systematic review*)

Uma revisão sistemática é uma revisão da literatura que segue métodos explícitos e organizados para reunir e sintetizar os estudos que respondem a uma pergunta bem definida. O que a diferencia de uma revisão comum é o método. A pergunta, os critérios para incluir ou excluir estudos, as bases pesquisadas e a estratégia de busca são definidos e relatados, e a seleção fica registrada, de preferência num fluxograma que mostra quantos estudos foram encontrados, excluídos e incluídos. Esse relato completo permite que outra pessoa repita a revisão. É como escolher um restaurante lendo todas as avaliações publicadas, com critérios decididos antes, e anotando por que cada uma foi aceita ou descartada, em vez de perguntar a alguns amigos.

Revisões sistemáticas têm vários papéis: resumem o que se sabe numa área, ajudam a apontar o que falta pesquisar, respondem perguntas que estudos isolados não conseguem responder e mostram problemas nos estudos originais. Existem diretrizes próprias para relatá-las, como a PRISMA, que YAN et al. (2022, p. 560) seguiram na revisão sobre uso de texto clínico com aprendizado de máquina para sepse. MARKWART et al. (2020, p. 1536) juntaram revisão sistemática e meta-análise para estimar o peso da sepse de origem hospitalar.

Na Definição do Estudo, esses dois trabalhos são citados como revisões sistemáticas. Não confundir com meta-análise, descrita na entrada anterior: a revisão é o processo de buscar e escolher os estudos; a meta-análise é uma das formas de juntar os resultados deles.

Aparece em: Definição do Estudo.

**Validação interna, externa, temporal e prospectiva** (*internal, external, temporal and prospective validation*)

As quatro respondem à mesma pergunta, se o desempenho medido se sustenta, mas usam dados cada vez mais distantes daqueles que construíram o modelo.

- **Interna:** avalia o modelo na mesma população em que ele foi desenvolvido, por exemplo com divisão em treino e teste, validação cruzada ou bootstrap (COLLINS et al., 2024, Box 1, p. 4). Serve para estimar o otimismo, isto é, o quanto o desempenho medido durante o desenvolvimento exagera o real (A06 – Avaliação de desempenho e validação, 2026, p. 4).
- **Temporal:** testa se o modelo funciona em outro período (A06 – Avaliação de desempenho e validação, 2026, p. 4). Um exemplo hipotético é treinar com altas de 2019 a 2022, validar em 2023 e testar em 2024, sempre com todas as internações da mesma pessoa no mesmo conjunto (Atividade 04 – Tarefa rótulo coorte tempo vazamento, 2026, p. 7).
- **Externa:** testa se o modelo funciona em outra instituição (A06 – Avaliação de desempenho e validação, 2026, p. 4). Divisões por tempo e por instituição revelam mudanças que uma divisão aleatória dentro de uma mesma base pode esconder (A05 – Formulação do problema e ciclo de vida do modelo, 2026, p. 4).
- **Prospectiva:** avalia o modelo num estudo prospectivo, com pacientes acompanhados a partir do momento em que entram no estudo (ver a entrada de estudo retrospectivo e observacional, neste glossário). Uma avaliação clínica completa vai além do desempenho estatístico e chega à integração, ao uso e ao impacto (A06 – Avaliação de desempenho e validação, 2026, p. 4). O Sepsis-3 seguiu essa lógica: os critérios foram testados primeiro em grandes bases de dados, e o consenso recomendou validá-los, ao final, de forma prospectiva (SINGER et al., 2016, p. 4 e 12).
  Pense num aluno que tira boa nota nas provas da própria turma (interna). Ele ainda precisa mostrar que sabe a matéria nas provas do ano seguinte (temporal), numa escola diferente (externa) e, por fim, no trabalho de verdade (prospectiva).

A palavra "validação" causa confusão. Em aprendizado de máquina, "dados de validação" podem ser os usados para ajustar o modelo ou os usados para medir o desempenho. Por isso, o TRIPOD+AI prefere falar em avaliação e afirma que não existe "modelo validado" (COLLINS et al., 2024, p. 3 e Box 1, p. 4). Nesta entrada, "validação" quer dizer sempre avaliação do desempenho. O conjunto de validação, usado para escolhas durante o desenvolvimento, é outra coisa (ver a entrada de conjunto de teste, neste glossário).

Na Definição do Estudo, a validação é só interna, toda dentro do MIMIC-III: validação cruzada em 5 dobras no conjunto de treino e um conjunto de teste separado desde o início (Desenho do Estudo). A validação externa, a temporal e a prospectiva ficam fora do escopo, pelos motivos registrados na Definição do Estudo.

Aparece em: Definição do Estudo.

**Valor incremental** (*incremental value*, também *added value*)

**Definição conceitual.** Valor incremental é o quanto uma nova fonte de informação melhora o desempenho de um modelo que já usa outras fontes. Neste estudo, a nova fonte são as notas clínicas, e a fonte que já existia são os dados estruturados (Definição do Estudo). AMROLLAHI et al. (2020, p. 197) mediram esse ganho comparando um modelo que incorporava as notas com um modelo de referência só com dados estruturados.

É como uma segunda opinião médica: ela só vale a pena se disser algo que a primeira ainda não disse.

**Definição operacional.** É a diferença de AUPRC entre os modelos no conjunto de teste:

$$\delta = AUPRC_{combinado} - AUPRC_{estruturado}$$

O IC 95% de $\delta$ é calculado por *bootstrap* pareado com 2.000 reamostragens. Os dois modelos usam o mesmo algoritmo, a mesma regra para valores faltantes e a mesma busca de hiperparâmetros, para que $\delta$ isole o efeito do texto (Desenho do Estudo). Exemplo (números inventados): se o modelo combinado tem AUPRC de 0,30 e o estruturado de 0,25, então $\delta = 0{,}30 - 0{,}25 = 0{,}05$.

Não confundir com relevância clínica: uma diferença estatisticamente significativa não mostra, sozinha, que a diferença importa na prática (Apostila 02 – Regressão Logística, 2026, p. 13).

Aparece em: Definição do Estudo.