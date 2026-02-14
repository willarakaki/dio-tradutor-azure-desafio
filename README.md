# Azure AI Toolkit: Tradutor de Documentos e Artigos

Este repositório contém um conjunto de ferramentas robustas para automatizar a tradução de conteúdos, combinando serviços de IA especializados e modelos de linguagem de larga escala (LLMs). O projeto foi desenvolvido como parte do treinamento para a certificação **Microsoft AI-102** através do Bootcamp na DIO.

---

## Funcionalidades Principais

O toolkit está estruturado em dois módulos complementares:

1.  **Módulo Translator (Documentos Word):**
    * Focado em tradução técnica de arquivos `.docx`.
    * Preserva a estrutura original de parágrafos.
    * Otimizado para evitar o processamento de linhas vazias.

2.  **Módulo OpenAI (Artigos Web):**
    * **Web Scraping:** Extração automática de texto limpo de URLs usando `BeautifulSoup`.
    * **Tradução Contextual:** Utiliza o modelo `4o-mini` (ou similar) via Azure OpenAI para traduções que compreendem o contexto do artigo.
    * **Saída Formatada:** Retorno direto em formato Markdown para facilitar a publicação.

---

## Stack Tecnológica

* **Linguagem:** Python 3.x
* **Serviços de Nuvem (Azure):**
    * `Azure AI Translator`: Tradução neural de alta performance.
    * `Azure OpenAI Service`: Modelos generativos para tradução contextualizada.
* **Bibliotecas de Integração:**
    * `LangChain`: Orquestração de prompts e modelos de chat.
    * `BeautifulSoup4`: Limpeza e extração de dados HTML.
    * `python-docx`: Manipulação estruturada de arquivos Word.

---

## Configuração e Uso

### 1. Pré-requisitos
O projeto foi otimizado para execução no **Google Colab**. Para que funcione, você deve configurar os "Secrets" (ícone da chave 🔑) com as seguintes variáveis:

* `TLT_SUBSCRIPTION_KEY`: Sua chave de recurso do Azure Translator.
* `OPENAI_AZURE_KEY`: Sua chave de recurso do Azure OpenAI.

### 2. Fluxo de Trabalho



#### **Tradução de Arquivos Locais**
Basta carregar o arquivo no ambiente do Colab e executar:
```python
input_file = "/content/NOME_DO_ARQUIVO.docx"
translate_document(input_file)
