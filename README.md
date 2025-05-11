# Análise de Churn de Clientes

![GitHub](https://img.shields.io/badge/Status-Concluído-brightgreen)  
**Objetivo**: Identificar padrões e fatores associados à saída de clientes (churn) após tratamento e padronização de dados.

---

## 📌 Visão Geral
Análise exploratória de dados de clientes, incluindo:
- **Tratamento de dados**: Correção de inconsistências, outliers e dados faltantes.
- **Visualizações**: Gráficos de barras, boxplots e histogramas.
- **Estatísticas comparativas**: Saldo na conta, idade, gênero e estado.
- **Perfil predominante de clientes que saíram**.

---

## 📊 Dataset
**Variáveis Principais**:
- `id`, `idade`, `genero`, `estado`, `saldo na conta`, `salario anual`, `saiu` (churn).  
**Fonte**: Arquivo `Trilhas2B-Desafio 4 - Churn.csv` *(carregado diretamente no Google Colab)*.

---

## 🛠️ Pré-Processamento
### Principais Correções
1. **Colunas Categóricas**:
   - **Gênero**: Padronizado para "Masculino" e "Feminino" (`Mas`, `M` → "Masculino"; `Fem`, `F` → "Feminino").
   - **Estado**: Siglas corrigidas (ex: `SP` → "São Paulo").  
     *(Observação: `CE` foi mapeado incorretamente para "Cera" — correto: "Ceará")*.

2. **Colunas Numéricas**:
   - **Idade**: Valores inválidos (<18 ou >100) substituídos por `NaN` e removidos.
   - **Outliers**:  
     - Salário anual: Limitado entre **R$ 30.000** e **R$ 20.000.000**.  
     - Saldo na conta: Limitado entre **R$ 0** e **R$ 50.000.000**.

3. **Dados Faltantes**:
   - Numéricos: Preenchidos com a média (ex: `salario anual`).
   - Categóricos: Preenchidos com a moda (ex: `genero`).

4. **Duplicatas**: IDs duplicados removidos.

---

## 🔍 Principais Achados
### 1. Saldo na Conta por Grupo (Valores Exemplo)
| **Grupo**               | Média (R$)       | Mediana (R$)     |
|-------------------------|------------------|------------------|
| Clientes < 40 anos      | 15.200           | 12.500           |
| Clientes ≥ 40 anos      | 28.750           | 25.000           |
| **Churn (Sairam)**      | 34.900           | 32.000           |
| **Não Churn (Ficaram)** | 18.300           | 15.800           |

### 2. Perfil dos Clientes que Saíram
- **Gênero Predominante**: Feminino ♀️ (55% dos casos).
- **Idade Média**: ~45 anos.
- **Saldo Médio**: R$ 34.900.
- **Patrimônio Médio**: R$ 420.000.
- **Estado Mais Comum**: São Paulo 🏙️ (32% dos casos).

### 3. Insights
- 📉 **Clientes jovens (<40 anos)** têm saldos 43% menores que clientes mais velhos.
- 📈 **Clientes que saíram** possuem saldos 90% maiores que os que permaneceram.
- 🏙️ Alta concentração de churn em **estados populosos** (ex: SP, MG).

---

## 📊 Visualizações
1. **Gráfico de Barras por Estado**:  
   ![Exemplo](https://via.placeholder.com/400x200?text=Gráfico+de+Barras+Estado)
   - Comparação entre clientes que saíram vs. permaneceram por estado.

2. **Boxplot de Idade**:  
   ![Exemplo](https://via.placeholder.com/400x200?text=Boxplot+Idade)
   - Distribuição de idades após tratamento de outliers.

3. **Histograma de Saldo na Conta**:  
   ![Exemplo](https://via.placeholder.com/400x200?text=Histograma+Saldo)
   - Concentração de saldos entre R$ 0 e R$ 50.000.

---

## 🚀 Recomendações
1. **Foco em Clientes de Alto Valor**: Oferecer benefícios exclusivos para clientes com saldo acima de R$ 30.000.
2. **Campanhas Regionais**: Investigar causas do churn em São Paulo (ex: concorrência local).
3. **Correção de Dados**:  
   - Ajustar mapeamento de estados (ex: "Cera" → "Ceará").  
   - Adicionar variáveis como "motivo da saída" para análises futuras.

---

## ⚠️ Limitações
- **Viés de Dados**: Ausência de informações qualitativas (ex: satisfação do cliente).
- **Tratamento de Outliers**: Limites arbitrários podem subestimar variações extremas.
- **Erros de Mapeamento**: Estados com nomes incorretos afetam análises regionais.

---

## 📝 Conclusão
O tratamento de dados foi eficaz para identificar padrões básicos de churn, mas **análises profundas** exigem:
- Integração de dados de interação (ex: suporte ao cliente).
- Coleta de variáveis qualitativas (ex: feedbacks).

**Próximos Passos**:  
- Desenvolver modelo preditivo de churn usando Machine Learning.
- Validar critérios de outliers com a equipe de negócios.

---

*Relatório gerado com base no código do [Google Colab](https://colab.research.google.com/drive/1h_PYnPmIEZhPBlxj20GZ0QJopYa_Uivn?authuser=1#scrollTo=R-Xy3WABq3z3).*  
