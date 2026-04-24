# Machine-Learning-Classification

Como atividade acadêmica, desenvolvemos um projeto de Machine Learning supervisionado, utilizando como referência a estrutura de um case prático voltado à análise comercial. Ressaltamos que a base de dados utilizada no trabalho final é diferente da base originalmente proposta, pois alguns dados continham informações sensíveis e frágeis. Dessa forma, foi aproveitada principalmente a lógica do código, metodologia analítica e estrutura do projeto, com adaptações realizadas pelo grupo para fins de aprendizado.

O conjunto de dados utilizado continha informações sobre oportunidades comerciais ganhas e perdidas, incluindo variáveis como status da oportunidade, datas de criação e encerramento, motivo de perda, perfil do cliente (ICP), vendedor responsável, pré-vendedor, valor da oportunidade, segmento de mercado e origem do lead.

* Objetivo do Projeto

O principal objetivo foi identificar os fatores que influenciam a perda de oportunidades comerciais, analisando também os padrões relacionados às oportunidades convertidas com sucesso. Para isso, buscamos responder perguntas como:

Quais os principais motivos de perda?
O tempo da oportunidade influencia no fechamento?
Quais canais geram melhores resultados?
Existe diferença de performance entre vendedores?
O ICP impacta na conversão?
É possível prever se uma oportunidade será ganha ou perdida?

* Metodologia Aplicada

O projeto foi conduzido com base na metodologia CRISP-DM, passando pelas etapas de:

Compreensão do negócio
Entendimento dos dados
Preparação da base
Análise exploratória (EDA)
Modelagem preditiva
Avaliação dos resultados
Técnicas Utilizadas

Durante o desenvolvimento foram aplicadas técnicas como:

Tratamento e limpeza de dados com Python / Pandas
Visualização de dados com Matplotlib e Seaborn
Clusterização com K-Means
Classificação com Decision Tree
Avaliação por Matriz de Confusão, ROC Curve e AUC
Interpretação de variáveis com Feature Importance e SHAP Values
Principais Insights

* Os resultados indicaram que:

O tempo em aberto da oportunidade foi uma das variáveis mais relevantes para prever perdas;
O valor financeiro teve baixa influência isolada;
Alguns canais de origem apresentaram melhor conversão que outros;
Grande parte das perdas estava relacionada à falta de contato, desinteresse ou demora no processo comercial;
O modelo preditivo apresentou bom desempenho para apoiar a priorização comercial.

* Conclusão

O projeto proporcionou uma experiência prática completa em Ciência de Dados aplicada ao contexto de negócios, envolvendo desde exploração e tratamento dos dados até construção e interpretação de modelos de Machine Learning.
