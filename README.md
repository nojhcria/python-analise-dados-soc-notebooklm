# Python para Análise de Dados aplicada ao SOC com NotebookLM

## Contexto do Projeto

Este projeto foi desenvolvido como parte do Bootcamp **Bradesco - GenAI, Dados & Cyber**, com o objetivo de utilizar o **NotebookLM** como ferramenta de aprendizagem ativa.

O tema escolhido foi:

**Python para Análise de Dados aplicada ao SOC**

A escolha do tema está relacionada ao meu objetivo de conectar conhecimentos de **Segurança da Informação / SOC** com minha jornada de aprendizado em **Python, análise de dados e automação**.

A proposta deste projeto foi utilizar fontes abertas e confiáveis para estudar como Python pode apoiar a análise de dados em uma rotina de SOC, considerando chamados, alertas, severidade, status, SLA e relatórios operacionais.

---

## Objetivos de Estudo

Os principais objetivos deste projeto foram:

* Entender como Python pode ser usado em uma rotina de SOC.
* Compreender como arquivos CSV podem armazenar dados de chamados, alertas e logs.
* Estudar como a biblioteca pandas pode apoiar análises operacionais.
* Relacionar análise de dados com atividades de segurança, como triagem, priorização e resposta a incidentes.
* Criar um miniguia de estudo com resumos, glossário e prompts reutilizáveis.
* Documentar o processo de aprendizagem no GitHub.

---

## Curadoria de Fontes

As fontes abaixo foram selecionadas por serem abertas, confiáveis e relacionadas ao tema do projeto.

### 1. Python - Documentação do módulo CSV

Fonte usada para entender como Python pode ler e escrever arquivos CSV, formato comum para exportação de dados de chamados, alertas e relatórios.

Link:
https://docs.python.org/pt-br/3/library/csv.html

---

### 2. pandas - Documentação oficial

Fonte usada para estudar estruturas e funções básicas de análise de dados com Python, como DataFrame, filtros, agrupamentos e resumos.

Link:
https://pandas.pydata.org/docs/

---

### 3. NIST SP 800-61 - Incident Response

Fonte usada para relacionar análise de dados com resposta a incidentes e práticas de segurança.

Link:
https://csrc.nist.gov/pubs/sp/800/61/r3/final

---

## Uso do NotebookLM

Após selecionar as fontes, criei um caderno temático no NotebookLM com o nome:

**Python para Análise de Dados aplicada ao SOC**

O NotebookLM foi utilizado para:

* Resumir conceitos técnicos das fontes selecionadas.
* Relacionar Python, CSV e pandas com análise de dados em SOC.
* Criar exemplos de dados que podem ser analisados em uma operação de segurança.
* Sugerir métricas simples para chamados e alertas.
* Apoiar a construção deste miniguia de estudo.



-------------


---

# Engenharia de Prompts e Cicatrizes do Processo

Nesta etapa, foram testados prompts estratégicos no NotebookLM para extrair respostas mais úteis e aplicadas ao tema escolhido.

---

## Prompt 1 — Visão geral do tema

### Prompt utilizado

```text
Com base nas fontes carregadas, explique como Python pode ser usado para análise de dados em uma rotina de SOC. Foque em chamados, alertas, severidade, status, SLA e relatórios operacionais. Explique em linguagem simples.
```

### Resposta obtida

O NotebookLM explicou que Python pode apoiar a rotina de um SOC ao automatizar a leitura e organização de dados de chamados e alertas, principalmente quando esses dados são exportados em formato CSV.

A resposta destacou que o módulo `csv` do Python e a biblioteca `pandas` permitem transformar dados em tabelas organizadas, facilitando análises por severidade, status, SLA e relatórios operacionais.

Também foram citados recursos como:

* leitura de arquivos CSV;
* uso de DataFrames;
* contagem de chamados por severidade;
* filtros para alertas críticos;
* cálculo de tempo de SLA;
* criação de relatórios operacionais;
* uso de agrupamentos com `groupby()`;
* geração de resumos com `describe()`.

### Fontes utilizadas na resposta

* Documentação oficial do módulo CSV do Python.
* Documentação oficial do pandas.
* Fonte sobre resposta a incidentes.

