# Modelos Substitutos Regionais como Guia para Otimização de Raciocínio Abdutivo no Diagnóstico Clínico
## Disciplina: Inteligência Artificial Explicável com Raciocínio Automatizado

Este projeto implementa um pipeline de **Explainable AI (XAI)** baseado em uma abordagem **Neuro-Simbólica**. O objetivo principal é extrair explicações locais minimalistas e logicamente consistentes de um modelo *black-box* através de um processo de duas etapas: **Destilação de Conhecimento** (usando um Modelo Substituto Regional) e **Raciocínio Abdutivo**.

O pipeline foi validado utilizando o clássico conjunto de dados *UCI Heart Disease Dataset*, demonstrando alta fidelidade e capacidade de simplificação cognitiva de predições clínicas.

---

## 🧠 Arquitetura do Sistema

O fluxo de trabalho do framework é dividido em três pilares fundamentais:

1. **Linha de base de desempenho preditivo (Modelo mestre):** Treinamento de um classificador de alta performance (*XGBoost*).
2. **Destilação de conhecimento (Modelo estudante):** Destilação do comportamento do *Mestre* para um *aluno* (uma *Árvore de Decisão rasa*), que atua como um particionador do espaço de *features* e filtro de ruído, alcançando **80.22% de fidelidade**.
3. **Busca da Explicação Abdutiva:** Aplicação de um algoritmo *greedy backward-elimination* sobre o modelo destilado para encontrar o **Subconjunto suficiente mínimo** (*Prime Implicant*), isolando apenas as predições críticas para uma instância local.
