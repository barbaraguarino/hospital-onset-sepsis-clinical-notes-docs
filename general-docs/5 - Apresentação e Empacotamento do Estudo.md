# Apresentação e Empacotamento do Estudo

**Versão**: 0.1 | **Data**: 27/09/2026 | **Fase**: Apresentação e Empacotamento

**Como usar este documento:**

- Este documento tem duas funções. **Orientação** (estrutura do artigo, estilo de escrita e Jupyter Notebook): consulte desde já, sempre que for escrever qualquer entregável. **Registro** (entregáveis, pacote de replicação, conformidade com o TRIPOD+AI e revisão final): preencha na fase final, com o que foi efetivamente entregue.
- As seções de orientação são texto do próprio documento. As seções de registro trazem a orientação neste formato de bloco, seguida do espaço para preencher.
- A versão começa em **0.1** quando o documento ganha o primeiro conteúdo e sobe 0.1 a cada revisão fechada (fim de um chat de revisão, não a cada pequena edição). O documento vira **1.0** na entrega final (04/12/2026). A Data é a da última edição do documento.
- Marque só o que falta decidir com **[A decidir]**. O que não tem marcação já está decidido.
- Todo número vem com a fonte ao lado: (AUTOR, ANO) para outros estudos; script e commit para resultados deste estudo.
- Para remeter a outro documento, cite o documento inteiro (ex.: "ver Planejamento do Estudo"), nunca uma seção pelo nome.
- Datas no formato DD/MM/AAAA.

## 25. Entregáveis Finais

> Liste cada entregável, o que ele precisa conter e, na fase final, a versão, a data e onde está (link ou caminho).
>
>
> Entregáveis previstos:
>
> - **README.md**: o artigo completo, com a estrutura descrita adiante
> - **Jupyter Notebook**: o pipeline comentado célula a célula, com cada decisão justificada no texto
> - **Repositório (pacote de replicação)**: código, consultas SQL, ambiente e instruções, sem os dados
> - **Checklist de reprodutibilidade** conferido
> - **Checklist TRIPOD+AI** preenchido, como material suplementar
> - **Apresentação oral ou slides**: [A decidir] (confirmar com o professor se faz parte da entrega)
>
> *Exemplo (ilustrativo, não é deste estudo):* "README.md — versão final, 01/12/2026, raiz do repositório, tag `v2.0-entrega`. Notebook — `notebooks/estudo.ipynb`, mesma tag, executado do início ao fim em 30/11/2026."
>

## 26. Estrutura do Artigo (README)

O README é escrito como um artigo científico completo. A tabela abaixo lista as seções, o que vai em cada uma, de qual documento de trabalho sai o conteúdo e qual exigência do professor ela atende (marcada com ★). Todas as exigências do professor precisam aparecer: motivação, dataset, formalização matemática, método de validação, medidas de desempenho, avaliação e conclusão.

