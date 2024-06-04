# Projeto de Análise de Dados
Este projeto visa analisar dados de produtividade de uma equipe, realizando cálculos e gerando gráficos que auxiliam na visualização do desempenho em termos de horas trabalhadas, bugs corrigidos, tarefas concluídas e produtividade diária.

# Tecnologias Utilizadas
Python  
Pandas  
Numpy  
Matplotlib  
Google Colab  

# Instalação
Para rodar este projeto, você precisará ter o Python instalado em sua máquina, além das bibliotecas pandas, numpy e matplotlib. Você pode instalá-las utilizando pip:

```sh
$ pip install pandas numpy matplotlib
```

# Como Executar
Clone o repositório para sua máquina local.
Abra o arquivo .ipynb no Google Colab ou em seu Jupyter Notebook.
Execute o notebook para gerar os cálculos e gráficos.

# Código

```sh
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

dados = pd.read_csv('https://raw.githubusercontent.com/ysmaelmarks/projeto3_SNSeg_SENAC-/main/dados.csv')
df = pd.DataFrame(dados)

# Total de Horas Trabalhadas
horasTrabalhadas = df['Horas Trabalhadas'].sum()
print(f'Horas trabalhadas: {horasTrabalhadas}')

# Média Diária de Horas Trabalhadas
mediaHorasTrabalhadas = df['Horas Trabalhadas'].mean()
print(f'Média diária de: {mediaHorasTrabalhadas:.2f} horas')

# Total de Bugs Corrigidos
bugsCorrigidos = df['Bugs Corrigidos'].sum()
print(f'Bugs corrigidos: {bugsCorrigidos}')

# Média Diária de Bugs Corrigidos
print(f'Bugs corrigidos: {bugsCorrigidos/7:.1f}')

# Total de Tarefas Concluídas
tarefasConcluidas = df['Tarefas Concluídas'].sum()
print(f'Tarefas concluídas: {tarefasConcluidas}')

# Média Diária de Tarefas Concluídas
mediaTarefasConcluidas = df['Tarefas Concluídas'].mean()
print(f'Média diária de: {mediaTarefasConcluidas:.1f} tarefas concluídas')

# Produtividade Diária
produtividade = tarefasConcluidas / horasTrabalhadas
print(f'Produtividade diária de: {produtividade:.1f} tarefas concluídas por hora')

```

# Códigos dos Gráficos

## Horas Trabalhadas

```sh
plt.figure(figsize=(10, 6))
plt.plot(df.index, df['Horas Trabalhadas'], marker='o')
plt.title('Horas Trabalhadas')
plt.xlabel('Índice')
plt.ylabel('Horas Trabalhadas')
plt.grid(True)
plt.show()
```

## Bugs Corrigidos

```sh
plt.figure(figsize=(10, 6))
plt.plot(df.index, df['Horas Trabalhadas'], marker='o')
plt.title('Horas Trabalhadas')
plt.xlabel('Índice')
plt.ylabel('Horas Trabalhadas')
plt.grid(True)
plt.show()
```

## Gráfico de Tarefas Concluídas

```sh
plt.figure(figsize=(10, 6))
plt.plot(df.index, df['Tarefas Concluídas'], marker='s', color='g')
plt.title('Tarefas Concluídas')
plt.xlabel('Índice')
plt.ylabel('Tarefas Concluídas')
plt.grid(True)
plt.show()
```

## Gráfico de Produtividade Diária

```sh
df['Produtividade'] = df['Tarefas Concluídas'] / df['Horas Trabalhadas']
plt.figure(figsize=(10, 6))
plt.plot(df.index, df['Produtividade'], marker='d', color='m')
plt.title('Produtividade Diária')
plt.xlabel('Índice')
plt.ylabel('Tarefas Concluídas por Hora')
plt.grid(True)
plt.show()
```

# Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para enviar um pull request ou abrir uma issue para discutir o que você gostaria de mudar.
