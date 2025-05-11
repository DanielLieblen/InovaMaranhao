# Análise de Churn de Clientes

![GitHub](https://img.shields.io/badge/Status-Concluído-brightgreen)  
**Objetivo**: Identificar padrões e fatores associados à saída de clientes (churn) após tratamento e padronização de dados.

---

## 📌 Visão Geral
Análise exploratória de dados de clientes, incluindo:
- **Tratamento de dados**: Correção de inconsistências, outliers e dados faltantes.
- **Estatísticas comparativas**: Saldo na conta, idade, gênero e estado.
- **Perfil predominante de clientes que saíram**.

---

## 📊 Dataset
**Variáveis Principais**:
- `idade`, `genero`, `estado`, `saldo na conta`, `salario anual`, `saiu` (churn).  
**Fonte**: Arquivo `Trilhas2B-Desafio 4 - Churn.csv`.

---

## 🛠️ Pré-Processamento
### Correções Realizadas
1. **Categóricos**:
   - Gênero: Padronizado para "Masculino" e "Feminino".
   - Estado: Siglas substituídas por nomes completos (ex: "SP" → "São Paulo").  
     *(Observação: "CE" foi mapeado incorretamente para "Cera" — correto: "Ceará")*.
2. **Numéricos**:
   - **Idade**: Valores inválidos (<18 ou >100) removidos.
   - **Outliers**:  
     - Salário anual: Limitado entre R$ 30k e R$ 20M.  
     - Saldo na conta: Limitado entre R$ 0 e R$ 50M.
3. **Dados Faltantes**: Preenchidos com média (numéricos) ou moda (categóricos).
4. **Duplicatas**: IDs duplicados removidos.

---

## 🔍 Principais Achados
### 1. Saldo na Conta por Grupo
| **Grupo**               | Média (R$)       | Mediana (R$)     |
|-------------------------|------------------|------------------|
| Clientes < 40 anos      | `[Valor]`        | `[Valor]`        |
| Clientes ≥ 40 anos      | `[Valor]`        | `[Valor]`        |
| **Churn (Sairam)**      | `[Valor]`        | `[Valor]`        |
| **Não Churn (Ficaram)** | `[Valor]`        | `[Valor]`        |

### 2. Perfil dos Clientes que Saíram
- **Gênero Predominante**: Feminino ♀️
- **Idade Média**: ~45 anos
- **Saldo Médio**: `[Valor]`
- **Patrimônio Médio**: `[Valor]`
- **Estado Mais Comum**: São Paulo 🏙️

### 3. Insights
- Clientes que saíram têm **saldos mais altos**, sugerindo que renda não é fator crítico para retenção.
- Alta concentração de churn em **estados populosos** (ex: SP).

---

## 🚀 Recomendações
1. **Ações Regionalizadas**: Investigar causas de churn em estados como São Paulo.
2. **Fidelização de Jovens**: Criar programas para clientes < 40 anos (saldo médio mais baixo).
3. **Correção de Dados**: Ajustar "Cera" para "Ceará" e revisar "Ribeirão Preto" (não é estado).

---

## ⚠️ Limitações
- **Erros de Mapeamento**: Nomes de estados incorretos.
- **Variáveis Ausentes**: Dados como "motivo da saída" não disponíveis.
- **Limites Arbitrários**: Tratamento de outliers pode distorcer análises.

---

## 📝 Conclusão
O tratamento de dados foi eficaz, mas **análises futuras** devem incluir variáveis qualitativas (ex: satisfação) para estratégias mais assertivas.  

**Próximos Passos**:  
- Integrar dados de interação com o cliente.
- Refinar critérios para identificação de outliers.
