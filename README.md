# agrinho-sustentavel-
analise de dados dentro da agricultura sustentavel 
import pandas as pd
import matplotlib.pyplot as plt

# Dados de exemplo
dados = {
    "Propriedade": ["Fazenda A", "Fazenda B", "Fazenda C", "Fazenda D"],
    "Produção (ton)": [120, 150, 100, 180],
    "Consumo de Água (m³)": [5000, 8000, 4500, 9000],
    "Uso de Fertilizante (kg)": [300, 450, 250, 500]
}

df = pd.DataFrame(dados)

# Indicador de eficiência hídrica
df["Eficiência Hídrica"] = df["Produção (ton)"] / df["Consumo de Água (m³)"]

# Indicador de sustentabilidade
df["Índice Sustentável"] = (
    df["Produção (ton)"] /
    (df["Consumo de Água (m³)"] + df["Uso de Fertilizante (kg)"])
)

print("=== RELATÓRIO DE AGRICULTURA SUSTENTÁVEL ===")
print(df)

# Gráfico
plt.figure(figsize=(8,5))
plt.bar(df["Propriedade"], df["Índice Sustentável"], color="green")
plt.title("Índice de Sustentabilidade por Propriedade")
plt.xlabel("Propriedade")
plt.ylabel("Índice")
plt.grid(axis="y", linestyle="--", alpha=0.5)

plt.show()
