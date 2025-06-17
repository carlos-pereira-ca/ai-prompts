
# 🧠 Prompt de Avaliação INVEST para Estórias de Usuário no Jira

Este prompt define o comportamento de um **avaliador inteligente de estórias de usuário** baseado na técnica **INVEST** (*Independent, Negotiable, Valuable, Estimable, Small, Testable*), amplamente utilizada em contextos ágeis de engenharia de software.

O agente avalia estórias de forma **estruturada, ponderada e explicável**, atribuindo notas de 0 a 10 para cada dimensão do INVEST com base nos seguintes campos fornecidos:

- `Resumo`
- `Estória` (descrição principal)
- `Critérios de Aceitação`
- `Esta Estória é Parte do Épico`
- `Sumário de Subtarefas`

---

## ⚖️ Lógica de Avaliação

Cada dimensão INVEST possui:
- Um **peso definido** na média final
- **Critérios objetivos de pontuação**
- **Aceleradores e penalizações** com base na qualidade ou ausência de campos

A pontuação final é calculada como uma **média ponderada** dos critérios INVEST:

| Dimensão    | Peso |
|-------------|------|
| Independent | 15%  |
| Negotiable  | 15%  |
| Valuable    | 20%  |
| Estimable   | 20%  |
| Small       | 10%  |
| Testable    | 20%  |

---

## 🔍 Transparência nas Justificativas

O agente é instruído a **mencionar explicitamente** qualquer fator da instrução que tenha influenciado a nota de cada dimensão. Isso garante rastreabilidade e clareza nas análises.

---

## ✨ Diferenciais

- Adaptado para **estórias técnicas**, reconhecendo valor técnico no critério *Valuable*
- Penalização automática por ausência de campos essenciais (ex: descrição ou critérios de aceitação)
- Uso inteligente do **número de subtarefas** para calibrar os critérios *Small*, *Estimable* e *Testable*
- Saída padronizada com formatação legível e consistente
- Ideal para uso com **agentes LLM (ex: OpenAI)** integrados ao Jira, n8n, pipelines de revisão de backlog ou rotinas de auditoria ágil

---

## 📥 Comandos suportados

- `[score]` → Retorna somente o score final numérico (ex: `8.3`)
- `[analise]` → Retorna análise completa INVEST com notas, justificativas e recomendações

---

## 🛠 Exemplos de uso

Integrável em ferramentas como:
- n8n (fluxos de automação com entrada de estórias)
- Workflows de QA de backlog
- Scripts de auditoria para refinamento contínuo
- Avaliações automatizadas em rituais ágeis

---

> Criado e mantido por [@carlos.pereira](mailto:carlos.pereira@contaazul.com)
