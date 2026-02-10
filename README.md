# 📊 Amazon Sales Analysis: NLP & Business Insights

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=for-the-badge&logo=pandas)
![NLP](https://img.shields.io/badge/NLP-WordCloud_%26_Transformers-green?style=for-the-badge)

## 🎯 O Desafio de Negócio
O objetivo deste projeto foi analisar dados reais de vendas da Amazon para responder a uma pergunta crucial de marketing:
> *"O preço alto garante uma avaliação de 5 estrelas? E o que realmente motiva o cliente a elogiar um produto?"*

Ao longo da análise, descobrimos que os métodos estatísticos tradicionais não eram suficientes, exigindo uma abordagem criativa com **Processamento de Linguagem Natural (NLP)**.

---

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Manipulação de Dados:** Pandas, NumPy
* **Visualização:** Matplotlib, Seaborn
* **NLP (Texto):** WordCloud, Transformers (Hugging Face - BART/T5)

---

## 🚀 Passo a Passo do Projeto

### 1. Engenharia de Dados (Data Cleaning)
O dataset bruto continha moedas em Rúpia Indiana (₹) e strings sujas. O primeiro passo foi limpar e converter para Real (BRL).

```python
# Exemplo de limpeza e conversão
def limpar_moeda(valor):
    if isinstance(valor, str):
        valor = valor.replace('₹', '').replace(',', '').strip()
    return float(valor)

# Convertendo Rúpia para Real (Cotação Ex: 0.06)
df['preco_convertido'] = df['discounted_price'].apply(limpar_moeda) * 0.06
