# ✨💻 **Análise de Dados com Python** ✨💻

Este projeto consiste em realizar uma análise de dados de clientes utilizando Python. O objetivo é identificar o perfil ideal de cliente com base em um histórico de compras, utilizando a biblioteca pandas. O projeto segue as seguintes etapas:

## Passo 1️⃣: Importação da base de dados

```python
import pandas as pd

tabela = pd.read_csv("clientes.csv", encoding="latin", sep=";")

# deletar a coluna inútil
tabela = tabela.drop("Unnamed: 8", axis=1)
```

## Passo 2️⃣: Visualização da base de dados

```python
display(tabela)
```

## Passo 3️⃣: Tratamento da base de dados

```python
# Correção de valores no formato errado
tabela["Salário Anual (R$)"] = pd.to_numeric(tabela["Salário Anual (R$)"], errors="coerce")

# Remoção de valores vazios
tabela = tabela.dropna()

print(tabela.info())
```

## Passo 4️⃣: Análise inicial - Notas dos clientes

```python
display(tabela.describe())
```

## Passo 5️⃣: Análise completa - Perfil ideal de cliente

```python
import plotly.express as px

# Análise de características que podem impactar na nota dos clientes
for coluna in tabela.columns:
    grafico = px.histogram(tabela, x=coluna, y="Nota (1-100)", histfunc="avg", text_auto=True, nbins=10)
    grafico.show()
```

## Análise 📈

A partir da análise dos dados, podemos identificar o perfil ideal de cliente:

- Profissão: Áreas de trabalho como Entretenimento e Artística são preferíveis (evitar área de construção).
- Idade: Clientes com mais de 10 anos.
- Renda: O salário não parece fazer uma diferença significativa na nota dos clientes.
- Experiência de trabalho: Entre 10 e 15 anos.
- Tamanho da família: Famílias de até 7 pessoas.

## Observações Finais 📝

Este projeto utiliza Python para realizar uma análise de dados visando identificar o perfil ideal de cliente com base no histórico de compras. As informações obtidas podem auxiliar na tomada de decisões para aumentar o faturamento e o lucro da empresa.

**Nota**: É importante ressaltar que este projeto é apenas um exemplo educacional e os resultados obtidos podem variar de acordo com a natureza dos dados e o contexto específico do negócio.

Feito com ♥ por Anderson Leite 👋 [Entre em contato!](https://www.linkedin.com/in/andersondiasleite/)
