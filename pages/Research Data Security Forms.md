# Questions to Rebeca
	- What is the difficulty today?
	  logseq.order-list-type:: number
	- How much does the average person (doing research) knows about technologies, IT?
	  logseq.order-list-type:: number
	- If given a site to enter, login, and to insert data for the research would this be a challenge?
	  logseq.order-list-type:: number
	- What the ethics committee considers a safe data? 
	  logseq.order-list-type:: number
		- What are the rules?
		  logseq.order-list-type:: number
	- logseq.order-list-type:: number
- #[[Infra]] #[[DevOps]] #[[Cybersecurity]] #[[IT-Projects]]
- # Épicos para secure-research-data-insertion
	- ## Chat:
		- # 🧠 ESTRUTURA SUGERIDA DE LABELS
		  
		  Crie essas labels no GitHub:
		- `epic`
		- `infra`
		- `security`
		- `ansible`
		- `lgpd`
		- `docs`
		- `demo`
		- `backup`
		- `priority:high`
		- `priority:medium`
		- `priority:low`
		  
		  ---
		- # 📦 ÉPICO 1 — Planejamento e Arquitetura
		- ## 🧾 Issue: Definir requisitos do sistema
		  
		  **Labels:** `epic`, `priority:high`
		  
		  **Descrição:**
		  
		  Definir escopo funcional e restrições do sistema de coleta de dados.
		  
		  **Checklist:**
		- Definir tipos de usuários (admin, pesquisador, coletor)
		- Definir tipo de dados (sensíveis / não sensíveis)
		- Definir volume esperado de dados
		- Definir necessidade de anonimização
		  
		  ---
		- ## 🧾 Issue: Definir arquitetura inicial
		  
		  **Labels:** `infra`, `priority:high`
		  
		  **Checklist:**
		- Definir topologia (single server vs separado)
		- Definir stack (Nginx + DB + app)
		- Escolher banco de dados
		- Definir estratégia de deploy
		  
		  ---
		- ## 🧾 Issue: Definir estratégia de acesso seguro
		  
		  **Labels:** `security`, `priority:high`
		  
		  **Checklist:**
		- Definir uso de Tailscale
		- Definir grupos de acesso
		- Definir política de autenticação
		  
		  ---
		- ## 🧾 Issue: Criar diagrama de arquitetura (v1)
		  
		  **Labels:** `docs`, `priority:medium`
		  
		  **Checklist:**
		- Criar diagrama simples (fluxo de dados)
		- Validar clareza para leigos
		  
		  ---
		- # ⚙️ ÉPICO 2 — Setup Base
		- ## 🧾 Issue: Provisionar servidor Linux
		  
		  **Labels:** `infra`, `priority:high`
		  
		  **Checklist:**
		- Escolher ambiente (local ou VPS)
		- Instalar Ubuntu Server
		- Validar acesso SSH
		  
		  ---
		- ## 🧾 Issue: Hardening inicial de SSH
		  
		  **Labels:** `security`, `priority:high`
		  
		  **Checklist:**
		- Configurar login por chave
		- Desabilitar login por senha
		- Alterar porta SSH (opcional)
		  
		  ---
		- ## 🧾 Issue: Instalar  LimeSurvey  manualmente
		  
		  **Labels:** `infra`, `priority:high`
		  
		  **Checklist:**
		- Instalar dependências
		- Configurar banco
		- Validar acesso local
		  
		  ---
		- # 🔐 ÉPICO 3 — Segurança
		- ## 🧾 Issue: Configurar  Tailscale
		  
		  **Labels:** `security`, `priority:high`
		  
		  **Checklist:**
		- Instalar Tailscale
		- Conectar ao tailnet
		- Criar grupo de acesso
		  
		  ---
		- ## 🧾 Issue: Configurar firewall
		  
		  **Labels:** `security`, `priority:high`
		  
		  **Checklist:**
		- Instalar UFW
		- Bloquear portas públicas
		- Liberar apenas via VPN
		  
		  ---
		- ## 🧾 Issue: Configurar HTTPS
		  
		  **Labels:** `security`, `priority:high`
		  
		  **Checklist:**
		- Configurar TLS
		- Validar certificado
		- Testar acesso seguro
		  
		  ---
		- ## 🧾 Issue: Criar usuários e permissões no LimeSurvey
		  
		  **Labels:** `security`, `priority:high`
		  
		  **Checklist:**
		- Criar usuários individuais
		- Definir roles
		- Testar restrições
		  
		  ---
		- # 🧾 ÉPICO 4 — Auditoria e LGPD
		- ## 🧾 Issue: Configurar logs do sistema e aplicação
		  
		  **Labels:** `lgpd`, `security`, `priority:high`
		  
		  **Checklist:**
		- Ativar logs no LimeSurvey
		- Validar logs de login
		- Validar logs de inserção
		  
		  ---
		- ## 🧾 Issue: Definir política de retenção de dados
		  
		  **Labels:** `lgpd`, `priority:medium`
		  
		  **Checklist:**
		- Definir tempo de retenção
		- Documentar política
		- Validar com pesquisa
		  
		  ---
		- ## 🧾 Issue: Documentar fluxo de dados (LGPD)
		  
		  **Labels:** `lgpd`, `docs`, `priority:high`
		  
		  **Checklist:**
		- Mapear entrada → armazenamento → acesso
		- Identificar dados sensíveis
		- Descrever controles de acesso
		  
		  ---
		- # 🔁 ÉPICO 5 — Automação (Ansible)
		- ## 🧾 Issue: Criar estrutura base do Ansible
		  
		  **Labels:** `ansible`, `priority:high`
		  
		  **Checklist:**
		- Criar diretórios (roles, inventory)
		- Criar playbook principal
		  
		  ---
		- ## 🧾 Issue: Criar role common
		  
		  **Labels:** `ansible`, `priority:medium`
		  
		  ---
		- ## 🧾 Issue: Criar role security
		  
		  **Labels:** `ansible`, `security`, `priority:high`
		  
		  ---
		- ## 🧾 Issue: Criar role nginx
		  
		  **Labels:** `ansible`, `priority:medium`
		  
		  ---
		- ## 🧾 Issue: Criar role database
		  
		  **Labels:** `ansible`, `priority:medium`
		  
		  ---
		- ## 🧾 Issue: Criar role limesurvey
		  
		  **Labels:** `ansible`, `priority:high`
		  
		  ---
		- ## 🧾 Issue: Criar role tailscale
		  
		  **Labels:** `ansible`, `priority:high`
		  
		  ---
		- ## 🧾 Issue: Testar idempotência do Ansible
		  
		  **Labels:** `ansible`, `priority:high`
		  
		  **Checklist:**
		- Rodar playbook múltiplas vezes
		- Validar ausência de erros
		- Testar rebuild completo
		  
		  ---
		- # 💾 ÉPICO 6 — Backup
		- ## 🧾 Issue: Implementar backup automatizado
		  
		  **Labels:** `backup`, `priority:high`
		  
		  **Checklist:**
		- Backup do banco
		- Backup de arquivos
		- Configurar cron
		  
		  ---
		- ## 🧾 Issue: Testar restore de backup
		  
		  **Labels:** `backup`, `priority:high`
		  
		  **Checklist:**
		- Simular falha
		- Restaurar dados
		- Validar integridade
		  
		  ---
		- # 📄 ÉPICO 7 — Documentação
		- ## 🧾 Issue: Criar documentação técnica
		  
		  **Labels:** `docs`, `priority:high`
		  
		  ---
		- ## 🧾 Issue: Criar diagrama final de arquitetura
		  
		  **Labels:** `docs`, `priority:high`
		  
		  ---
		- ## 🧾 Issue: Documentar segurança e controle de acesso
		  
		  **Labels:** `docs`, `security`, `priority:high`
		  
		  ---
		- ## 🧾 Issue: Criar README do projeto
		  
		  **Labels:** `docs`, `priority:medium`
		  
		  ---
		- # 🎤 ÉPICO 8 — Demonstração
		- ## 🧾 Issue: Criar ambiente de demonstração
		  
		  **Labels:** `demo`, `priority:high`
		  
		  ---
		- ## 🧾 Issue: Criar cenários de uso (válido vs bloqueado)
		  
		  **Labels:** `demo`, `priority:high`
		  
		  ---
		- ## 🧾 Issue: Criar apresentação simplificada
		  
		  **Labels:** `demo`, `docs`, `priority:medium`
		  
		  ---
		- ## 🧾 Issue: Ensaiar apresentação
		  
		  **Labels:** `demo`, `priority:medium`
		  
		  ---
		- # 🚀 ÉPICO 9 — Portfólio
		- ## 🧾 Issue: Organizar repositório público
		  
		  **Labels:** `docs`, `priority:high`
		  
		  ---
		- ## 🧾 Issue: Escrever case técnico
		  
		  **Labels:** `docs`, `priority:medium`
		  
		  ---
		- ## 🧾 Issue: Criar post para LinkedIn
		  
		  **Labels:** `docs`, `priority:low`
		  
		  ---
		- # 🎯 COMO USAR ISSO AGORA
		- Crie um projeto no GitHub (Projects / Kanban)
		- Crie colunas:
			- Backlog
			- To Do
			- In Progress
			- Done
		- Copie cada issue acima
		- Priorize:
			- comece pelas `priority:high`
			  
			  ---
		- # 🧠 DICA FINAL (ouro)
		  
		  👉 Não tente fazer tudo em paralelo
		  
		  Fluxo ideal:
		- Infra funcionando
		- Segurança
		- Automação
		- Documentação
		- Demo