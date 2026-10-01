# Apêndice C — Glossário e Fundamentação

**Versão**: 0.1 | **Data**: 01/10/2026 | **Fase**: Todas (documento de apoio)

**Como usar este documento:**

- É o guia dos conceitos do estudo: quase uma fundamentação teórica, só que mais simples. É escrito aos poucos, conforme os termos aparecem nos outros documentos ou nas leituras; não precisa estar completo desde o início.
- **Conceitos do Domínio** = o que se estuda: a condição clínica, os termos clínicos e as siglas, e os construtos medidos. **Conceitos Metodológicos** = como se estuda: ML, estatística, processamento de texto e métodos de pesquisa. Na dúvida, pergunte: "isso existiria mesmo sem ML?" Se sim, é do domínio.
- Entradas em ordem alfabética dentro de cada seção. Siglas aparecem por extenso no título da entrada (ex.: "UTI — Unidade de Terapia Intensiva").
- Escreva **com suas palavras**. Trecho literal só entre aspas, com página (ou seção, quando o artigo não tiver páginas). Toda definição vem com fonte (AUTOR, ANO); definições clínicas vêm de fonte primária (consenso, diretriz, artigo de definição), nunca de memória.
- A versão começa em **0.1** quando o documento ganha o primeiro conteúdo e sobe 0.1 a cada revisão fechada (fim de um chat de revisão, não a cada pequena edição). O documento vira **1.0** na entrega final (04/12/2026). A Data é a da última edição do documento.
- Para indicar onde o termo aparece, cite o documento inteiro, nunca uma seção pelo nome.

## Conceitos do Domínio

**Apoio à decisão clínica** (*clinical decision support*)

Apoio à decisão clínica é o uso de sistemas no computador que juntam informações clínicas e dados do próprio paciente para ajudar a decidir sobre o cuidado (NATIONAL LIBRARY OF MEDICINE, 2026, descritor D020000). Como o nome diz, o sistema apoia a decisão: organiza a informação e sinaliza o que merece atenção, mas quem decide é o profissional. Os modelos de predição em saúde são o exemplo mais típico, porque esse é o uso principal deles. Eles ajudam a decidir se o paciente deve fazer mais exames, se precisa ser acompanhado mais de perto por risco de piora ou se um tratamento deve começar (COLLINS et al., 2024, p. 1).

No caso da sepse de início hospitalar, GINESTRA et al. (2024, p. 1423) defendem pesquisar quais pacientes e quais formas de apresentação geram mais dúvida no diagnóstico e poderiam se beneficiar de ferramentas de apoio ao diagnóstico e à decisão. Para eles, só dá para confiar clinicamente nessas ferramentas se antes se entender como a HOS se manifesta. É nesse papel que a Definição do Estudo coloca o uso pretendido do modelo: um alerta de risco que apoia o julgamento clínico, sem substituí-lo.

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

**Infecção suspeita** (*suspected infection*)

Infecção suspeita é quando a equipe desconfia de uma infecção e passa a agir como se ela existisse: colhe material, como sangue ou urina, para exame de cultura e começa um antibiótico. Tudo isso acontece antes de haver confirmação. Resultados de laboratório levam dias para ficar disponíveis no prontuário (YAN et al., 2022, Tabela 2, p. 564), e tratar logo pode melhorar o desfecho dos pacientes com sepse (SINGER et al., 2016, p. 4).

**Definição conceitual.** O Sepsis-3 trata a infecção como o gatilho da sepse, mas não se propôs a redefinir o que é infecção (SINGER et al., 2016, p. 4). O consenso reconhece que a infecção quase nunca está confirmada por exame quando o tratamento começa. Mesmo depois de concluídos os exames, só 30% a 40% dos casos de sepse têm cultura positiva. Por isso, os estudos epidemiológicos precisam de indicadores indiretos, como o início de antibiótico ou a probabilidade de infecção estimada pela equipe (SINGER et al., 2016, p. 13). Para pesquisas com dados de prontuário, o consenso sugere identificar a infecção suspeita pela combinação de antibiótico, oral ou parenteral (injetável), com cultura de fluidos do corpo, como sangue, urina, líquor e líquido do abdome, dentro de um prazo definido (SINGER et al., 2016, Tabela 2, nota b, p. 24). O estudo que validou os critérios do Sepsis-3 usou exatamente essa combinação, contando só antibióticos não profiláticos, isto é, não usados apenas para prevenir (SEYMOUR et al., 2016, Tabela 2, p. 22). Ele também fixou a ordem e o prazo entre os dois eventos. Se o antibiótico veio primeiro, a cultura precisa ter sido colhida em até 24 horas. Se a cultura veio primeiro, o antibiótico precisa ter sido prescrito em até 72 horas. O início da infecção é o horário do primeiro dos dois (SEYMOUR et al., 2016, p. 4). Os autores avisam que só estudaram pacientes em que já havia suspeita de infecção. O estudo não trata de como diagnosticar infecção quando a disfunção orgânica é o primeiro sinal (SEYMOUR et al., 2016, p. 11).

