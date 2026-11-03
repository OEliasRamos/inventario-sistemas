# Ficha do Sistema: App de Triagem e Seleção (AppSheet)

## 1. Identificação
- **Tipo:** AppSheet
- **Link / local:** `https://www.appsheet.com/start/ficticio-app-triagem-up`
- **Conta Google dona:** `operacao@upestagios.com.br`
- **Quem criou / quem mantém:** Criado internamente por Elias (2021); mantido pela equipe de operações.
- **Status:** Em uso

---

## 2. Para que serve
- **Resumo:** Aplicativo utilizado pela equipe interna para gerenciar o funil de candidatos inscritos nas vagas abertas de estágio. Permite avaliar currículos, marcar status (Inscrito, Pré-selecionado, Entrevista, Encaminhado, Aprovado, Reprovado) e agendar entrevistas com as empresas contratantes.
- **Etapas do estágio que atende:** Triagem, Entrevistas e Encaminhamento.
- **Quem usa:** Equipe interna (recrutadores e atendimento).
- **Frequência de uso:** Diária (contínua durante todo o expediente comercial).

---

## 3. Como funciona
- **Telas / páginas principais:**
  1. *View "Vagas Abertas" (Deck View):* Lista das oportunidades ativas com contagem de inscritos e prazo limite.
  2. *View "Candidatos por Vaga" (Table View com agrupamento por Status):* Exibe os estudantes ordenados por compatibilidade de curso e data de inscrição.
  3. *View "Ficha do Candidato" (Detail View):* Visualização dos dados do aluno, link para o currículo no Google Drive, histórico de notas e botão de ação rápida para WhatsApp.
  4. *View "Agenda de Entrevistas" (Calendar View):* Calendário semanal com os horários marcados com as empresas parceiras.
- **Ações e automações (Actions & Bots):**
  - *Action "Avançar Etapa":* Botão de um clique que altera o campo `Status` de "Inscrito" para "Pré-selecionado".
  - *Bot "Notificar Recrutador":* Dispara e-mail para a equipe quando uma vaga recebe mais de 20 inscritos.
  - *Action "Abrir WhatsApp":* Abre o link `https://wa.me/55...` com mensagem pré-preenchida de convocação.
- **Regras de negócio importantes:**
  - Validação `Valid_If` no campo `Horario_Entrevista`: não permite agendar duas entrevistas no mesmo slot de 30 minutos.
  - Regra de idade/período: Alunos no último semestre só podem ser encaminhados se a vaga aceitar estágio de curta duração (menos de 6 meses).

---

## 4. Dados
- **Bases que lê:**
  - Google Sheets: `Base_Candidatos_Geral` (Aba `Inscricoes`)
  - Google Sheets: `Base_Vagas_Ativas` (Aba `Vagas`)
- **Bases que escreve:**
  - Google Sheets: Atualiza colunas `Status_Selecao`, `Data_Entrevista`, `Parecer_Recrutador` e `Feedback_Empresa`.
- **Principais entidades:** Estudante, Vaga, Empresa Parceira, Agendamento de Entrevista.
- **Volume aproximado:** ~450 candidatos novos por mês; ~60 vagas simultâneas.

---

## 5. Integrações
- **Portal de Vagas Web ➔ AppSheet:** Indireta via Google Sheets. O formulário do site grava na planilha, e o AppSheet sincroniza a leitura.
- **WhatsApp:** Manual via botão que gera deep-link (sem uso de API oficial do WhatsApp).
- **E-mail:** Envio nativo de notificações via serviço de e-mail do AppSheet.

---

## 6. Problemas e limitações
- **Latência de sincronização:** Como o AppSheet depende de sync na nuvem com o Google Sheets, novos inscritos do site demoram até 15 minutos para aparecer na tela se o recrutador não der "Sync" manual.
- **Comunicação manual com o candidato:** O envio de mensagens para confirmação de presença ainda exige que o recrutador mande uma a uma pelo celular/WhatsApp Web.
- **Gargalo de aprovação:** Quando o estudante é aprovado, a equipe precisa copiar os dados dele manualmente e colar na planilha do gerador de contratos.

---

## 7. Observações para a integração (Projeto Start BSB)
- O fluxo de mudança de status (funil Kanban) é muito bem aceito pela equipe e deve ser mantido ou replicado na nova interface unificada.
- Integrar um Agente de IA para fazer uma pré-triagem automática (comparando requisitos da vaga vs. currículo do estudante) antes do recrutador humano intervir.
- Automatizar o disparo de notificações de agendamento por WhatsApp via API oficial.

---

## 8. Evidências
- [evidencias/prints-telas.pdf](file:///c:/Trabalho%20-%20UP%20Estágios/PROJETOS/Inventário%20dos%20Sistemas%20da%20Up%20Estágio/sistemas/triagem-candidatos/evidencias/) — Prints das 4 visualizações principais do app.
- [dados/app-documentation.md](file:///c:/Trabalho%20-%20UP%20Estágios/PROJETOS/Inventário%20dos%20Sistemas%20da%20Up%20Estágio/sistemas/triagem-candidatos/dados/) — Extração das tabelas, colunas, tipos e fórmulas gerada pela ferramenta do AppSheet.

---

## 9. Dúvidas em aberto
- *(Resolvida)* Existe bot de WhatsApp? Confirmado que hoje é 100% manual (ver [01-pendencias.md](file:///c:/Trabalho%20-%20UP%20Estágios/PROJETOS/Inventário%20dos%20Sistemas%20da%20Up%20Estágio/01-pendencias.md#PEND-002)).
- *(Aberta)* Quem tem acesso de edição às regras do AppSheet hoje além do Elias? (Perguntar à equipe de TI/Operações).
