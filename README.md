# 📊 Machine Learning aplicado a Recrutamento e Seleção

## 📌 Sobre o Projeto
Como atividade acadêmica, um projeto de **Machine Learning Supervisionado** foi desenvolvido, utilizando como referência a estrutura de um case prático voltado à análise comercial. A base de dados utilizada neste repositório é diferente da base originalmente proposta, pois alguns dados continham informações sensíveis e frágeis. Dessa forma, foi aproveitada principalmente a lógica do código, metodologia analítica e estrutura do projeto, com adaptações realizadas pelo grupo para fins de aprendizado.

Neste repositório, a base foi adaptada para um cenário de **Recrutamento e Seleção**, composta por **500 candidatos fictícios**, gerados com Python (Faker, NumPy), sem qualquer informação real.

## 🗂️ Base de Dados
Arquivo: `database_recruiter.csv` (dados simulados, sem informações reais).

| Variável | Descrição |
|---|---|
| `ID_Candidato` | Identificador do candidato |
| `Status` | Resultado final: Aprovado / Reprovado (**variável alvo**) |
| `Data_Inscricao` | Data da inscrição na vaga |
| `Data_Finalizacao` | Data de encerramento do processo |
| `Motivo_Reprovacao` | Motivo da reprovação (vazio para aprovados) |
| `Tempo_Processo_Dias` | Duração do processo seletivo em dias |
| `Pretensao_Salarial` | Pretensão salarial informada (R$) |
| `Recrutador` | Recrutador responsável |
| `Origem_Candidato` | Canal de candidatura (LinkedIn, Gupy, Indicação, Catho, Indeed, Site Empresa) |
| `Senioridade` | Júnior, Pleno ou Sênior |
| `Area` | Dados, TI, Financeiro, RH, Marketing ou Operações |
| `Teste_Tecnico` | Resultado do teste técnico |

## 🎯 Objetivo
Identificar fatores associados à aprovação ou reprovação de candidatos e avaliar se é possível prever o resultado do processo seletivo.

**Perguntas de negócio analisadas**
- Qual canal de candidatura gera mais aprovações?
- Existem diferenças de aprovação entre áreas e senioridades?
- A pretensão salarial influencia o resultado?
- O tempo do processo seletivo está associado à aprovação?
- Quais são os principais motivos de reprovação?
- Há diferença de desempenho entre recrutadores?
- É possível prever se um candidato será aprovado ou reprovado?

## 🧩 Metodologia (CRISP-DM)
1. Compreensão do negócio
2. Entendimento dos dados (dicionário, qualidade, nulos e duplicados)
3. Preparação da base (tipagem de datas, definição do target, tratamento de nulos)
4. Análise exploratória (EDA)
5. Modelagem (K-Means e Árvore de Decisão)
6. Avaliação dos resultados

## ⚙️ Técnicas e Ferramentas
Python · Pandas · NumPy · Matplotlib · Seaborn · SciPy (teste KS) · Scikit-Learn · K-Means (Elbow e Silhouette) · Decision Tree · Split temporal treino/teste · ROC/AUC · Matriz de Confusão · SHAP Values · Faker

## 🔎 O que foi feito
- **EDA:** aprovados x reprovados por origem, área, senioridade, recrutador e mês de inscrição; taxa de aprovação por categoria; principais motivos de reprovação; pretensão salarial por senioridade; tempo de processo por status.
- **KS (Kolmogorov-Smirnov):** importância univariada das variáveis numéricas.
- **K-Means:** segmentação por pretensão salarial e tempo de processo, com escolha do K via Silhouette.
- **Árvore de Decisão:** previsão de aprovação com divisão temporal (70% mais antigos para treino, 30% mais recentes para teste) e interpretação via SHAP.

## 📈 Principais Resultados e Aprendizados
- **Vazamento de informação (data leakage):** `Motivo_Reprovacao`, `Tempo_Processo_Dias`, `Data_Finalizacao` e `Teste_Tecnico` só são conhecidos após o desfecho (ou são determinados por ele). Por isso ficaram **fora do modelo**, que usa apenas variáveis disponíveis na triagem: pretensão salarial, senioridade, área, recrutador e origem.
- **Pretensão salarial** varia conforme a senioridade, mas isso reflete a forma como a base foi simulada.
- **Processos mais longos** aparecem associados a reprovações e desistências, porém como `Tempo_Processo_Dias` é consequência do desfecho, essa relação não deve ser lida como causal.
- **Desempenho do modelo:** como a base é fictícia e majoritariamente aleatória, o modelo apresenta desempenho próximo ao acaso (AUC ≈ 0,5). Isso é esperado e reforça a importância de validar hipóteses e checar vazamento antes de confiar em métricas altas.
- Resultados por canal, área e recrutador variam levemente entre si, mas **sem diferenças fortes**, o que é coerente com dados gerados aleatoriamente. (Atualize esta seção com os números da sua execução.)

> ⚠️ **Aviso:** os dados são simulados e os resultados têm finalidade exclusivamente didática. Não representam processos seletivos reais e não devem ser usados para tomada de decisão.