**Definição operacional.** O estudo usa a mesma combinação e os mesmos prazos: antibiótico registrado na tabela `PRESCRIPTIONS` e cultura de fluido corporal registrada na tabela `MICROBIOLOGYEVENTS`. A cultura conta pela coleta, seja qual for o resultado. O início da infecção é o primeiro dos dois eventos (Desenho do Estudo; Dados). A tabela `PRESCRIPTIONS` só registra a data de início do antibiótico, sem hora, e parte das culturas também só tem data. Nesses casos, usa-se 00h00 da data registrada. Essa convenção é conservadora para a HOS porque adianta o episódio: um antibiótico ou uma cultura só conta como posterior à janela se a data for depois do dia em que a janela termina (Desenho do Estudo). Três mapeamentos continuam abertos e serão fixados antes de olhar as contagens do desfecho: quais medicamentos contam como antibiótico, quais vias contam como oral ou parenteral e quais tipos de amostra contam como fluido corporal: **[A decidir]** (Dados).

Aparece em: Definição do Estudo.

**Morbimortalidade** (*morbidity and mortality*)

Morbimortalidade é uma palavra composta que junta morbidade, o quanto uma população adoece, e mortalidade, o quanto ela morre. O vocabulário MeSH define as duas partes separadamente. Morbidade é a proporção de pacientes com uma doença em certo período, para cada unidade de população (NATIONAL LIBRARY OF MEDICINE, 2026, descritor D009017). Mortalidade é o total de mortes registradas em uma população. O próprio MeSH avisa que é um conceito estatístico, que não deve ser confundido com a morte de uma pessoa (NATIONAL LIBRARY OF MEDICINE, 2026, descritor D009026).

Na literatura sobre sepse, as duas ideias costumam aparecer juntas para mostrar o peso da doença. GINESTRA et al. (2024, p. 1421), por exemplo, descrevem a sepse como uma síndrome ligada a alta morbidade, alta mortalidade e altos custos. A Definição do Estudo usa a palavra nesse sentido amplo, quando cita a redução da morbimortalidade como um benefício possível de um alerta precoce, benefício que este estudo não avalia.

Aparece em: Definição do Estudo.

**Mortalidade hospitalar** (*hospital mortality*, também *in-hospital mortality*)

Mortalidade hospitalar mede quantos pacientes internados morrem, por qualquer causa, antes da alta. No MeSH, é uma estatística vital que mede ou registra a taxa de morte por qualquer causa entre pessoas internadas (NATIONAL LIBRARY OF MEDICINE, 2026, descritor D017052). Por ser uma estatística, ela descreve um grupo, não uma pessoa. Uma mortalidade hospitalar de 20% quer dizer que 20 de cada 100 pacientes daquele grupo morreram durante a internação (exemplo inventado).

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

**Sistema de alerta precoce** (*early warning system*)

No contexto da sepse, um sistema de alerta precoce é um mecanismo que avisa a equipe do hospital quando um paciente pode estar desenvolvendo a doença, para que ela seja reconhecida e tratada mais cedo. Esses alertas podem se basear em critérios clínicos fixos ou em modelos preditivos, inclusive de aprendizado de máquina, e os dois tipos têm limitações conhecidas (GINESTRA et al., 2024, p. 1423). Os alertas baseados nos critérios de SIRS (a síndrome da resposta inflamatória sistêmica, descrita junto ao Sepsis-3 neste glossário) são pouco específicos. Quase metade dos pacientes de enfermaria cumpre pelo menos 2 critérios de SIRS em algum momento da internação, o que torna esse alerta pouco prático e fora de sintonia com as definições atuais de sepse. Os modelos preditivos mais avançados tiveram efeito variado nos desfechos dos pacientes. A ferramenta preditiva mais usada não identificou a sepse em dois terços dos casos e gerou muitos falsos positivos, que são alertas disparados em pacientes sem sepse (GINESTRA et al., 2024, p. 1423).

