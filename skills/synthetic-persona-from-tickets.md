# Skill: Synthetic Persona from Tickets

Cria uma "persona" com voz real de usuário a partir de um volume grande de tickets/feedback — útil para testar uma hipótese de produto rapidamente antes de esperar uma pesquisa qualitativa formal.

## Input
- Um volume razoável de tickets/feedback de um segmento específico de usuário (ex: "usuários do módulo financeiro"), quanto mais real e recente, melhor.
- Contexto de quem é esse usuário (cargo, contexto de uso, nível técnico).

## Processo
1. Peça para a IA extrair da massa de tickets: vocabulário real usado, principais frustrações, e o que o usuário valoriza quando algo funciona bem.
2. Peça para consolidar isso em uma persona com nome, contexto e "voz" consistente com os dados — não uma persona genérica de manual de marketing.
3. Use essa persona para rodar hipóteses de produto rapidamente ("como a Persona X reagiria a Y?") como um primeiro filtro — nunca como substituto de validação real com usuários.
4. Revalide a persona periodicamente com dados novos — ela fica desatualizada conforme o produto muda.

### Prompt de exemplo
```
Aqui estão N tickets de suporte de usuários do módulo [X] (cargo: [Y]).
Extraia: vocabulário recorrente, principais frustrações, o que valorizam quando algo funciona.
Consolide em uma persona com nome, contexto de uso e "voz" — que eu possa usar para testar
hipóteses de produto rapidamente.
```

## Output esperado
Um documento curto de persona (meia página), com trechos reais (anonimizados) que sustentam cada traço — não uma ficha genérica.

## Limite
- É um atalho para hipótese inicial, não substitui pesquisa com usuários reais antes de uma decisão grande.
- Risco real: a persona pode refletir só quem reclama (viés de quem abre ticket), não a base toda — sempre deixe isso explícito quando for usar o output.
- Nunca inclua dados que identifiquem clientes/usuários reais — sempre anonimize antes de gerar ou compartilhar.
