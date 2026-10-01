# Análise e Interpretação do Estudo

**Versão**: X.X | **Data**: DD/MM/AAAA | **Fase**: Análise e Interpretação

**Como usar este documento:**

- Todos os resultados vêm da avaliação única do conjunto de teste registrada na Operação do Estudo (predições salvas) e seguem o plano de análise do Planejamento do Estudo. O que não estava planejado é marcado como **exploratório**.
- Reporte **tudo** que foi planejado, inclusive resultados não significativos ou contrários à hipótese. Omitir resultados desfavoráveis distorce a conclusão.
- Todo número vem com a fonte ao lado. Aqui, a fonte é o script (e o commit) que o gerou; números de outros estudos vêm com (AUTOR, ANO).
- Figuras e tabelas não mostram registros individuais de pacientes nem trechos de notas clínicas.
- A versão começa em **0.1** quando o documento ganha o primeiro conteúdo e sobe 0.1 a cada revisão fechada (fim de um chat de revisão, não a cada pequena edição). O documento vira **1.0** na entrega final (04/12/2026). A Data é a da última edição do documento.
- Marque só o que falta decidir com **[A decidir]**. O que não tem marcação já está decidido.
- Todo termo clínico ou técnico novo é definido no Apêndice C – Glossário e Fundamentação.
- Para remeter a outro documento, cite o documento inteiro (ex.: "ver Operação do Estudo"), nunca uma seção pelo nome.
- Datas no formato DD/MM/AAAA.

## 21. Estatística Descritiva

> Em ML, a descrição tem duas partes.
>
>
> **Parte 1 — A coorte.** A partir da coorte final validada (ver Operação do Estudo), descreva as características dos pacientes, separadas por desfecho (positivos e negativos) e por conjunto (treino e teste). Em artigos clínicos, essa tabela costuma ser chamada de "Tabela 1":
>
> - Variáveis contínuas (ex.: idade): mediana e intervalo interquartil, ou média e desvio padrão se a distribuição for aproximadamente simétrica
> - Variáveis categóricas (ex.: sexo): contagem e percentual
> - Proporção de valores ausentes por variável
> - Proporção de casos positivos em cada conjunto
>
> A comparação entre treino e teste mostra se a divisão produziu conjuntos parecidos.
>
> **Parte 2 — O desempenho.** Para cada tratamento e cada referência descritiva: a métrica principal e as secundárias no conjunto de teste, cada uma com intervalo de confiança. No lugar de boxplots, os gráficos típicos são as curvas que acompanham as métricas escolhidas (ex.: curva ROC para a AUROC).
>
> Registre onde estão os scripts, as tabelas e os gráficos.
>
> *Exemplo (ilustrativo, não é deste estudo):* "Coorte final: 8.700 internações (treino 6.960; teste 1.740). Idade: mediana de 74 anos (IIQ 64–82) nos readmitidos e de 71 anos (IIQ 60–80) nos não readmitidos. Readmissões: 19,1% no treino e 19,0% no teste. Modelo A: AUROC 0,68 (IC 95%: 0,65–0,71). Modelo B: AUROC 0,72 (IC 95%: 0,69–0,75). Tabela 1 em `resultados/tabela1.csv` e curvas ROC em `resultados/curvas_roc.png`, gerados por `analise/descritiva.py` (commit `c1d2e3f`)."
>

## 22. Redução do Conjunto de Dados

> Em experimentos com pessoas, esta etapa remove participantes com dados inválidos antes do teste de hipóteses. Em ML, as exclusões por elegibilidade e qualidade já foram feitas e registradas na validação dos dados (ver Operação do Estudo), então esta seção costuma ser curta. Registre:
>
> - Se alguma unidade foi removida **do conjunto usado na análise** depois da validação dos dados, com o critério e onde ele foi definido antes (ver Planejamento do Estudo)
> - Para cada remoção: quantas unidades, por quê e se o resultado muda com e sem elas (análise de sensibilidade)
> - Se nenhuma unidade foi removida, diga isso explicitamente
>
> ⚠️ Nunca remova unidades do conjunto de teste porque o modelo errou nelas ou porque parecem "atípicas" depois de ver as predições. Isso ajusta o resultado ao que se queria encontrar. Os casos em que o modelo erra são material de análise exploratória, não de exclusão.
>
> *Exemplo (ilustrativo, não é deste estudo):* "Nenhuma unidade removida após a validação dos dados. Os valores extremos de sinais vitais foram tratados no pré-processamento, antes do treino, com o critério previsto no planejamento (ver Operação do Estudo)."
>

