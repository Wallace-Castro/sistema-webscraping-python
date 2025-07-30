# 📊 Análise de Sentimentos de Reviews do IMDb com Python

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=Jupyter&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=Selenium&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

> Um script em Python, desenvolvido em um Jupyter Notebook, que automatiza a coleta de reviews de filmes do site IMDb e realiza uma análise de sentimentos para classificar as opiniões.


## 📖 Sobre o Projeto

Este projeto tem como objetivo extrair dados de opiniões públicas de uma fonte online e transformá-los em insights quantificáveis. Para este exemplo, o script foca em coletar as reviews do filme **"Jogador Nº 1"** (tt1677720) do site IMDb.

O processo é dividido em duas etapas principais:
1.  **Web Scraping:** Utiliza o Selenium para navegar dinamicamente na página usando o **Microsoft Edge**, carregar todas as reviews e revelar textos ocultos (spoilers).
2.  **Análise de Sentimentos:** Utiliza a biblioteca NLTK para processar o texto de cada review e classificá-lo como positivo, negativo ou neutro, apresentando a contagem final.

---

## 🤖 Fluxo de Trabalho do Script

O notebook está estruturado para executar as seguintes ações em sequência:

1.  **Configuração do Ambiente:** A primeira célula instala todas as bibliotecas necessárias (`selenium`, `webdriver-manager`, `nltk`, `pandas`) e faz o download do léxico `vader` do NLTK.

2.  **Coleta de Dados Dinâmica:**
    - O **Selenium** abre um navegador **Microsoft Edge** e acessa a página de reviews do IMDb.
    - Ele simula o comportamento humano clicando repetidamente no botão "Load More" até que todas as reviews da página sejam carregadas.
    - Em seguida, ele clica em todos os botões de "spoiler" para garantir que o texto completo das reviews seja visível no HTML.

3.  **Extração e Estruturação:**
    - O HTML completo da página é passado para o **BeautifulSoup** para ser parseado.
    - O título e o texto de cada review são extraídos e organizados em um **DataFrame do Pandas**.

4.  **Análise e Contagem:**
    - A função `SentimentIntensityAnalyzer` do **NLTK** é aplicada a cada review para gerar um "compound score" (de -1 a 1).
    - Com base nesse score, cada review é classificada como "Positivo", "Negativo" ou "Neutro".
    - Ao final, o script exibe o DataFrame com as análises e a contagem total de reviews para cada categoria de sentimento.

## 🛠️ Bibliotecas Utilizadas

- **[Selenium](https://www.selenium.dev/):** Para automação de navegador e scraping de conteúdo dinâmico.
- **[BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/bs4/doc/):** Para parsing de HTML.
- **[NLTK (Natural Language Toolkit)](https://www.nltk.org/):** Para análise de sentimentos.
- **[Pandas](https://pandas.pydata.org/):** Para manipulação e estruturação de dados.
- **[Webdriver-Manager](https://pypi.org/project/webdriver-manager/):** Para gerenciar o driver do navegador de forma automática.

---

## 👨‍💻 Autor

Desenvolvido por **Wallace Castro de Oliveira**.