Por isso, entre as prioridades de pesquisa sobre HOS, GINESTRA et al. (2024, Tabela 1, p. 1424) propõem três coisas. A primeira é levar em conta, ao desenvolver esses modelos, a forma como a HOS se apresenta e os riscos próprios dela. A segunda é voltar o uso para os pacientes e os momentos com mais risco de atraso no cuidado. A terceira é definir metas de tratamento que digam com quanta antecedência o alerta precisa disparar para ser útil clinicamente. É nessa linha que a Definição do Estudo coloca o problema.

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

Tempo de internação é o período em que o paciente fica internado num hospital ou em outra instituição de saúde (NATIONAL LIBRARY OF MEDICINE, 2026, descritor D007902). Pode ser medido para a internação inteira no hospital ou só para o tempo na UTI, e a literatura sobre sepse usa as duas medidas.

**Definição conceitual.** Além de mostrar quanto o paciente usa os recursos do hospital, o tempo de internação indica gravidade. No estudo que validou os critérios do Sepsis-3, ficar 3 dias ou mais na UTI entrou, junto com o óbito no hospital, no desfecho secundário, porque é mais comum na sepse do que numa infecção sem complicação (SEYMOUR et al., 2016, p. 5). Comparados aos pacientes com COS, os pacientes com HOS ficam internados mais que o dobro do tempo, tanto na UTI quanto no hospital (GINESTRA et al., 2024, p. 1421).

**Definição operacional.** **[A decidir]**. A tabela que descreve a coorte inclui o tempo de internação, no total e por classe, mas os documentos não dizem se é o tempo no hospital ou na UTI, nem como ele é calculado (Dados).

Aparece em: Definição do Estudo.

**UTI — Unidade de Terapia Intensiva** (*Intensive Care Unit*, ICU)

A unidade de terapia intensiva é a parte do hospital que oferece vigilância contínua e cuidado a pacientes com doença aguda (NATIONAL LIBRARY OF MEDICINE, 2026, descritor D007362). O Sepsis-3 recomenda que pacientes com sepse recebam, em geral, mais monitoramento e mais intervenções, o que pode incluir a internação em terapia intensiva (SINGER et al., 2016, p. 7). Os pacientes com HOS vão para a UTI com mais frequência que os com COS (GINESTRA et al., 2024, p. 1423).

Reconhecer a sepse dentro da UTI tem dificuldades próprias. Muitas vezes o paciente já tinha disfunção orgânica antes da infecção, já recebeu tratamento antes de chegar e está recebendo suporte para os órgãos, como ventilação mecânica e medicamentos para a pressão, e tudo isso interfere nos escores clínicos (SEYMOUR et al., 2016, p. 11). Este estudo se passa na UTI porque o MIMIC-III é uma base de dados de UTI (YAN et al., 2022, p. 561). A população são adultos cuja primeira passagem pela UTI acontece nas primeiras 48 horas da internação (Desenho do Estudo).

Aparece em: Definição do Estudo.

**Ventilação mecânica** (*mechanical ventilation*)

A ventilação mecânica é uma forma de respiração artificial. O descritor MeSH correspondente, *Respiration, Artificial*, reúne os métodos, mecânicos ou não, que empurram o ar para dentro e para fora dos pulmões. Eles são usados em pessoas que pararam de respirar ou que têm insuficiência respiratória, para aumentar a entrada de oxigênio e a saída de gás carbônico (NATIONAL LIBRARY OF MEDICINE, 2026, descritor D012121). A definição própria de ventilação mecânica, e não da respiração artificial em geral, ainda está **[A decidir]**.

Na literatura do estudo, a ventilação mecânica aparece de duas formas. Primeiro, como sinal de gravidade: pacientes com HOS precisam dela cerca de duas vezes mais que os com COS (GINESTRA et al., 2024, p. 1421 e 1423). Segundo, como uma intervenção que atrapalha as medidas clínicas: o Sepsis-3 observa que vasopressores, sedativos e ventilação mecânica alteram os sinais dos pacientes de UTI e, com isso, pioram o desempenho de escores simples feitos à beira do leito (SINGER et al., 2016, p. 9). Neste estudo, a ventilação mecânica não é medida como variável própria. O que entra nas variáveis e no componente respiratório do SOFA é o uso de suporte respiratório (Desenho do Estudo).

Aparece em: Definição do Estudo.

## Conceitos Metodológicos

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

**IC 95% — Intervalo de Confiança de 95%** (*95% confidence interval*, 95% CI)