## 23. Teste de Hipóteses

> **Parte 1 — Hipóteses (QPs confirmatórias).** Para cada hipótese:
>
> - Métrica de cada tratamento no teste, com intervalo de confiança
> - Teste aplicado e verificação das suas premissas
> - Estatística do teste (quando houver) e **p-valor exato** (ex.: p = 0,031, e não apenas "p < 0,05")
> - **Tamanho de efeito:** em ML, normalmente a diferença entre as métricas, com intervalo de confiança
> - **Decisão:** rejeita ou não rejeita H0, ao nível α definido no planejamento
> - **Conformidade com o plano:** igual ao planejado ou, se não, qual foi o desvio (ID DV-xx; ver Operação do Estudo)
>
> **Parte 2 — Análises exploratórias.** Separadas das hipóteses e marcadas como exploratórias. Para cada uma, indique se estava **planejada** (QPs exploratórias, explicabilidade, subgrupos, leitura de casos) ou se surgiu **depois** de ver os resultados (*post hoc*). Registre o método, como os casos foram escolhidos (quando for o caso) e o resultado, sem conclusão confirmatória: uma análise exploratória levanta hipóteses para estudos futuros, não as confirma.
>
> Em análises qualitativas de texto clínico, descreva os casos com suas próprias palavras e em termos das categorias definidas antes, sem copiar trechos das notas (ver Planejamento do Estudo, sobre ética e termos de uso).
>
> *Exemplos (ilustrativos, não são deste estudo):*
>
> - "H0-1: diferença AUROC_B − AUROC_A = 0,04 (IC 95%: 0,01–0,07), por *bootstrap* pareado com 1.000 reamostragens por paciente; p = 0,012. H0-1 rejeitada ao nível α = 0,05. Conforme o planejado."
> - "Exploratória planejada: nos 40 casos em que B acertou e A errou, lidos com a ficha de quatro categorias, a categoria mais frequente foi instabilidade dos sinais vitais nas últimas 24 horas antes da alta (18 casos)."
> - "Exploratória *post hoc*: a diferença entre os modelos pareceu maior em pacientes acima de 75 anos; não testada formalmente."

## 24. Interpretação

> O que os resultados significam **dentro do contexto do estudo**. Organize em cinco partes:
>
> - **Resposta a cada QP:** uma resposta direta, na ordem das QPs. As confirmatórias se apoiam no teste de hipóteses; as exploratórias são respondidas com cautela e marcadas como tal
> - **Importância prática:** a diferença encontrada é grande o suficiente para importar na prática? Compare com a diferença relevante definida no planejamento, se houver. Significância estatística não é o mesmo que relevância clínica
> - **Comparação com a literatura:** confronte os resultados com os estudos do Apêndice B – Matriz de Literatura, citando (AUTOR, ANO). Diga o que torna a comparação direta ou não (dataset, população, definição do desfecho, métrica)
> - **Reavaliação das ameaças à validade:** retome cada ameaça prevista no Planejamento do Estudo e diga se o risco residual se confirmou ou mudou; acrescente as novas ameaças criadas pelos desvios (IDs DV-xx; ver Operação do Estudo). As ameaças originais continuam intactas no Planejamento; a reavaliação fica só aqui
> - **O que os resultados não permitem concluir:** limites explícitos (ex.: desempenho em outro hospital, utilidade no uso clínico real, relação de causa entre as variáveis e o desfecho)
>
> *Exemplo (ilustrativo, não é deste estudo):* "QP1: neste dataset, acrescentar sinais vitais aos dados de admissão melhorou a predição de readmissão (diferença de 0,04 na AUROC). A diferença é modesta e seu impacto clínico não foi avaliado. O resultado vai na mesma direção de (AUTOR, ANO), que usou outro hospital e outra definição de readmissão, o que impede comparar os valores diretamente. Reavaliação: a redução da grade de hiperparâmetros (DV-01) afetou os dois modelos igualmente e não altera a comparação; a validade externa continua com risco alto (um único hospital). Não é possível concluir que o modelo B funcionaria em outro hospital nem que reduziria readmissões se usado na prática."
>