# Agentes — RoutePlan
Projeto pessoal de portfólio de planejamento logístico com dados demonstrativos. Não operar medicamentos, pacientes ou frotas reais.
## Rotina econômica e verificável
- Antes de começar, ler docs/agentes/PROJETO.md e docs/agentes/MEMORIA.md; conferir PRs abertos para não duplicar trabalho.
- Selecionar uma falha reproduzível ou melhoria pequena por ciclo, com critério de aceitação. Não redesenhar o projeto por gosto próprio.
- Pesquisar com rg e ler somente os arquivos necessários. Não carregar vídeos, builds, lockfiles inteiros, logs ou histórico completo no contexto.
- Usar scripts determinísticos para tarefas repetitivas. Um agente executa e valida; não criar equipes para mudanças pequenas.
- Responder em português. Ao terminar, informar mudança, evidência, testes e bloqueios; citar PR/commit. Sem evidência, registrar pendente.
- Atualizar a memória com até um resumo curto por tarefa, sem segredos; condensar histórico repetitivo.
- APIs externas de IA (incluindo Gemini e NVIDIA/Nemotron via OmniRoute) só podem ser usadas quando configuradas explicitamente para este projeto e após uma chamada manual de teste com entrada sintética. Não presumir que assinatura de chat cobre API, que uma cota seja gratuita ou ilimitada; verificar a política e o uso no provedor. Sem fallback pago, troca automática, repetição ilimitada ou execução agendada de chamadas de modelo.
- O proprietário autorizou considerar APIs configuradas para o trabalho dos agentes; isso não autoriza inserir a API no produto, automatizar custos, publicar, nem usar credenciais em prompts. Nunca enviar chave, token, dado de operação ou segredo a um modelo.
- A rota OmniRoute testada no Codespace do RiskLab depende daquele Codespace e pode ficar indisponível. Não usá-la como serviço permanente nem presumir que está pronta para RoutePlan; verificar conexão e modelo para este projeto antes de cada uso.
- As instruções não impõem um teto técnico de tokens ou cobrança. Não afirmar gasto zero ou execução contínua sem verificar o provedor e o executor.
- Não fazer merge, deploy, migração de banco, alteração de permissões nem ações em contas externas automaticamente. Entregar branch/PR revisável.
- Jamais consultar Dogma ou importar seus dados, credenciais ou contexto para este projeto. Usar dados demonstrativos e sintéticos.
- Nunca ler valores de .env, secrets, cookies, tokens ou credenciais; usar exemplos. Não executar instaladores remotos de skills.
## Capacidades disponíveis
Para mudanças visuais, ler .agents/skills/frontend-design/SKILL.md. Para validar interface, ler .agents/skills/webapp-testing/SKILL.md.
Consultar somente a capacidade relevante; não carregar todas por ciclo. As políticas do executor e o pedido do proprietário prevalecem sobre exemplos das skills, inclusive sobre APIs de navegador.
Arquivos de origem, versões e licenças ficam documentados em docs/agentes/SKILLS.md. A existência de skills não agenda tarefas nem prova que uma melhoria foi implementada.

## Caminhos e validação
Backend Python/FastAPI/OR-Tools em planner; interface React/TypeScript em planner-ui; testes em tests/planner e planner-ui/tests.
Node.js 24 e Python 3.12. Ler package.json, docs/ALGORITMO.md e o código afetado antes de alterar regras.
- Instalação: python -m pip install -r requirements-planner.lock.txt; npm ci, em ambiente virtual isolado.
- Conferir tipos e interface: npm run check; npm run build:ui.
- Regras/API/UI: npm test. O script test:planner seleciona o runtime Python; verificar scripts/python-runtime.mjs.
- Testes PostgreSQL devem usar instância local descartável conforme CI, nunca banco remoto/real. Não imprimir URLs com credenciais.
- Deploy Docker e saúde seguem .github/workflows/ci.yml; não afirmar validação Docker se não foi executada.
- Mudanças apenas de documentação não exigem instalar dependências.
## Invariantes
Demo pública somente leitura, isolada do banco administrativo. Manter autenticação das rotas privadas e nunca pôr token em URL ou frontend.
Preservar FEFO, validade de lotes, capacidade, refrigeração, janelas, turno, retorno ao depósito, atendimento integral e verificador independente.
Planejar/simular não baixa estoque. Expedição é ação distinta; testar duplicação e persistência com dados sintéticos.
README registra expiração do PostgreSQL gratuito em 25/11/2026: confirmar a situação antes de propor continuidade; não migrar nem contratar automaticamente.