### Cicatriz / dificuldade encontrada

A primeira resposta ficou boa, mas ainda trouxe uma visão ampla. Para deixar o resultado mais útil, foi importante direcionar o prompt com termos específicos da rotina de SOC, como chamados, alertas, severidade, status, SLA e relatórios operacionais.

---

## Prompt 2 — Tipos de dados analisados em SOC

### Prompt utilizado

```text
Quais tipos de dados podem ser analisados em uma rotina de SOC usando Python? Organize em uma tabela com as colunas: tipo de dado, exemplo fictício e possível análise.
```

### Resposta obtida

O NotebookLM organizou os principais tipos de dados que podem ser analisados em uma rotina de SOC usando Python.

| Tipo de dado          | Exemplo fictício                     | Possível análise                                                     |
| --------------------- | ------------------------------------ | -------------------------------------------------------------------- |
| Alertas de segurança  | Tipo: Força Bruta                    | Identificar tipos de alertas mais frequentes usando `value_counts()` |
| Status e severidade   | Severidade: Crítica / Status: Aberto | Filtrar incidentes críticos abertos usando indexação booleana        |
| Métricas de SLA       | Data de abertura e data de resposta  | Calcular tempo de resposta e verificar cumprimento de SLA            |
| Logs de incidentes    | Evento: Acesso Negado                | Agrupar eventos por usuário, sistema ou tipo de ocorrência           |
| Performance da equipe | Chamados fechados por analista       | Criar relatórios de produtividade e carga de trabalho                |


### Fontes utilizadas na resposta

* Documentação do pandas.
* Documentação do módulo CSV.
* Fonte sobre resposta a incidentes.

### Cicatriz / dificuldade encontrada

A resposta trouxe bons exemplos, mas alguns exemplos pareciam próximos de dados reais, como IPs e nomes de usuários. Para um projeto de GitHub, é importante reforçar que os dados devem ser fictícios, anonimizados e sem exposição de informações sensíveis.


----------

---

## Prompt 3 — Leitura e análise de CSV com Python

### Prompt utilizado

```text
Com base nas fontes sobre Python, CSV e pandas, explique como um arquivo CSV de chamados SOC poderia ser lido, analisado e resumido com Python. Use exemplos simples para iniciante.
```

### Resposta obtida

O NotebookLM explicou que um arquivo CSV de chamados SOC pode ser analisado de duas formas principais:

1. Usando o módulo nativo `csv` do Python.
2. Usando a biblioteca `pandas`, que é mais indicada para análise de dados.

A resposta destacou que com pandas é possível carregar um arquivo com:

```python
import pandas as pd

df = pd.read_csv('chamados_soc.csv')
```

Depois disso, seria possível realizar análises como:

```python
criticos = df[df['Severidade'] == 'Crítica']
```

```python
print(df['Status'].value_counts())
```

Também foram citados conceitos como:

* DataFrame;
* seleção de colunas;
* filtros;
* contagem de registros;
* agrupamento com `groupby()`;
* tabelas dinâmicas;
* resumo estatístico com `describe()`.

### Fontes utilizadas na resposta

* Documentação oficial do módulo CSV do Python.
* Documentação oficial do pandas.

### Cicatriz / dificuldade encontrada

A resposta foi útil, mas trouxe alguns conceitos que podem ser avançados para iniciantes, como `pivot_table` e agrupamentos mais complexos. Para melhorar, seria necessário pedir uma versão ainda mais simples, focada apenas em leitura de CSV, filtros e contagens básicas.

---

## Prompt 4 — Métricas simples para SOC

### Prompt utilizado

```text
Sugira métricas simples que poderiam ser calculadas com Python em uma base fictícia de chamados SOC. Organize em tabela com: métrica, objetivo e exemplo de uso.
```

### Resposta obtida

O NotebookLM sugeriu métricas simples que podem ser calculadas com Python em uma base fictícia de chamados SOC.

