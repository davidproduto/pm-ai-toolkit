# Skill: Data-Informed Prioritization

Cruza o backlog com dados de uso (analytics) e volume de suporte para gerar um ranking de prioridade defensável — em vez de priorizar por "quem gritou mais alto por último".

## Input
- Lista de itens candidatos ao backlog (de qualquer origem: suporte, vendas, pesquisa, ideia interna).
- Dados de uso do produto (analytics: quantos usuários tocam essa área, com que frequência).
- Volume de tickets de suporte relacionados a cada item, se houver.

## Processo
1. Para cada item do backlog, monte uma linha com: alcance (quantos usuários afeta), frequência (uso recorrente ou pontual), severidade (bloqueia o trabalho ou é incômodo menor), e esforço estimado (se já houver estimativa de eng).
2. Use um framework simples e transparente — RICE (Reach, Impact, Confidence, Effort) ou um score próprio — para não depender de "achismo".
3. Peça para a IA montar a tabela e ordenar, mas **sempre revise manualmente os 3 primeiros e os 3 últimos** — o modelo pode superestimar itens com dados incompletos.
4. Documente a decisão final no [decision log](../templates/decision-log-template.md), incluindo o que foi descartado e por quê.

### Prompt de exemplo
```
Tenho estes N itens de backlog com os seguintes dados: [colar tabela com alcance, frequência,
severidade, esforço estimado]. Aplique RICE e monte um ranking. Para os 3 primeiros e 3
últimos colocados, explique o racional em uma frase.
```

## Output esperado
Uma tabela ranqueada com racional explícito por item — algo que você consegue defender em uma reunião de priorização sem parecer arbitrário.

## Limite
- O modelo não conhece o contexto estratégico da empresa (parcerias, compromissos contratuais, pressão de um cliente-chave) — isso precisa ser ajustado manualmente por você.
- RICE (ou qualquer framework) é um ponto de partida, não uma verdade absoluta — use para estruturar a conversa, não para terceirizar a decisão.
