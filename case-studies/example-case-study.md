# Case Study: Reduzindo abandono no fluxo de matrícula (dados fictícios)

> Todos os números, nomes e trechos de ticket abaixo são fictícios, criados para fins de exemplo.

## 1. Problema
No início do trimestre, o time de suporte notou um aumento de tickets sobre "erro ao finalizar matrícula" no módulo de Secretaria. A hipótese inicial era um bug técnico pontual.

**Evidência:**
- 47 tickets em 3 semanas mencionando falha na etapa final do fluxo de matrícula (vs. média histórica de ~8/mês).
- Dado de analytics: taxa de conclusão do funil de matrícula caiu de 82% para 61% no mesmo período.

## 2. Investigação
Usando a skill [support-ticket-pattern-analysis](../skills/support-ticket-pattern-analysis.md), agrupamos os 47 tickets:
- 68% mencionavam um campo obrigatório específico ("documento do responsável") que não estava claro que era obrigatório antes do envio.
- 22% eram sobre lentidão no upload de anexos.
- 10% eram casos diversos sem padrão claro.

**Causa raiz suspeita:** mudança recente de layout moveu o campo obrigatório para uma seção colapsada por padrão, e usuários não abriam a seção antes de tentar enviar.

## 3. Hipótese e decisão
Em vez de assumir que era "só um bug", tratamos como problema de UX de formulário — o campo existia, mas estava invisível no fluxo padrão.

**Métrica de sucesso:** taxa de conclusão do funil de matrícula voltar a ≥80% em 2 semanas após o ajuste.

## 4. Experimento
Ver [experiment brief](../templates/experiment-brief-template.md) preenchido:
- **Mudança:** seção com o campo obrigatório passa a vir expandida por padrão + validação inline antes do envio final.
- **Desenho:** feature flag, rollout gradual 10% → 50% → 100% ao longo de 5 dias, monitorando taxa de conclusão e volume de tickets relacionados.

## 5. Resultado
| | Esperado | Real |
|---|---|---|
| Taxa de conclusão do funil | ≥80% | 84% |
| Volume de tickets relacionados | queda de 70%+ | queda de 81% |

## 6. Decisão final
Ship para 100% dos usuários. Registrado no [decision log](../templates/decision-log-template.md) com nota para revisitar em 3 meses caso surja novo padrão de ticket no mesmo fluxo.

## 7. Aprendizado
Volume alto de tickets num curto espaço de tempo é sinal mais forte do que reclamação isolada — mas a causa raiz real só apareceu quando agrupamos por padrão textual, não olhando ticket por ticket. Isso motivou formalizar a skill de análise de padrões como parte do processo padrão de triagem.
