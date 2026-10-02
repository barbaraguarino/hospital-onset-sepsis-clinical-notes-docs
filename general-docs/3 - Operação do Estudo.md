# Operação do Estudo

**Versão**: X.X | **Data**: DD/MM/AAAA | **Fase**: Operação

**Como usar este documento**:

- Este documento é escrito **durante** a execução, no mesmo dia de cada etapa, e não reconstruído de memória no final. É ele que permite reproduzir o estudo e defender cada número depois.
- Aqui entra **o que aconteceu**, não os resultados de desempenho: métricas e testes estatísticos ficam em Análise e Interpretação do Estudo.
- Tudo que for executado de forma diferente da versão 1.0 congelada da Definição e do Planejamento é registrado como desvio do plano, mesmo que pareça pequeno.
- A versão começa em **0.1** quando o documento ganha o primeiro conteúdo e sobe 0.1 a cada revisão fechada (fim de um chat de revisão, não a cada pequena edição). O documento vira **1.0** na entrega final (04/12/2026). A Data é a da última edição do documento.
- Marque só o que falta decidir com **[A decidir]**. O que não tem marcação já está decidido.
- Todo número vem com a fonte ao lado. Aqui, a fonte normalmente é a própria execução: indique o commit, o script ou a consulta que gerou o número.
- Todo termo clínico ou técnico novo é definido no Apêndice C – Glossário e Fundamentação.
- Para remeter a outro documento, cite o documento inteiro (ex.: "ver Planejamento do Estudo"), nunca uma seção pelo nome.
- Datas no formato DD/MM/AAAA.

## 17. Preparação

> Registre, com data, o que foi feito antes da execução completa:
>
> - **Ética e acesso:** resposta do CEP (ou informação de que a apreciação não é necessária), credenciamento e termo de uso do dataset
> - **Dados:** download ou carga do dataset (versão e data), verificação de integridade (ex.: conferir se os arquivos batem com os *checksums* publicados pelos mantenedores, quando existirem) e contagem de linhas das tabelas usadas
> - **Ambiente:** máquina, sistema operacional, versões da linguagem, das bibliotecas e do banco de dados, e o arquivo que fixa essas versões (ex.: `requirements.txt`)
> - **Execução-piloto:** quando foi feita, com qual amostra, o que deu errado e o que mudou por causa dela. O piloto nunca usa o conjunto de teste
> - **Congelamento:** data e tag do Git da versão 1.0 da Definição e do Planejamento, criada depois do piloto e antes da execução completa
>
> *Exemplo (ilustrativo, não é deste estudo):* "10/10/2026: o CEP informou por e-mail que a apreciação não é necessária (e-mail arquivado). 12/10/2026: dataset versão X baixado; *checksums* conferidos; tabelas carregadas no PostgreSQL, com contagem de linhas igual à da documentação. 14/10/2026: ambiente fixado em `requirements.txt`. 18/10/2026: execução-piloto com 1% das internações; a consulta de sinais vitais levou mais de 2 h e foi reescrita com índice. 20/10/2026: versão 1.0 congelada (tag `v1.0`)."
>

## 18. Registro de Execução

> Uma entrada por execução de uma etapa do pipeline (extração, pré-processamento, treino, avaliação), inclusive as que falharam. Para cada uma:
>
> - Data e etapa
> - Versão do código (hash do *commit* ou tag) e configuração usada (parâmetros, sementes)
> - Duração e recursos usados, quando relevante (ex.: memória insuficiente)
> - O que foi gerado e onde está (arquivos de saída), sem os valores das métricas
> - Ocorrências: erros, avisos e qualquer coisa fora do previsto
>
> ⚠️ Registre explicitamente **cada vez que o conjunto de teste for usado**. O planejado é uma única vez, no final; qualquer uso adicional é desvio do plano.
>
> *Exemplo (ilustrativo, não é deste estudo):*
>
> - "22/10/2026 — Extração (commit `a1b2c3d`): 3 consultas SQL, 1h40. Tabelas intermediárias salvas no esquema `estudo`. Aviso: 12 internações com data de alta anterior à admissão, tratadas na validação dos dados."
> - "25/10/2026 — Treino do modelo A (commit `d4e5f6a`, semente 42): busca de hiperparâmetros interrompida por falta de memória; grade reduzida (desvio DV-01) e reexecutada no mesmo dia."
> - "30/10/2026 — Avaliação final no conjunto de teste (commit `b7c8d9e`): primeiro e único uso do teste. Predições salvas localmente, fora do repositório."