O intervalo de confiança de 95% é uma faixa de valores calculada junto com uma estimativa para mostrar o quanto ela é incerta. Toda estimativa feita com uma amostra poderia sair um pouco diferente com outra amostra. O intervalo expressa essa incerteza, sempre dentro das hipóteses do método usado para calculá-lo (Apostila 02 – Regressão Logística, 2026, p. 12). Na leitura mais comum, chamada frequentista, os "95%" descrevem o método: se o estudo fosse repetido muitas vezes, os intervalos feitos desse jeito conteriam o valor verdadeiro em cerca de 95% das vezes (Apostila 02 – Regressão Logística, 2026, p. 13). Pense num pescador cujo jeito de lançar a rede pega o peixe em cerca de 95 de cada 100 lançamentos. Num lançamento qualquer, ele não sabe se o peixe ficou dentro. Os 95% falam do jeito de lançar, não daquela rede.

Um jeito comum de calcular o intervalo é a aproximação de Wald, que a apostila apresenta para o coeficiente de uma regressão logística (Apostila 02 – Regressão Logística, 2026, p. 12). Parte-se da estimativa e do seu erro-padrão, e os limites são:

$$IC_{95\%} \approx \left[\, b - 1{,}96 \times EP \;;\; b + 1{,}96 \times EP \,\right]$$

Aqui, $b$ é a estimativa, o melhor valor que os dados fornecem; $EP$ é o erro-padrão, que mede o quanto essa estimativa é incerta; e 1,96 é o valor da aproximação normal com dois lados usada para 95% de confiança. Com os números inventados da apostila, $b = 0{,}6931$ e $EP = 0{,}250$, a margem é $1{,}96 \times 0{,}250 = 0{,}49$. Os limites ficam em $0{,}6931 - 0{,}49 = 0{,}2031$ e $0{,}6931 + 0{,}49 = 1{,}1831$ (Apostila 02 – Regressão Logística, 2026, p. 12). A fórmula mostra que, quanto maior o erro-padrão, mais largo o intervalo e menos precisa a estimativa.

Na Definição do Estudo, o intervalo acompanha os números de MARKWART et al. (2020, p. 1536): 48,7% dos casos de sepse com disfunção orgânica tratados em UTI tiveram origem no hospital, com IC 95% de 38,3% a 59,3%. A leitura correta é que a melhor estimativa é 48,7% e que os dados são compatíveis com valores entre cerca de 38% e 59%. Um erro comum é achar que 95% dos pacientes estão entre esses limites. O intervalo fala da estimativa, não das pessoas (Apostila 02 – Regressão Logística, 2026, p. 13). O estudo também vai calcular intervalos de confiança para os próprios resultados, mas por outro método, o bootstrap, que entra neste glossário quando aparecer nos documentos novos.

Aparece em: Definição do Estudo.

**Meta-análise** (*meta-analysis*)

A meta-análise é uma técnica estatística que junta os resultados de vários estudos sobre a mesma pergunta num único resumo em número. Ela só é possível quando cada estudo informa sua estimativa de efeito e a variância dessa estimativa, isto é, o quanto ela é incerta (PAGE et al., 2021, Box 1, p. 3). É uma das formas de síntese estatística, termo mais amplo que inclui outros métodos, como combinar os resultados de testes estatísticos ou contar quantos estudos apontam para cada lado (PAGE et al., 2021, Box 1, p. 3). É como juntar as pesquisas de vários institutos num número-resumo, levando em conta a precisão de cada uma, em vez de confiar numa pesquisa só.

A meta-análise costuma fazer parte de uma revisão sistemática, mas não é obrigatória. Uma revisão pode não fazer síntese estatística, por exemplo quando só um estudo cumpre os critérios (PAGE et al., 2021, p. 2). Também pode não fazer porque os estudos não se comparam: foi o caso de YAN et al. (2022, p. 559), que não fizeram meta-análise porque as medidas dos 9 estudos incluídos não podiam ser comparadas. Já MARKWART et al. (2020, p. 1536) fizeram meta-análises de efeitos aleatórios, um tipo de modelo de meta-análise, para chegar a estimativas combinadas (*pooled*) da proporção, da incidência e da mortalidade da sepse de origem hospitalar. Eles relataram heterogeneidade significativa, ou seja, os resultados variaram muito de um estudo para outro. Isso pede cautela ao usar o número combinado como estimativa para um contexto específico.