| Seção do artigo | O que contém | Sai de | ★ Exigência do professor |
| --- | --- | --- | --- |
| **Título** | Identifica o estudo como desenvolvimento/avaliação de um modelo preditivo, com a população e o desfecho | Definição do Estudo |  |
| **Resumo** | Estruturado: contexto, objetivo, métodos, resultados (com números principais) e conclusão | Todos |  |
| **Abstract** | Versão em inglês do resumo: [A decidir] | — |  |
| **Palavras-chave** | 3 a 6 termos | — |  |
| **1. Introdução** | Problema clínico, por que importa, por que ML, lacuna, objetivo, QPs e contribuição | Definição do Estudo | ★ Motivação |
| **2. Trabalhos Relacionados** | Estratégia de busca, síntese comparativa e onde este estudo entra | Definição do Estudo; Apêndice B |  |
| **3. Métodos** |  |  |  |
| 3.1 Fonte de dados | Dataset: origem, período, pacientes cobertos, tipos de dado, versão, acesso | Planejamento do Estudo | ★ Dataset |
| 3.2 Coorte | Unidade de análise, população, critérios de inclusão e exclusão | Planejamento do Estudo | ★ Dataset |
| 3.3 Desfecho | Definição conceitual e operacional | Planejamento do Estudo; Apêndice C |  |
| 3.4 Formulação do problema | Notação matemática da tarefa: entradas, rótulo, janelas de tempo, função que o modelo aprende | Planejamento do Estudo | ★ Formalização matemática |
| 3.5 Entradas e pré-processamento | Grupos de entradas, tratamento de ausentes e de valores extremos, processamento de texto | Planejamento do Estudo; Operação do Estudo |  |
| 3.6 Modelos e treinamento | Algoritmos, hiperparâmetros, busca de hiperparâmetros | Planejamento do Estudo |  |
| 3.7 Validação | Divisão dos dados, unidade da divisão, uso único do teste | Planejamento do Estudo | ★ Método de validação |
| 3.8 Métricas e análise estatística | Métricas principal e secundárias, hipóteses, teste, α, limiar de decisão | Planejamento do Estudo | ★ Medidas de desempenho |
| 3.9 Análises exploratórias | Explicabilidade, subgrupos, leitura de casos, análises de sensibilidade | Planejamento do Estudo |  |
| 3.10 Ética | Aprovação, termos de uso, proteção dos dados | Planejamento do Estudo |  |
| 3.11 Desvios do plano | O que mudou em relação à versão 1.0 e por quê | Operação do Estudo |  |
| **4. Resultados** |  |  | ★ Avaliação |
| 4.1 Coorte | Fluxograma e Tabela 1 | Operação do Estudo; Análise e Interpretação |  |
| 4.2 Desempenho | Métricas de cada modelo com IC; curvas | Análise e Interpretação |  |
| 4.3 Hipóteses | Teste, p-valor exato, tamanho de efeito, decisão | Análise e Interpretação |  |
| 4.4 Análises exploratórias | Resultados rotulados como exploratórios | Análise e Interpretação |  |
| **5. Discussão** | Principais achados, importância prática, comparação com a literatura, limitações (ameaças à validade reavaliadas), o que não pode ser concluído | Análise e Interpretação |  |
| **6. Conclusão** | Resposta curta a cada QP e trabalhos futuros | Análise e Interpretação | ★ Conclusão |
| **Disponibilidade de dados e código** | Onde está o código; como obter os dados pelos canais oficiais | Este documento (pacote de replicação) |  |
| **Declarações** | Ética; financiamento; conflitos de interesse; envolvimento de pacientes e do público (se não houve, declarar); uso de ferramentas de IA na preparação do estudo e do texto | Planejamento do Estudo; este documento |  |
| **Agradecimentos** | Opcional | — |  |
| **Referências** | No estilo final: [A decidir] | Referências |  |
| **Material suplementar** | Checklist TRIPOD+AI preenchido; detalhes de hiperparâmetros; tabelas extras | Este documento |  |

Antes de fechar o texto, confira no checklist TRIPOD+AI (Collins et al., 2024) os itens específicos de título e resumo e os de ciência aberta, que costumam ser esquecidos.

## 27. Estilo de Escrita

**Leitor.** Escreva para dois leitores ao mesmo tempo: alguém de computação sem formação em saúde e alguém da saúde sem formação em ML. Todo termo técnico ou clínico e toda sigla são definidos na primeira ocorrência.

**Tempo verbal e voz.** Métodos e resultados no passado ("a coorte foi composta por..."); interpretação e conclusões no presente ("os resultados indicam..."). Voz impessoal ("foi realizado", "este estudo").

**Parágrafos.** Um parágrafo, uma ideia. A primeira frase diz do que o parágrafo trata.

**Números.**

