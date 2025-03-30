# Atividade 02 - Curso Básico em Machine Learning
# Participante: Geovanne Pereira

# Questão 1: Função que retorna números ímpares de uma lista
def numeros_impares(lista):
    return [n for n in lista if n % 2 != 0]

# Questão 2: Função que retorna números primos de uma lista
def eh_primo(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def numeros_primos(lista):
    return [n for n in lista if eh_primo(n)]

# Questão 3: Função que retorna elementos exclusivos de cada lista
def elementos_exclusivos(lista1, lista2):
    return list(set(lista1) ^ set(lista2))

# Questão 4: Função para encontrar o segundo maior valor em uma lista
def segundo_maior(lista):
    lista_unica = list(set(lista))
    lista_unica.sort(reverse=True)
    return lista_unica[1] if len(lista_unica) >= 2 else None

# Questão 5: Ordenar lista de tuplas por nome
def ordenar_por_nome(lista):
    return sorted(lista, key=lambda x: x[0])

# Questão 6: Preenchendo código matplotlib
import matplotlib.pyplot as plt
import numpy as np

fig, axs = plt.subplots(ncols=2, nrows=2, figsize=(5.5, 3.5), layout="constrained")

for row in range(2):
    for col in range(2):
        axs[row, col].annotate(f'axs[{row}, {col}]', (0.5, 0.5),
                               transform=axs[row, col].transAxes,
                               ha='center', va='center', fontsize=18,
                               color='darkgrey')
fig.suptitle('plt.subplots()')

# Questão 7: Preenchendo código com matplotlib
import numpy as np
import matplotlib as mpl
import matplotlib.pyplot as plt

x = np.linspace(-2 * np.pi, 2 * np.pi, 100)
y = np.sin(x)

fig, ax = plt.subplots()
ax.plot(x, y)

# Questão 8: Ler CSV com pandas e exibir primeiras linhas
import pandas as pd

df = pd.read_csv('arquivo.csv')
print(df.head())

# Questão 9: Selecionar coluna e filtrar linhas por condição
coluna_filtrada = df[df['coluna'] > 10]['coluna']
print(coluna_filtrada)

# Questão 10: Lidar com valores ausentes (NaN)
df_sem_nan = df.dropna()  # Remove linhas com NaN
df_preenchido = df.fillna(0)  # Preenche NaN com 0
print(df_sem_nan.head())
print(df_preenchido.head())