Na Definição do Estudo, a meta-análise aparece na apresentação de MARKWART et al. (2020). Não confundir com revisão sistemática: a revisão é o processo de buscar, escolher e avaliar os estudos; a meta-análise é uma das formas de juntar estatisticamente os resultados deles.

Aparece em: Definição do Estudo.

**Modelo preditivo** (*prediction model*)

Um modelo preditivo em saúde estima, para cada pessoa, o valor de um desfecho ou o risco de ele acontecer. A maioria estima a chance de uma condição já estar presente, e aí o modelo é chamado de diagnóstico, ou de um desfecho acontecer no futuro, e aí é chamado de prognóstico (COLLINS et al., 2024, p. 1). O uso principal é apoiar decisões clínicas. Há exemplos conhecidos em várias áreas, como o escore de Framingham para doença cardiovascular e o EuroSCORE II para cirurgia cardíaca, e milhares de modelos são publicados todo ano (COLLINS et al., 2024, p. 1). A previsão do tempo é uma boa comparação: com as medidas de hoje, ela estima a chance de chover amanhã. Não garante a chuva, mas dá uma probabilidade que ajuda a decidir se vale levar guarda-chuva.

Dois termos acompanham qualquer modelo preditivo. O desfecho é o evento que se quer prever; em aprendizado de máquina costuma ser chamado de alvo ou rótulo. Os preditores são as características medidas de cada pessoa que entram no modelo, como idade ou pressão arterial, também chamadas de *features*, entradas ou variáveis independentes (COLLINS et al., 2024, Box 1, p. 4). O modelo pode devolver uma probabilidade ou uma classificação. Quando devolve uma classificação, é preciso explicar como foi escolhido o limite que separa as classes (COLLINS et al., 2024, Tabela 2, item 15, p. 7). Nos modelos de aprendizado de máquina, ao contrário da regressão tradicional, o resultado muitas vezes não é uma equação simples, o que exige mais cuidado ao relatar o modelo (COLLINS et al., 2024, p. 2). A mesma diretriz afirma que não existe "modelo validado" e prefere falar em avaliação do modelo (COLLINS et al., 2024, p. 3). Ela pede ainda que os dados de avaliação representem a população em que o modelo será usado (COLLINS et al., 2024, Box 1, p. 4).

Na Definição do Estudo, o modelo preditivo é a ferramenta cujo uso pretendido é apoiar a decisão clínica, na forma de alerta de risco. Aqui, o modelo estima a chance de o paciente desenvolver HOS depois da janela de observação. Pela classificação de COLLINS et al. (2024), isso corresponde a um modelo prognóstico (enquadramento proposto neste glossário).

Aparece em: Definição do Estudo.

**Revisão sistemática** (*systematic review*)

Uma revisão sistemática é uma revisão da literatura que segue métodos explícitos e organizados para reunir e sintetizar os estudos que respondem a uma pergunta bem definida (PAGE et al., 2021, Box 1, p. 3). O que a diferencia de uma revisão comum é o método. A pergunta, os critérios para incluir ou excluir estudos, as bases pesquisadas e a estratégia de busca são definidos e relatados, e a seleção fica registrada, de preferência num fluxograma que mostra quantos estudos foram encontrados, excluídos e incluídos (PAGE et al., 2021, Tabela 1, p. 4). Esse relato completo permite que outra pessoa repita a revisão (PAGE et al., 2021, p. 6). É como escolher um restaurante lendo todas as avaliações publicadas, com critérios decididos antes, e anotando por que cada uma foi aceita ou descartada, em vez de perguntar a alguns amigos.

Revisões sistemáticas têm vários papéis: resumem o que se sabe numa área, ajudam a apontar o que falta pesquisar, respondem perguntas que estudos isolados não conseguem responder e mostram problemas nos estudos originais (PAGE et al., 2021, p. 1). A diretriz PRISMA 2020, que substituiu a de 2009, orienta como relatá-las com uma lista de 27 itens (PAGE et al., 2021, p. 1). YAN et al. (2022, p. 560) seguiram a PRISMA na revisão sobre uso de texto clínico com aprendizado de máquina para sepse. MARKWART et al. (2020, p. 1536) juntaram revisão sistemática e meta-análise para estimar o peso da sepse de origem hospitalar.

Na Definição do Estudo, esses dois trabalhos são citados como revisões sistemáticas. Não confundir com meta-análise, descrita na entrada anterior: a revisão é o processo de buscar e escolher os estudos; a meta-análise é uma das formas de juntar os resultados deles.

Aparece em: Definição do Estudo.