- Todo número vem com a fonte: (AUTOR, ANO) para outros estudos; para os resultados deste estudo, a fonte é a saída do notebook, e os números do texto precisam ser iguais a ela.
- Vírgula decimal (padrão brasileiro) e o mesmo número de casas decimais para a mesma métrica em todo o texto.
- Métricas sempre com intervalo de confiança; p-valor exato; tamanho de efeito junto de todo teste.

**Resultados e interpretação separados.** Resultados descrevem o que foi observado, sem opinião. A Discussão interpreta.

**Honestidade.**

- Análises exploratórias sempre rotuladas como tal.
- Nada de causalidade ("a variável X causa o desfecho"): o estudo é preditivo.
- A novidade se escreve como "não encontrada na literatura revisada", nunca como "inédita".
- Os desvios do plano são declarados, não escondidos.
- Resultados não significativos são reportados como os demais.

**Proteção dos dados.** Nenhum trecho de nota clínica e nenhum registro individual no texto, nas figuras ou nas tabelas. Casos são descritos com suas palavras e em termos de categorias.

**Figuras e tabelas.**

- Numeradas e citadas no texto antes de aparecerem.
- A legenda se explica sozinha: o que é, qual conjunto de dados, n.
- A leitura não depende só de cor.

**Citações.** Nunca cite o que não leu. Toda citação no texto está nas Referências, e vice-versa.

**Markdown do README.** O GitHub renderiza fórmulas em LaTeX entre `$...$` (na linha) e `$$...$$` (em bloco). Figuras entram por caminho relativo dentro do repositório.

## 28. Jupyter Notebook

**O que é.** Um arquivo `.ipynb` que mistura dois tipos de célula: **texto** (em Markdown) e **código** (Python). Cada célula de código é executada separadamente, e a saída dela (números, tabelas, gráficos) aparece logo abaixo e **fica salva dentro do arquivo**.

**Como difere de um script.** Um script `.py` sempre roda inteiro, de cima para baixo. No notebook, um processo chamado **kernel** guarda na memória tudo o que já foi executado (variáveis, dados carregados), e você pode rodar as células em qualquer ordem. Isso é prático para explorar, mas cria a armadilha principal: o resultado pode depender da ordem em que você rodou as células, e não da ordem em que elas aparecem. Por isso, antes de qualquer entrega, **reinicie o kernel e execute todas as células em ordem**. Se der erro, o notebook não está reprodutível.

**Como rodar no DataSpell.** Abra o `.ipynb`, selecione como kernel o interpretador Python do ambiente do projeto (o mesmo do `requirements.txt`) e execute célula a célula ou todas de uma vez.

**Divisão em partes.** Cada parte começa com um título em Markdown:

1. Cabeçalho: título, objetivo, como executar, versão do código (tag ou commit)
2. Configuração: importações, sementes aleatórias, caminhos, versões das bibliotecas impressas na tela
3. Extração dos dados
4. Validação dos dados e construção da coorte (fluxograma)
5. Pré-processamento
6. Modelagem e treinamento
7. Avaliação no conjunto de teste (uma única vez)
8. Análises exploratórias
9. Resumo dos resultados

**Regra de ouro dos comentários.** Antes de cada bloco de código, uma célula de texto diz:

- **o que** o bloco faz;
- **por que** foi feito assim (a decisão, a alternativa descartada e, quando houver, o ID no Registro de Decisões);
- **o que esperar** da saída.

Depois de cada saída importante, uma célula de texto interpreta o resultado. Os comentários dentro do código explicam o *como*; as células de texto explicam o *porquê*.

**Código longo.** Funções longas ou reutilizadas ficam em módulos `.py` (ex.: pasta `src/`) importados pelo notebook, que fica responsável por contar a história. Isso deixa o notebook legível e permite testar as funções separadamente. O custo é que o leitor precisa abrir outro arquivo para ver os detalhes.

**Saídas e privacidade.** Como as saídas ficam salvas dentro do `.ipynb`, tudo o que aparecer na tela vai junto para o GitHub.

