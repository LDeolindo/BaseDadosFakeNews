# Base de Dados de Fake News

Versão em Português | [English Version](README.en.md)

## Descrição 

A Base de Dados com reivindicações de Fake News é um projeto desenvolvido para o Trabalho de Conclusão de Curso (TCC) intitulado "Criação de uma Base de Dados de Fake News". Essa base de dados foi desenvolvida a partir de sites de checagem de fatos no idioma português, fornecendo informações relevantes e categorizadas. 

## Método de Pesquisa

O projeto seguiu o seguinte método de pesquisa, composto pelas seguintes etapas:

![Metodo do Projeto](metodologia_claro.png)


## Origem e Coleta

A base de dados foi construída a partir da coleta de informações de sites de checagem de fatos. As fontes utilizadas foram:

- **Aos Fatos**: Site de verificação de fatos brasileiro. Mais informações disponíveis em: [Aos Fatos](https://www.aosfatos.org/quem-somos/).
- **E-farsas**: Site brasileiro de verificação de boatos e notícias falsas. Mais informações disponíveis em: [E-farsas](https://www.e-farsas.com/sobre/).

A coleta de dados foi realizada até 25/06/2023, contendo registros que vão do período de 02/04/2002 até 23/06/2023, abrangendo uma ampla variedade de reivindicações de notícias classificadas como `Falso`, `Verdadeiro` e `Distorcido` em diferentes áreas e tópicos. E inclui as variáveis de identificação e categorização necessárias.

## Descrição da Base

A Base de Dados de Reivindicações de Fake News inclui 5397 registro, contendo as seguintes informações (15 colunas):

- `load_date`: Data em que foi feita a coleta;
- `site_ranking`: Classificação da reivindicação de acordo com o site;
- `site_name`: Fonte original da reivindicação;
- `url`: URL do site onde foi coletada a reivindicação;
- `site_language`: Idioma do site onde foi realizada a coleta;
- `site_content_url`: URL para a reivindicação original;
- `site_url`: Link do site onde foi realizada a raspagem;
- `site_date_published`: Data em que a reivindicação foi publicada;
- `title`: Título da reivindicação;
- `description`: Descrição da reivindicação;
- `keywords`: Palavras-chave da reivindicação;
- `tag`: Rótulo da reivindicação;
- `claim_reviewed`: Reivindicação revisada;
- `review_body`: Corpo da revisão;
- `claim`: Reivindicação.

Das classificações, foram escolhidas trabalhar com reivindicações que fossem: **Verdadeiro**, **Falso** e **Distorcido**. Como pode ser observado, foram coletadas:

- **Verdadeiro**: 550;
- **Falso**: 4802;
- **Distorcido**: 45.


## Formato

O conjunto de dados está disponível em formato CSV e pode ser baixado [aqui](dados/filtrados/refined_dataset/dataset.csv).

## Processamento

Os seguintes passos de processamento foram aplicados ao conjunto de dados:

- **Aos Fatos**:
  1. Limpeza de dados: Remoção de caracteres especiais e da sequência de caracteres ` \| Aos Fatos`;
  2. Normalização: Conversão da coluna `site_date_published` para o formato de data e hora.
- **E-farsas**:
  1. Limpeza de dados: Remoção de caracteres especiais e da sequência de caracteres `- Publicidade -`;
  2. Normalização: Conversão da coluna `site_date_published` para o formato de data e hora.

## Licença e Termos de Uso

A Base de Dados de Fake News é fornecida para fins acadêmicos e de pesquisa. Você é livre para utilizar os dados, desde que cite a fonte original e faça referência ao trabalho de TCC "Criação de uma Base de Dados de Fake News". Consulte o arquivo de licença para mais informações.

## Exemplos de Uso

Aqui está um exemplo de como acessar e utilizar a base de dados em Python:

```python
import pandas as pd

# Carregar a base de dados
data = pd.read_csv('base_de_dados.csv')

# Exibir as primeiras linhas da base de dados
print(data.head())
