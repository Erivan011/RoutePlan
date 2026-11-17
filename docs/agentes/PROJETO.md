# Briefing — RoutePlan
## Objetivo
Portfólio pessoal de otimização de distribuição, com rotas, lotes, frota, cenários versionados e resultados auditáveis. Backend FastAPI/OR-Tools; frontend React/TypeScript.
## Fonte de verdade
README.md, docs/ALGORITMO.md, docs/ARQUITETURA.md, package.json e CI. A demonstração pública lê docs/demo-result.json; dados privados não devem passar por endpoints públicos.
## Prioridades
1. Preservar separação entre demo pública e operação administrativa.
2. Corrigir falhas reproduzíveis de filtros, alocações, exportação e estados vazios sem mudar silenciosamente o solver.
3. Melhorar clareza das rotas e razões de não atendimento, responsividade e uso pelo teclado.
4. Investigar continuidade de hospedagem: README registra expiração da base gratuita em 25/11/2026; esta anotação é um alerta documental, não verificação do provedor.
## Critérios de aceitação
- Visitante acessa apenas demonstração e exportações fictícias; endpoints administrativos exigem autenticação.
- Cada alocação respeita restrições e passa pelo verificador independente.
- Simulação não altera estoque; expedição tem validação própria e mantém histórico.
- Testes usam banco local temporário e cenário sintético; nenhum token real em comando, log, commit ou captura.
- Alterações visuais verificadas em desktop/móvel e sem perda de foco ao filtrar.
## Primeira investigação
Conferir checks e identificar uma falha pequena com reprodução. Não tocar na base de produção nem regenerar resultado de demonstração sem explicar a mudança.
