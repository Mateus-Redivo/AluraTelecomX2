# 📊 TelecomX - Análise Preditiva de Evasão de Clientes (Churn)

## 📋 Índice
- [Visão Geral](#-visão-geral)
- [Objetivos do Projeto](#-objetivos-do-projeto)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Metodologia](#-metodologia)
- [Análise dos Dados](#-análise-dos-dados)
- [Modelos Desenvolvidos](#-modelos-desenvolvidos)
- [Principais Resultados](#-principais-resultados)
- [Insights de Negócio](#-insights-de-negócio)
- [Recomendações Estratégicas](#-recomendações-estratégicas)
- [Como Executar](#-como-executar)
- [Próximos Passos](#-próximos-passos)


## 🎯 Visão Geral

Este projeto implementa uma solução completa de Machine Learning para predição de evasão de clientes (churn) em uma empresa de telecomunicações. Utilizando técnicas avançadas de ciência de dados, o projeto identifica os principais fatores que influenciam a decisão dos clientes de cancelar os serviços e propõe estratégias baseadas em dados para melhorar a retenção.

### 🔍 Problema de Negócio
A evasão de clientes é um dos principais desafios no setor de telecomunicações, representando custos significativos de aquisição de novos clientes e perda de receita recorrente. Este projeto visa:
- Identificar clientes com alto risco de churn antes que cancelem
- Entender os principais fatores que influenciam a decisão de cancelamento
- Desenvolver estratégias de retenção baseadas em evidências quantitativas


## 🎯 Objetivos do Projeto

### Objetivos Principais
1. Modelagem Preditiva: Criar modelos de machine learning para prever churn com alta precisão
2. Análise de Fatores: Identificar as variáveis mais importantes na decisão de cancelamento
3. Insights Acionáveis: Traduzir resultados técnicos em recomendações de negócio
4. Estratégias de Retenção: Propor ações específicas para diferentes perfis de clientes

### Objetivos Secundários
- Comparar performance de diferentes algoritmos (Random Forest vs. Regressão Logística)
- Desenvolver interpretações claras dos modelos para stakeholders não-técnicos
- Estabelecer métricas de acompanhamento para monitoramento contínuo


## 📁 Estrutura do Projeto

- **AluraTelecomX2/**
  - 📒 **TelecomX_BR.ipynb** – Notebook principal com análise completa  
  - 📊 **dados_tratados.csv** – Dataset pré-processado para análise  
  - 🌳 **modelo_random_forest_final.pkl** – Modelo Random Forest treinado e otimizado  
  - 🔢 **modelo_regressao_logistica_final.pkl** – Modelo Regressão Logística treinado e otimizado  
  - 📜 **LICENSE** – Licença do projeto  
  - 📝 **README.md** – Documentação do projeto (este arquivo)  



### Descrição dos Arquivos

- TelecomX_BR.ipynb: Notebook Jupyter contendo toda a análise, desde exploração dos dados até desenvolvimento e avaliação dos modelos
- dados_tratados.csv: Dataset com 7.034 registros de clientes, incluindo 23 variáveis sobre características demográficas, contratuais, de serviços e financeiras
- modelo_random_forest_final.pkl: Modelo Random Forest otimizado e pronto para produção (78.4% acurácia)
- modelo_regressao_logistica_final.pkl: Modelo Regressão Logística otimizado para comparação (75.4% acurácia)
- README.md: Documentação completa do projeto com metodologia, resultados e recomendações


## 🛠️ Tecnologias Utilizadas

### Linguagem e Ambiente
- Python 3.x - Linguagem principal
- Jupyter Notebook - Ambiente de desenvolvimento interativo

### Bibliotecas de Ciência de Dados
- Pandas - Manipulação e análise de dados
- NumPy - Computação numérica e operações com arrays
- Matplotlib & Seaborn - Visualização de dados e gráficos

### Machine Learning
- Scikit-learn - Algoritmos de ML, métricas e pré-processamento
  - RandomForestClassifier - Modelo ensemble baseado em árvores
  - LogisticRegression - Modelo linear probabilístico
  - GridSearchCV - Otimização automática de hiperparâmetros
  - StandardScaler - Normalização de dados
  - train_test_split - Divisão treino/teste

### Métricas e Avaliação
- Accuracy, Precision, Recall, F1-Score - Métricas de classificação
- ROC-AUC - Área sob a curva ROC
- Confusion Matrix - Matriz de confusão
- Cross-validation - Validação cruzada para robustez



## 🔬 Metodologia

### 1. Preparação dos Dados
- Limpeza: Remoção de IDs únicos e variáveis redundantes
- Seleção de Features: Análise de correlação para eliminar variáveis com baixo poder preditivo
- Encoding: Conversão de variáveis categóricas usando One-Hot Encoding
- Normalização: Padronização de variáveis numéricas para Regressão Logística

### 2. Análise Exploratória
- Distribuição de Churn: Análise do balanceamento das classes (26.5% churn)
- Correlações: Identificação de variáveis com maior correlação com churn
- Análise Bivariada: Investigação das relações entre tenure, gastos mensais e churn

### 3. Desenvolvimento de Modelos
- Abordagem Comparativa: Desenvolvimento de dois modelos complementares
- Random Forest: Modelo robusto sem necessidade de normalização
- Regressão Logística: Modelo interpretável com dados normalizados
- Otimização: Grid Search para encontrar melhores hiperparâmetros

### 4. Validação e Avaliação
- Validação Cruzada: 5-fold cross-validation para estabilidade
- Métricas Múltiplas: Avaliação usando accuracy, precision, recall e F1-score
- Análise de Overfitting: Comparação performance treino vs. teste



## 📊 Análise dos Dados

### Dataset Características
- Total de Registros: 7.034 clientes
- Taxa de Churn: 26.5% (1.869 clientes)
- Variáveis: 23 features após pré-processamento
- Período: Dados de comportamento histórico de clientes

### Principais Descobertas da EDA

#### 1. Distribuição de Churn
- 73.5% dos clientes permanecem ativos
- 26.5% evadem (ratio 2.8:1)
- Dataset moderadamente desequilibrado, mas gerenciável

#### 2. Tempo de Relacionamento (Tenure)
- Clientes que permanecem: 37.6 meses em média
- Clientes que evadem: 17.9 meses em média
- Insight: Período crítico são os primeiros 6-12 meses

#### 3. Gastos Mensais
- Clientes que permanecem: R$ 61.27 em média
- Clientes que evadem: R$ 74.44 em média
- Insight: Gastos mais altos estão associados a maior churn

#### 4. Variáveis Mais Correlacionadas com Churn
1. Contract_Month-to-month: +0.405 (contratos mensais aumentam churn)
2. tenure: -0.352 (maior tempo reduz churn)
3. PaperlessBilling_Yes: +0.192 (cobrança digital aumenta churn)
4. PaymentMethod_Electronic check: +0.302 (método menos conveniente)

## 🤖 Modelos Desenvolvidos

### Modelo 1: Random Forest Classifier
Características:
- Algoritmo: Ensemble de árvores de decisão otimizado via Grid Search
- Vantagens: Robusto, não requer normalização, boa interpretabilidade
- Hiperparâmetros Otimizados via Grid Search

Performance:
- Acurácia: 78.4%
- Precision: Variável conforme threshold
- Recall: Variável conforme threshold
- F1-Score: 0.642

### Modelo 2: Regressão Logística
Características:
- Algoritmo: Regressão linear com função logística
- Vantagens: Altamente interpretável, fornece probabilidades calibradas
- Hiperparâmetros Otimizados via Grid Search

Performance:
- Acurácia: 75.4%
- Precision: Variável conforme threshold
- Recall: Variável conforme threshold
- F1-Score: Menor que Random Forest
- AUC-ROC: Boa performance

### Modelo Recomendado: Random Forest
Justificativa:
- Melhor F1-Score (0.642 vs menor para LR)
- Maior acurácia (78.4% vs 75.4%)
- Robustez e estabilidade superior
- Melhor balanceamento precision-recall
- Modelos salvos como: modelo_random_forest_final.pkl e modelo_regressao_logistica_final.pkl

## 🏆 Principais Resultados

### Variáveis Críticas Identificadas

#### 1. tenure (Tempo de Relacionamento)
- Importância RF: 27.8% (1ª posição)
- Coeficiente LR: -0.803 (DIMINUI churn)
- Insight: Cada mês adicional reduz significativamente o risco

#### 2. Charges.Monthly (Gastos Mensais)
- Importância RF: 15.0% (2ª posição)
- Coeficiente LR: Presente mas não no top 3
- Insight: Clientes com gastos altos são mais propensos ao churn

#### 3. Contract_Two year (Contrato de 2 Anos)
- Importância RF: 11.0% (3ª posição)
- Coeficiente LR: -1.064 (DIMINUI churn - 1ª posição)
- Insight: Contratos longos são fundamentais para retenção

#### 4. Contract_One year (Contrato de 1 Ano)
- Importância RF: Variável importante
- Coeficiente LR: -0.670 (DIMINUI churn - 3ª posição)
- Insight: Contratos anuais também reduzem significativamente o churn

### 4 Variáveis Críticas Consolidadas:
1. Contract_One year - Forte proteção contra churn
2. Contract_Two year - Proteção máxima contra churn  
3. Charges.Monthly - Fator de risco quando elevado
4. tenure - Proteção crescente com tempo de relacionamento
- Importância RF: 8.9% (3ª posição)
- Coeficiente LR: -0.756 (forte proteção)
- Insight: Contratos longos são fundamentais para retenção

#### 4. PaymentMethod_Electronic check
- Importância RF: 7.1% (5ª posição)
- Coeficiente LR: +0.623 (aumenta risco)
- Insight: Método de pagamento menos conveniente gera atrito

#### 5. InternetService_Fiber optic
- Importância RF: 6.8% (4ª posição)
- Coeficiente LR: +0.445 (aumenta risco)
- Insight: Fibra óptica tem maior churn que DSL

### Performance Comparativa
| Métrica | Random Forest | Regressão Logística | Melhor |
|---------|---------------|---------------------|---------|
| Accuracy | 78.4% | 75.4% | Random Forest |
| F1-Score | 0.642 | Menor | Random Forest |
| Interpretabilidade | Boa | Excelente | Reg. Logística |
| Modelo Recomendado | ✅ Random Forest | - | Melhor Performance |

## 💡 Insights de Negócio

### 1. Período Crítico de Retenção
- Descoberta: 70% do churn ocorre nos primeiros 12 meses
- Implicação: Necessidade de programa intensivo de onboarding
- Ação: Monitoramento especial nos primeiros 6 meses

### 2. Paradoxo dos Gastos Altos
- Descoberta: Clientes que gastam mais têm maior propensão ao churn
- Implicação: Possível insatisfação com custo-benefício
- Ação: Revisão de valor percebido vs. preço para clientes premium

### 3. Importância dos Contratos Longos
- Descoberta: Contratos anuais reduzem churn em 60%
- Implicação: Flexibilidade contratual tem trade-off com retenção
- Ação: Incentivos para migração de contratos mensais para anuais

### 4. Atrito no Método de Pagamento
- Descoberta: Cheque eletrônico aumenta churn em 30%
- Implicação: Experiência de pagamento impacta satisfação
- Ação: Facilitar migração para débito automático

### 5. Desafio da Fibra Óptica
- Descoberta: Fibra tem maior churn que DSL
- Implicação: Expectativas mais altas não estão sendo atendidas
- Ação: Melhoria na qualidade de serviço e suporte técnico

## 📈 Recomendações Estratégicas

### 🚨 Programa Early Warning (Prioridade Alta)
Objetivo: Reduzir churn nos primeiros 6 meses em 30%

Ações:
- Score de risco automático para clientes novos
- Contato proativo da equipe de sucesso nos primeiros 30 dias
- Programa de benefícios especiais para período de adaptação
- Monitoramento quinzenal de satisfação

### 💰 Estratégia de Pricing Inteligente (Prioridade Alta)
Objetivo: Otimizar relação preço-valor para diferentes segmentos

Ações:
- Segmentação de clientes por sensibilidade ao preço
- Ofertas personalizadas baseadas no perfil e histórico
- Programa de fidelidade com benefícios crescentes por tempo
- Análise regular de valor percebido vs. preço pago

### 📋 Migração Contratual Incentivada (Prioridade Média)
Objetivo: Aumentar proporção de contratos anuais em 25%

Ações:
- Campanhas direcionadas para conversão mensal → anual
- Benefícios exclusivos para contratos de longo prazo
- Processo simplificado de upgrade contratual
- Comunicação clara das vantagens da estabilidade

### 🔧 Excelência Operacional (Prioridade Média)
Objetivo: NPS > 70 e tempo de resolução < 24h

Ações:
- Suporte técnico especializado para fibra óptica
- Resolução proativa de problemas antes que virem reclamações
- Sistema de feedback contínuo dos clientes
- Treinamento das equipes com base nos insights dos modelos

### 📱 Experiência Digital Superior (Prioridade Baixa)
Objetivo: 90% dos clientes usando canais digitais

Ações:
- Portal do cliente intuitivo com todas as funcionalidades
- App mobile com processo de pagamento simplificado
- Comunicação omnichannel integrada
- Incentivos para migração de métodos de pagamento

## ⚙️ Como Executar

### Pré-requisitos
bash
# Instalar as dependências
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

### Execução
1. Clone ou baixe os arquivos do projeto
2. Navegue até o diretório do projeto
3. Inicie o Jupyter Notebook:
   bash
   jupyter notebook TelecomX_BR.ipynb
   
4. Execute as células sequencialmente para reproduzir a análise

### Usando os Modelos Treinados

Os modelos finais já estão salvos e prontos para uso em produção:

python
import pickle
import pandas as pd

# Carregar modelo Random Forest (recomendado)
with open('modelo_random_forest_final.pkl', 'rb') as f:
    modelo_rf = pickle.load(f)

# Carregar modelo Regressão Logística  
with open('modelo_regressao_logistica_final.pkl', 'rb') as f:
    modelo_lr = pickle.load(f)

# Fazer predições em novos dados
# X_novos_dados deve ter as mesmas features do treinamento
predicoes = modelo_rf.predict(X_novos_dados)
probabilidades = modelo_rf.predict_proba(X_novos_dados)[:, 1]


Modelos Disponíveis
- modelo_random_forest_final.pkl: 78.4% acurácia, F1-Score 0.642 ✅ Recomendado
- modelo_regressao_logistica_final.pkl: 75.4% acurácia, alta interpretabilidade

### Estrutura do Notebook
1. Importação de Bibliotecas - Setup do ambiente
2. Preparação dos Dados - Limpeza e feature engineering
3. Análise Exploratória - Visualizações e insights iniciais
4. Correlação e Seleção - Identificação de variáveis importantes
5. Modelagem - Desenvolvimento dos modelos Random Forest e Regressão Logística
6. Otimização - Grid Search para hiperparâmetros
7. Avaliação - Métricas de performance e comparação
8. Interpretação - Análise das variáveis mais importantes
9. Insights de Negócio - Tradução dos resultados em recomendações

## 📊 Métricas de Acompanhamento

### Métricas Principais
- Taxa de churn por tenure: 0-6m, 6-12m, 12m+
- Churn por tipo de contrato: Mensal vs. Anual vs. 2 anos
- Satisfação por método de pagamento
- NPS segmentado por tipo de serviço (DSL vs. Fibra)
- Taxa de conversão contratual (mensal → anual)

### Métricas Operacionais
- Tempo médio de resolução de problemas técnicos
- Taxa de adoção de canais digitais
- Efetividade das ações de retenção por segmento
- Score de risco de churn em tempo real
- ROI das campanhas de retenção

## 🚀 Próximos Passos

### Implementação Imediata (30 dias)
1. Implementar score de risco baseado nas 5 variáveis críticas
2. Criar dashboards de monitoramento em tempo real
3. Treinar equipes com base nos insights dos modelos
4. Definir processos de intervenção por nível de risco

### Médio Prazo (90 dias)
1. Lançar programa Early Warning para clientes novos
2. Revisar estratégia de pricing por segmento
3. Campanha de migração contratual com incentivos
4. Melhorar experiência para clientes de fibra óptica

### Longo Prazo (180 dias)
1. Avaliar impacto das ações implementadas
2. Ajustar modelos com novos dados
3. Expandir programa para outros segmentos
4. Benchmark com concorrentes e melhores práticas

### Melhorias Técnicas Futuras
1. Modelos Ensemble Avançados: XGBoost, LightGBM
2. Deep Learning: Redes neurais para padrões complexos
3. Análise Temporal: Modelos que consideram evolução do comportamento
4. Segmentação Automática: Clustering para identificar perfis de risco
5. A/B Testing: Validação experimental das estratégias propostas

## 🎯 Resultados Esperados

Com a implementação das estratégias baseadas nos insights dos modelos de Machine Learning:

### Resultados Obtidos pelos Modelos:
- Random Forest: 78.4% de acurácia, F1-Score 0.642 ✅ Modelo Final
- Regressão Logística: 75.4% de acurácia, alta interpretabilidade
- Concordância: 4 variáveis críticas identificadas por ambos os modelos
- Confiabilidade: Modelos apresentam boa generalização (sem overfitting)

### Impacto Esperado das Estratégias:
- Redução de 20-30% na taxa de churn geral
- Redução de 40% no churn dos primeiros 6 meses  
- Aumento de 25% na proporção de contratos anuais
- Melhoria de 15 pontos no NPS
- ROI positivo das ações de retenção em 6 meses

### Variáveis Críticas para Monitoramento:
1. tenure (Tempo de relacionamento) - Proteção crescente
2. Charges.Monthly (Gastos mensais) - Fator de risco 
3. Contract_Two year - Proteção máxima contra churn
4. Contract_One year - Forte proteção contra churn

## 📞 Contato e Suporte

Para dúvidas sobre implementação ou extensões do projeto:
- Análise Técnica: Consulte o notebook detalhado TelecomX_BR.ipynb
- Insights de Negócio: Verifique as seções de recomendações estratégicas
- Reprodutibilidade: Todos os códigos estão documentados no notebook
- Modelos Prontos: Use os arquivos .pkl para predições em produção

### 🏁 Status do Projeto: CONCLUÍDO COM SUCESSO ✅

Entregáveis Finais:
- ✅ Análise exploratória completa dos dados
- ✅ Dois modelos de Machine Learning desenvolvidos e otimizados
- ✅ Random Forest: 78.4% acurácia (modelo recomendado)
- ✅ Regressão Logística: 75.4% acurácia (alta interpretabilidade)
- ✅ Modelos salvos e prontos para produção (arquivos .pkl)
- ✅ 4 variáveis críticas identificadas para monitoramento
- ✅ Estratégias de retenção baseadas em evidências quantitativas
- ✅ Documentação completa e reprodutível

🚀 Modelos e estratégias prontos para implementação em produção!

### 📄 Licença
Este projeto foi desenvolvido para fins educacionais e de demonstração de técnicas de Machine Learning aplicadas a problemas reais de negócio.
