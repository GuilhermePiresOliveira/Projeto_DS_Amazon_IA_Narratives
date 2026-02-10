# 📊 Análise de Vendas Amazon: Insights de Negócio com NLP & Python

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=for-the-badge&logo=pandas)
![NLP](https://img.shields.io/badge/NLP-WordCloud_%26_AI-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Concluído-success?style=for-the-badge)

## 🎯 O Desafio de Negócio
Este projeto simula um cenário real de **E-commerce Analytics**. O objetivo foi analisar dados de vendas da Amazon para responder a perguntas estratégicas:

> *"O preço influencia na satisfação do cliente? Produtos mais caros recebem melhores avaliações?"*
> *"O que realmente faz um cliente dar 5 estrelas para um produto?"*

Durante a análise, descobrimos que os métodos estatísticos tradicionais não eram suficientes, exigindo uma abordagem criativa com **Processamento de Linguagem Natural (NLP)** para extrair valor dos textos dos reviews.

---

## 🛠️ Stack Tecnológico
* **Linguagem:** Python
* **Manipulação de Dados:** Pandas, NumPy
* **Visualização:** Matplotlib, Seaborn
* **Processamento de Texto (NLP):** WordCloud, Transformers (Hugging Face - BART/T5)
* **Ambiente:** Google Colab / Jupyter Notebook

---

## 🚀 A Jornada dos Dados (Pipeline)

### 1. Engenharia de Dados (ETL & Limpeza)
O dataset bruto apresentava desafios como moedas estrangeiras (Rúpia Indiana - ₹) e formatação inconsistente.
* **Limpeza:** Remoção de símbolos de moeda e conversão de strings para `float`.
* **Conversão Cambial:** Transformação dos valores de Rúpia para Real (BRL) para contextualizar a análise.

```python
# Exemplo do tratamento de dados
def limpar_moeda(valor):
    valor = str(valor).replace('₹', '').replace(',', '').strip()
    return float(valor)

df['preco_convertido'] = df['discounted_price'].apply(limpar_moeda) * 0.06 # Cotação BRL