| Métrica                  | Objetivo                                      | Exemplo de uso                             |
| ------------------------ | --------------------------------------------- | ------------------------------------------ |
| Volume por severidade    | Priorizar incidentes críticos e altos         | `df['Severidade'].value_counts()`          |
| Tempo médio de resposta  | Avaliar eficiência e SLA                      | `df['Tempo_Resposta'].mean()`              |
| Distribuição de status   | Ver chamados abertos, fechados e em andamento | `df['Status'].value_counts()`              |
| Volume por analista      | Monitorar carga de trabalho                   | `df.groupby('Analista').size()`            |
| Top 5 tipos de alerta    | Identificar alertas mais recorrentes          | `df['Tipo_Alerta'].value_counts().head(5)` |
| Resumo estatístico geral | Obter visão geral dos dados numéricos         | `df.describe()`                            |


### Fontes utilizadas na resposta

* Documentação oficial do pandas.
* Fonte sobre resposta a incidentes.

### Cicatriz / dificuldade encontrada

A resposta trouxe boas métricas, mas algumas exigem que a base de dados já esteja bem estruturada, com colunas como `Tempo_Resposta`, `Analista`, `Tipo_Alerta` e `Severidade`.

Para um projeto inicial, é melhor começar com uma base fictícia simples e evoluir aos poucos.

---

## Prompt 5 — Consolidação do miniguia

### Prompt utilizado

```text
Com base nas fontes carregadas e nas respostas anteriores, crie um miniguia de estudo sobre Python para Análise de Dados aplicada ao SOC. O material deve conter: resumo estruturado, glossário dos principais conceitos e prompts reutilizáveis para revisão futura.
```

### Resposta obtida

O NotebookLM gerou um miniguia consolidando os principais aprendizados sobre o uso de Python na rotina de SOC.

A resposta destacou que Python pode apoiar a ingestão de dados, limpeza, análise de incidentes, geração de métricas, relatórios e exportação de resultados.

Também foram apresentados conceitos como CSV, DataFrame, Series, indexação booleana, SLA, `value_counts()`, `groupby()` e `describe()`.

### Fontes utilizadas na resposta

* Documentação oficial do módulo CSV do Python.
* Documentação oficial do pandas.
* Fonte sobre resposta a incidentes.

### Cicatriz / dificuldade encontrada

O miniguia ficou útil, mas a parte de prompts reutilizáveis veio incompleta. Por isso, foi necessário complementar manualmente os prompts finais para que servissem como material de revisão e apoio para estudos futuros.


---

# Miniguia de Estudo

## 1. Python aplicado ao SOC

Python pode ser usado para automatizar e melhorar análises em uma rotina de SOC.

Em vez de analisar manualmente planilhas grandes de chamados, alertas ou logs, é possível usar Python para carregar os dados, filtrar informações importantes, calcular métricas e gerar relatórios.

Exemplos de uso:

* analisar chamados abertos;
* identificar incidentes críticos;
* calcular SLA;
* contar alertas por severidade;
* gerar relatórios operacionais;
* exportar resultados em CSV ou Excel.

---

## 2. Leitura de arquivos CSV

CSV é um formato muito usado para exportar dados de ferramentas de segurança, planilhas e sistemas de chamados.

Exemplo de base fictícia:

```text
id_chamado,status,severidade,categoria,sla
INC001,Aberto,Alta,Malware,85
INC002,Fechado,Baixa,Acesso,100
INC003,Aberto,Crítica,Phishing,70
```

Com Python, esses arquivos podem ser lidos usando o módulo `csv` ou a biblioteca `pandas`.

---

## 3. Uso do pandas

O pandas é uma biblioteca Python muito usada para análise de dados.

Com ela, é possível transformar um arquivo CSV em uma tabela chamada DataFrame.

Exemplo:

```python
import pandas as pd

df = pd.read_csv('chamados_soc.csv')
```

A partir disso, é possível realizar análises como:

```python
df['Status'].value_counts()
```

```python
df['Severidade'].value_counts()
```

```python
df[df['Severidade'] == 'Crítica']
```

---

## 4. Análises simples em SOC

Com uma base fictícia de chamados SOC, é possível analisar:

* total de chamados;
* chamados por status;
* chamados por severidade;
* chamados críticos;
* chamados fora do SLA;
* categorias mais recorrentes;
* volume por analista;
* tempo médio de resposta.

