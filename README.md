📊 Análise de Risco de Crédito — Lending Club (2019–2020)

Projeto completo envolvendo Python, SQL, Estatística, EDA e Machine Learning (bônus), inspirado em práticas utilizadas por bancos e fintechs para avaliação de risco de crédito.

🚀 1. Motivação do Projeto

Este é meu primeiro projeto completo de Análise de Risco de Crédito, criado com os objetivos de:

Consolidar conhecimentos em Python, SQL, Estatística e Machine Learning

Desenvolver capacidade analítica em finanças e risco de crédito

Criar um projeto robusto para portfólio

Simular etapas reais adotadas por instituições financeiras

Durante o desenvolvimento, enfrentei desafios reais — como grande volume de dados, manipulação SQL, tratamento de inconsistências e balanceamento de classes — o que resultou em forte evolução prática.

🧭 2. Etapas do Projeto

O projeto foi estruturado em cinco grandes fases, replicando um fluxo profissional de Data Science:

2.1 Entendimento do Problema e Perguntas de Negócio

Análise inicial do dataset

Compreensão das variáveis

Formulação de 10 perguntas-chave

2.2 Preparação do Dataset

Uso de SQL para filtrar os anos 2019 e 2020

Redução de 90 → 73 colunas

Criação das tabelas:

analise_de_credito

previsao_de_inadimplencia

Organização e tratamento de colunas numéricas e categóricas

Estruturação para EDA e ML

📌 Sobre o arquivo projeto.db

O arquivo projeto.db, disponibilizado neste repositório, não é o dataset original do Lending Club.
Ele já está tratado, filtrado e compactado, resultado do processamento feito no DB Browser for SQLite, onde:

Reduzi o dataset original de mais de 1.000.000 de linhas para 96.000 linhas

Filtrei somente os anos 2019 e 2020

Utilizei comandos DROP para remover colunas irrelevantes

Executei VACUUM para compactar e otimizar o arquivo

Deixei o banco mais leve e adequado para análise e Machine Learning

Essa é a versão utilizada no notebook.

2.3 Análise Exploratória (EDA)

Gráficos, estatísticas e análises

Relação entre renda, FICO, juros, propósitos e inadimplência

Avaliação geográfica, temporal e comportamental

Análises completas com visualizações

2.4 Machine Learning (bônus)

Pré-processamento com ColumnTransformer

Random Forest com class_weight="balanced"

Avaliação com AUC-ROC, Recall e métricas detalhadas

Comparação entre modelo balanceado × não balanceado

2.5 Documentação

Síntese dos resultados

Limitações

Possíveis melhorias

README final (este arquivo)

❓ 3. Perguntas de Negócio Investigadas

Qual o valor médio dos empréstimos e quais faixas são mais comuns?

Qual a situação dos empréstimos (Fully Paid × Charged Off)?

Como o FICO Score se distribui e como afeta inadimplência?

Há diferença de renda entre os propósitos de empréstimo?

Quais propósitos são mais comuns e mais arriscados?

O histórico de crédito interfere no risco?

Taxas de juros influenciam inadimplência?

Há regiões/estados com risco maior?

Como o volume de empréstimos evoluiu em 2019–2020?

Quais variáveis mais influenciam inadimplência (feature importance)?

📈 4. Principais Resultados do EDA
1. Valor dos Empréstimos

Média: R$ 15.142

Faixas mais comuns: R$ 9.580–10.360 e R$ 14.260–15.040

Máximo: R$ 40.000

2. Situação dos Empréstimos

Fully Paid: 81,6%

Charged Off: 18,4%
➡ Taxa de inadimplência elevada.

3. FICO Score

Média: 711

87% entre Bom e Muito Bom
➡ Quanto menor o FICO, maior a inadimplência.

4. Renda × Propósito

ANOVA indica diferença significativa

Alta renda: small_business, house

Baixa renda: vacation, renewable_energy, car

5. Propósitos mais arriscados

small_business → 25% inadimplência

medical → 18,5%

Outros entre 16–17%

6. Histórico de Crédito

Contas abertas têm relação moderada

Registros negativos quase não influenciam

7. Taxas de Juros

Quanto maior a taxa → maior inadimplência

ANOVA e Spearman confirmam relação forte

8. Geografia

Distribuição equilibrada entre regiões

Risco semelhante (17–19%)

9. Evolução 2019–2020

Queda constante dos volumes
➡ Impacto provável da COVID-19

10. Variáveis mais importantes

int_rate, installment, dti, revol_util, fico, subgrade, home_ownership, etc.
➡ Risco é multifatorial, sem variável dominante.

🤖 5. Machine Learning (bônus)
Pré-processamento

Numéricos → mediana

Categóricos → moda + OneHotEncoder

ColumnTransformer integrado ao Pipeline

Modelo 1 – Random Forest (não balanceado)

Recall inadimplentes ≈ 0
❌ Não utilizável.

Modelo 2 – Random Forest (balanceado)

Recall inadimplentes: 0.54

Recall bons pagadores: 0.73

AUC-ROC: 0.70

➡ Modelo inicial funcional e realista.

📝 6. Conclusões

A carteira apresenta risco elevado para padrões de mercado

Juros têm forte relação com inadimplência

FICO Score é excelente indicador de risco

Histórico de crédito tem efeito limitado

COVID-19 afetou diretamente o volume de empréstimos

O modelo ML é útil para triagem inicial de risco

🔧 7. Possíveis Melhorias

Testar XGBoost, CatBoost e LightGBM

Aplicar SMOTE

Hiperparâmetros mais avançados

SHAP/LIME para explicabilidade

Clusterização por perfis de clientes

Criar dashboard (Power BI ou Streamlit)

🔄 8. Como Carregar o Dataset no Google Colab (Forma Manual)

Como o arquivo do dataset é muito grande para ser enviado ao GitHub, o carregamento foi feito via upload manual.

📌 Passo a passo

Baixe o arquivo projeto.db para o seu computador
📥 Link para download do dataset

🔗https://drive.google.com/file/d/166iHxROEGtXp4YPppD5xU48qGR8zZ3iD/view?usp=sharing

Abra o notebook no Google Colab

Execute:

from google.colab import files
uploaded = files.upload()


Selecione o arquivo

Aguarde o upload

Continue executando o notebook normalmente

📂 9. Estrutura do Repositório
├── README.md                       → Documentação principal do projeto
├── projeto.db                      → Dataset tratado e compactado (96 mil linhas, 2019–2020)
└── Projeto-risco-de-credito.ipynb  → Notebook completo com EDA, SQL e ML (bônus)