## 19. Desvios do Plano

> Tudo que foi executado de forma diferente da versão 1.0 congelada da Definição e do Planejamento. Dê a cada desvio um ID (DV-01, DV-02...) e registre:
>
> - **Planejado:** o que a versão 1.0 dizia
> - **Ocorrido:** o que foi feito no lugar
> - **Motivo**
> - **Quando foi percebido:** antes ou depois de ver resultados no conjunto de teste. Um desvio decidido depois de ver o teste pode ter sido guiado pelo resultado e precisa ser declarado como tal
> - **Impacto na validade:** tipo de ameaça (conclusão, interna, construto ou externa) e como ela afeta o estudo. Esse impacto é retomado na reavaliação das ameaças à validade (ver Análise e Interpretação do Estudo)
>
> Se o desvio exigiu escolher entre alternativas, a escolha também entra no Apêndice A – Registro de Decisões, citando o ID do desvio.
>
> *Exemplo (ilustrativo, não é deste estudo):* "**DV-01.** Planejado: busca de hiperparâmetros em grade com 200 combinações por modelo. Ocorrido: grade reduzida para 50 combinações, a mesma para A e B. Motivo: memória insuficiente na máquina disponível. Percebido: durante o treino, antes de qualquer uso do teste. Impacto: validade de conclusão; os modelos podem ficar abaixo do melhor desempenho possível, mas como a redução foi igual para os dois, a comparação entre eles se mantém."
>

## 20. Validação dos Dados

> Registre as verificações feitas sobre os dados extraídos, os problemas encontrados e o que foi feito com cada um, sempre com o critério aplicado e onde ele foi definido (ver Planejamento do Estudo). Uma exclusão cujo critério não estava no planejamento também é um desvio do plano.
>
> - **Fluxograma da coorte:** quantas unidades havia no início e quantas saíram em cada critério de inclusão e exclusão, na ordem de aplicação, até a coorte final
> - **Coerência:** datas em ordem (ex.: admissão antes da alta), valores plausíveis, duplicatas, unidades de medida misturadas
> - **Valores ausentes:** proporção por variável de entrada
> - **Rótulo:** proporção de casos positivos na coorte (comparada à esperada no planejamento, se havia uma estimativa com fonte) e conferência manual de uma pequena amostra de positivos e negativos
> - **Vazamento de dados:** conferência de que nenhuma entrada é posterior ao momento da predição e de que nenhum paciente aparece no treino e no teste ao mesmo tempo
> - **Onde estão os dados:** local de armazenamento (fora do repositório) e versão da extração (o commit das consultas que os geraram)
>
> Aqui entram as exclusões por critérios de elegibilidade e de qualidade dos dados. A remoção estatística de valores extremos durante a análise, se prevista, é registrada em Análise e Interpretação do Estudo.
>
> *Exemplo (ilustrativo, não é deste estudo):* "Fluxograma: 58.000 internações no dataset → 46.000 de adultos → 9.800 com insuficiência cardíaca → 8.900 após excluir óbitos → 8.700 após excluir transferências (coorte final). Coerência: 12 internações com alta anterior à admissão, excluídas por datas incoerentes (critério de qualidade previsto no Planejamento). Ausentes: peso ausente em 31% das internações. Rótulo: 19% de readmissões; 20 casos conferidos manualmente, todos corretos. Vazamento: nenhuma entrada posterior à alta e nenhum paciente nos dois conjuntos (verificação automática no commit `e7f8a9b`). Dados: PostgreSQL local, esquema `estudo`, extração do commit `a1b2c3d`."
>