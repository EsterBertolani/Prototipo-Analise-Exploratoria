# Análise de Furtos e Roubos na Grande Vitória

Projeto desenvolvido para a disciplina **Projeto Integrador III**, com foco na análise preliminar de ocorrências de furtos e roubos na Região Metropolitana da Grande Vitória.

O objetivo principal do projeto é identificar padrões temporais nos registros de crimes contra o patrimônio, com ênfase na **hora de ocorrência**, utilizando técnicas de análise exploratória de dados e um modelo baseline inicial.

### Vídeo do projeto: [clique aqui]()

## Integrantes do grupo

* Alexsander Amorim Borchardt
* Ester da Silva Bertolani
* Larissa Moraes de Jesus
* Lucas Gonçalves Rufino de Souza
* Marcelo Henrique Fortaleza Mindas
* Vanderson de Almeida Alves


## Disciplina

**Projeto Integrador III**

- Curso: Ciência da Computação
- Professor: Howard Cruz Roatti
- Instituição: FAESA


## Tema do projeto

A criminalidade contra o patrimônio é um problema urbano relevante, pois afeta diretamente a segurança da população, a circulação nas cidades, o planejamento público e a sensação de segurança.

Neste projeto, o grupo analisa registros de **furtos e roubos** nos municípios da Grande Vitória, buscando responder perguntas como:

- Em quais horários ocorrem mais registros de furto e roubo?
- Existem diferenças entre os padrões horários de furtos e roubos?
- Quais municípios concentram mais ocorrências em números absolutos?
- Há variações por mês, dia da semana ou faixa horária?
- Um modelo simples consegue servir como referência inicial para previsão mensal de ocorrências?


## Recorte da análise

A análise considera o seguinte recorte:

- **Período:** 01/03/2021 até 30/04/2026
- **Região:** Grande Vitória
- **Municípios considerados:**
  - Vitória
  - Vila Velha
  - Serra
  - Cariacica
  - Viana
  - Guarapari
  - Fundão
- **Tipos de ocorrência:**
  - Furto
  - Roubo


## Base de dados

A base utilizada contém microdados de ocorrências criminais, com informações como:

- Data da ocorrência
- Hora da ocorrência
- Tipo de incidente
- Tipo de local
- Município
- Bairro

O arquivo principal utilizado no notebook é:

```text
MICRODADOS_OCORRENCIAS.csv
````

Caso ele não esteja acessível no repositório, será necessário baixá-lo novamente da fonte oficial utilizada: [SESP - Painel de Crimes contra o Patrimônio](https://sesp.es.gov.br/painel-de-crimes-contra-o-patrimonio), e adicioná-lo manualmente à pasta ´dados´ do projeto.

![Anexo](<Captura de tela 2026-05-05 191400.png>)

---

## Estrutura do projeto

(após limpeza das pastas)

```text
prototipo-analise-exploratoria/
│
├── dados/
│   └── MICRODADOS_OCORRENCIAS.csv
│
├── notebooks/
│   └── analise-furtos-roubos-gv.ipynb
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

## Tecnologias utilizadas

O projeto utiliza principalmente:

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook / Google Colab

Essas ferramentas foram utilizadas para:

* carregamento da base;
* tratamento dos dados;
* criação de variáveis temporais;
* análise exploratória;
* visualização dos dados;
* construção de um modelo baseline inicial.

---

## Como executar o projeto

### 1. Clonar o repositório

```bash
git clone https://github.com/EsterBertolani/Prototipo-Analise-Exploratoria
cd Prototipo-Analise-Exploratoria
```

---

### 2. Criar um ambiente virtual

No Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

No Linux/Mac:

```bash
python3 -m venv venv
source venv/bin/activate
```

---

### 3. Instalar as dependências

Execute:

```bash
pip install -r requirements.txt
```

---

### 4. Adicionar a base de dados

Coloque o arquivo:

```text
MICRODADOS_OCORRENCIAS.csv
```

dentro da pasta:

```text
dados/
```

Caso o notebook esteja procurando o arquivo em outro caminho, ajuste a variável responsável pelo caminho do CSV na sessão ´Carregamento dos dados´.

Exemplo:

```python
dados = pd.read_csv("../dados/MICRODADOS_OCORRENCIAS.csv", sep=';', encoding='latin-1')
```

---

### 5. Abrir o notebook

Para abrir localmente com Jupyter Notebook:

```bash
jupyter notebook
```

Depois, acesse a pasta `notebooks/` e abra o arquivo:

```text
analise-furtos-roubos-gv.ipynb
```

Também é possível executar o projeto no **Google Colab**, fazendo upload do notebook e do arquivo CSV.

---

## Etapas realizadas no notebook

O notebook da Entrega 2 está organizado nas seguintes etapas:

### 1. Introdução

Apresenta o contexto do projeto, o problema analisado e o objetivo da Entrega 2.

### 2. Bibliotecas utilizadas

Importa as bibliotecas necessárias para carregamento, tratamento, visualização e modelagem inicial.

### 3. Carregamento dos dados

Realiza a leitura da base de ocorrências e verifica se o arquivo foi carregado corretamente.

### 4. Visualização inicial da base

Exibe informações gerais da base, como quantidade de linhas, colunas, tipos de dados e primeiros registros.

### 5. Tratamento inicial dos dados

Inclui etapas como:

* padronização de textos;
* conversão da coluna de data;
* tratamento da coluna de hora;
* identificação de horários inválidos ou indeterminados.

### 6. Filtragem do escopo do projeto

Aplica os filtros definidos para a análise:

* período de 01/03/2021 até 30/04/2026;
* municípios da Grande Vitória;
* ocorrências relacionadas a furto e roubo.

### 7. Criação de variáveis temporais

Cria novas variáveis para apoiar a análise:

* ano;
* mês;
* ano/mês;
* dia da semana;
* hora do dia;
* faixa horária;
* categoria do crime.

### 8. Análise exploratória

Gera gráficos para investigar padrões nos dados, incluindo:

* ocorrências por tipo de crime;
* ocorrências por município;
* evolução mensal;
* distribuição por mês do ano;
* distribuição por dia da semana;
* distribuição por hora do dia;
* comparação entre furto e roubo por hora;
* heatmap de hora por dia da semana.

### 9. Modelo baseline

Implementa um modelo inicial simples para previsão da quantidade mensal de ocorrências.

O baseline serve como referência mínima para comparação com modelos mais robustos na próxima etapa do projeto.

As métricas utilizadas incluem:

* MAE;
* RMSE.

### 10. Principais análises realizadas

Entre as análises desenvolvidas nesta entrega, destacam-se:

* comparação entre furtos e roubos;
* distribuição das ocorrências por município;
* análise da evolução mensal;
* análise por dia da semana;
* análise por hora do dia;
* comparação dos horários de ocorrência entre furto e roubo;
* identificação de combinações relevantes entre dia da semana e horário;
* criação de um baseline simples de previsão mensal.

---

## Observações metodológicas

Alguns cuidados foram considerados durante a análise:

* Os dados representam registros oficiais, portanto podem existir casos não notificados.
* Registros com horário indeterminado foram mantidos na base geral, mas não utilizados nas análises específicas por hora.
* A comparação entre municípios foi feita em números absolutos, sem normalização por população.
* A análise atual é preliminar e tem caráter exploratório.
* O baseline inicial não representa o modelo final, servindo apenas como referência de comparação.

---

## Status do projeto

Projeto em desenvolvimento.

A versão atual corresponde à **Entrega 2**, com foco em análise exploratória, visualização dos dados e construção de um modelo baseline inicial.

````
