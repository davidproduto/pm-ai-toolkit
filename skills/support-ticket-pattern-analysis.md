# Skill: Support Ticket Pattern Analysis

Transforma uma exportação de tickets de suporte (CSV/XLSX) em padrões de bug agrupados, prontos para virar itens de backlog com causa raiz e critério de aceite.

## Input
- Um arquivo com tickets exportados do seu helpdesk (Zendesk, Intercom, etc.), contendo pelo menos: assunto, descrição, categoria/módulo, data.
- (Opcional) Volume de usuários afetados por ticket, se disponível.

## Processo
1. Peça para a IA agrupar os tickets por tema/submódulo e tipo de resolução (bug, dúvida, pedido de feature).
2. Para cada grupo com volume relevante, peça uma hipótese de causa raiz baseada no padrão de texto dos tickets (não uma causa raiz técnica real — é um ponto de partida para investigação).
3. Peça um rascunho de item de backlog: título, descrição do problema, causa raiz suspeita, critério de aceite, e os tickets de exemplo que sustentam essa demanda.
4. Sempre valide manualmente antes de criar o item real — a IA agrupa padrões textuais, não confirma causa raiz técnica.

### Prompt de exemplo
```
Aqui está uma exportação de tickets de suporte do módulo [X] (anexo/colado abaixo).
Agrupe por tema recorrente, ordene por volume, e para os 5 maiores grupos sugira:
- um título de item de backlog
- causa raiz suspeita (baseada no padrão dos relatos, não confirmada)
- critério de aceite
- quais tickets (ID) sustentam essa demanda
```

## Output esperado
Uma lista curta (3-5 itens) de possíveis demandas de produto, cada uma rastreável até os tickets originais — pronta para revisão humana antes de virar issue no Jira/GitHub.

## Limite
- Não substitui investigação técnica real da causa raiz.
- Volume de reclamação não é sinônimo de prioridade — cruze sempre com impacto de negócio (ver [data-informed-prioritization](./data-informed-prioritization.md)).
- Nunca cole dados sensíveis de clientes reais em ferramentas de IA sem checar a política de dados da sua empresa.