Essas análises ajudam a transformar dados operacionais em informação útil para tomada de decisão.

---

## 5. Cuidados com dados sensíveis

Projetos publicados no GitHub não devem conter dados reais de empresas ou clientes.

Não devem ser publicados:

* nomes reais de clientes;
* IPs internos;
* e-mails corporativos;
* credenciais;
* logs reais;
* prints de ferramentas internas;
* números reais de incidentes;
* dados confidenciais.

O ideal é usar bases fictícias, anonimizadas ou criadas apenas para estudo.


-------

---

# Glossário

## SOC

Centro de Operações de Segurança responsável por monitorar, analisar e responder eventos de segurança.

## Chamado

Registro de uma solicitação, incidente ou atividade operacional.

## Alerta

Evento gerado por uma ferramenta de segurança que pode indicar comportamento suspeito.

## SLA

Acordo de nível de serviço que define o prazo esperado para atendimento ou resolução.

## CSV

Formato de arquivo usado para armazenar dados em formato de tabela.

## Python

Linguagem de programação usada para automação, análise de dados e desenvolvimento de soluções.

## pandas

Biblioteca Python usada para análise e manipulação de dados.

## DataFrame

Estrutura do pandas parecida com uma tabela, composta por linhas e colunas.

## Series

Estrutura do pandas que representa uma única coluna de dados.

## Indexação Booleana

Técnica usada para filtrar dados com base em uma condição.

Exemplo:

```python
df[df['Severidade'] == 'Crítica']
```

## value_counts()

Função usada para contar a frequência dos valores de uma coluna.

## groupby()

Função usada para agrupar dados por uma ou mais colunas.

## describe()

Função usada para gerar um resumo estatístico dos dados.

---

# Prompts Reutilizáveis

## Prompt para entender um tema

```text
Com base nas fontes carregadas, explique este conteúdo com foco em análise de dados aplicada ao SOC.
```

## Prompt para gerar exemplos práticos

```text
Crie exemplos simples de como Python poderia ser usado para analisar dados fictícios de chamados SOC.
```

## Prompt para criar métricas

```text
Liste métricas que poderiam ser calculadas com Python em uma base CSV de chamados SOC. Organize em tabela com: métrica, objetivo e exemplo.
```

## Prompt para filtrar chamados críticos

```text
Explique como filtrar chamados críticos em uma base fictícia de SOC usando Python e pandas. Use linguagem simples para iniciante.
```

## Prompt para analisar volume operacional

```text
Explique como calcular o volume de chamados por status, severidade e categoria usando Python.
```

## Prompt para controle de SLA

```text
Explique como Python poderia ajudar a calcular e acompanhar SLA em uma base fictícia de chamados SOC.
```

## Prompt para proteção de dados sensíveis

```text
Quais informações de uma base SOC devem ser removidas ou anonimizadas antes de publicar um projeto no GitHub?
```

## Prompt para projeto de portfólio

```text
Transforme este aprendizado em uma ideia de projeto para GitHub usando Python, CSV e análise de chamados SOC fictícios.
```

---

# Ideia de Projeto Futuro

Como evolução deste estudo, pretendo desenvolver um projeto prático em Python com uma base fictícia de chamados SOC.

O projeto poderá conter:

* leitura de arquivo CSV;
* análise de chamados por status;
* análise por severidade;
* identificação de chamados fora do SLA;
* geração de resumo operacional;
* exportação de relatório;
* documentação no GitHub.

Nome sugerido para o projeto futuro:

**soc-ticket-analysis-python**

---

# Conclusão

Este projeto mostrou como o NotebookLM pode apoiar o aprendizado técnico quando usado com fontes confiáveis, bons prompts e pensamento crítico.

O principal aprendizado foi que Python pode ser uma ferramenta importante para transformar dados de SOC em informações úteis para análise, priorização e tomada de decisão.

Também ficou claro que projetos de segurança precisam ter cuidado com dados sensíveis. Por isso, qualquer base usada em estudos ou GitHub deve ser fictícia, anonimizada e segura para publicação.

Este miniguia servirá como base para meus próximos estudos em Python, pandas, SQL, automação e análise de dados aplicada à cibersegurança.