- Mantenha as saídas com resultados agregados (métricas, contagens, gráficos).
- Nunca exiba linhas de dados de pacientes (ex.: `df.head()`) nem trechos de notas.
- Para apagar todas as saídas de um notebook: `jupyter nbconvert --clear-output --inplace arquivo.ipynb`.

**Nunca no notebook:** senhas ou credenciais do banco (use arquivo de configuração fora do repositório).

## 29. Pacote de Replicação

> Descreva o que foi publicado para que outra pessoa possa refazer o estudo:
>
> - **Estrutura do repositório**, com a função de cada pasta (ex.: `notebooks/`, `src/`, `sql/`, `resultados/` só com resultados agregados, `requirements.txt`, `../.gitignore`, `LICENSE`; documentos de trabalho em `docs/`: [A decidir])
> - **O que não está no pacote e por quê:** os dados (termo de uso do dataset) e as credenciais
> - **Como obter os dados:** o caminho oficial de acesso e credenciamento
> - **Como executar:** ordem dos passos, tempo aproximado e hardware usado
> - **Versão final:** tag ou release do Git correspondente aos resultados relatados; DOI (ex.: Zenodo, gratuito), se houver
>
> **Checklist de reprodutibilidade** (marque na fase final):
>
> - [ ]  Versões fixadas (`requirements.txt`), com as versões do Python e do banco de dados informadas
> - [ ]  Sementes aleatórias fixadas e informadas
> - [ ]  Instruções para obter os dados pelo canal oficial
> - [ ]  Consultas SQL de extração incluídas
> - [ ]  Ordem de execução documentada; o notebook roda do início ao fim com o kernel reiniciado
> - [ ]  Tag ou commit correspondente aos resultados relatados
> - [ ]  Hardware e tempo de execução aproximado informados
> - [ ]  Números do README conferidos contra as saídas do notebook
> - [ ]  Nenhum dado individual nem credencial no repositório, **incluindo o histórico do Git** (um arquivo apagado continua no histórico se já foi versionado)
> - [ ]  Licença do código definida

## 30. Conformidade com o TRIPOD+AI

> Use o checklist oficial do TRIPOD+AI (Collins et al., 2024), disponível no site do TRIPOD. Para cada item, registre onde ele foi atendido no README ou, se não se aplicar, a justificativa. Alguns itens valem só para o desenvolvimento do modelo, outros só para a avaliação, e o checklist indica isso em cada item. O checklist preenchido vai como material suplementar do artigo.
>
>
>
> | Item | Resumo do item | Onde foi atendido | Observação |
> | --- | --- | --- | --- |
> |  |  |  |  |
>
> *Exemplo (ilustrativo, não é deste estudo):* "Item sobre o fluxo de participantes — atendido na seção de resultados da coorte (fluxograma). Item sobre envolvimento de pacientes e do público — não houve envolvimento; declarado nas Declarações."
>

## 31. Revisão Final

> Antes de entregar, confira:
>
> - [ ]  Todas as exigências do professor aparecem no README (motivação, dataset, formalização matemática, método de validação, medidas de desempenho, avaliação, conclusão)
> - [ ]  Todo número tem fonte; os números do texto batem com as saídas do notebook
> - [ ]  Toda citação está nas Referências e toda referência é citada; referências conferidas na fonte primária
> - [ ]  Termos e siglas definidos na primeira ocorrência
> - [ ]  Análises exploratórias rotuladas; desvios do plano declarados; resultados não significativos reportados
> - [ ]  Nenhum trecho de nota clínica nem registro individual no texto, nas figuras, nas tabelas ou no notebook
> - [ ]  Links funcionando; figuras e fórmulas aparecendo corretamente no GitHub
> - [ ]  Checklist de reprodutibilidade e checklist TRIPOD+AI completos
> - [ ]  Revisão ortográfica e leitura corrida do texto inteiro