# Ficha do Sistema: Portal de Vagas Web

## 1. Identificação
- **Tipo:** Web (WordPress + Elementor + formulários integrados)
- **Link / local:** `https://upestagios.com.br/vagas`
- **Conta Google dona / Hospedagem:** `contato@upestagios.com.br` / Hostinger
- **Quem criou / quem mantém:** Criado por agência terceirizada em 2019; mantido internamente pelo Elias.
- **Status:** Em uso

---

## 2. Para que serve
- **Resumo:** Página pública onde os estudantes consultam vagas abertas de estágio em Brasília e região, filtrando por curso e cidade, e realizam a candidatura enviando seus dados e currículo em PDF.
- **Etapas do estágio que atende:** Captação de Estudantes e Divulgação de Vagas.
- **Quem usa:** Estudantes (público externo) e equipe de comunicação/marketing (para publicação das vagas).
- **Frequência de uso:** Diária e contínua.

---

## 3. Como funciona
- **Telas / páginas principais:**
  1. *Página Inicial de Vagas:* Vitrine com cards resumidos de cada vaga (bolsa, carga horária, curso, bairro/cidade).
  2. *Página de Detalhes da Vaga:* Descrição completa das atividades, benefícios, requisitos e botão "Quero me candidatar".
  3. *Formulário de Inscrição (Modal ou página dedicada):* Coleta nome completo, e-mail, telefone/WhatsApp, curso, instituição de ensino, semestre atual e upload de currículo.
- **Ações e automações:**
  - Envio de webhook / script que grava a linha do formulário diretamente na planilha `Base_Candidatos_Geral` no Google Drive.
  - Salva o arquivo de currículo em pasta específica do Google Drive.
- **Regras de negócio importantes:**
  - Bloqueio de arquivos maiores que 5MB no upload.
  - Formato aceito para currículo: exclusivamente PDF.

---

## 4. Dados
- **Bases que lê:**
  - Banco de dados MySQL local do WordPress (posts de vagas).
- **Bases que escreve:**
  - Planilha Google Sheets: `Base_Candidatos_Geral` (Aba `Inscricoes`).
  - Google Drive: Pasta de uploads `/Candidatos/Curriculos_2026/`.
- **Principais entidades:** Estudante, Candidatura, Vaga de Estágio.
- **Volume aproximado:** ~1.200 acessos semanais; ~15 a 30 inscrições diárias.

---

## 5. Integrações
- **Google Sheets / Drive:** Via plugin de formulário com webhook ou script intermediário.
- **Redes Sociais:** Compartilhamento manual de links das vagas no Instagram e LinkedIn.

---

## 6. Problemas e limitações
- Vagas preenchidas precisam ser desativadas manualmente no painel do WordPress; se a equipe esquecer, estudantes continuam se inscrevendo em vagas já fechadas.
- O upload às vezes falha por instabilidade da hospedagem compartilhada.

---

## 7. Observações para a integração (Projeto Start BSB)
- O novo portal unificado deve ter sincronização bidirecional em tempo real: ao encerrar a vaga no sistema interno, a vaga sai do ar automaticamente no portal.
- Criação de área logada simples do estudante para acompanhar o status da sua candidatura ("Em análise", "Encaminhado", "Processo encerrado").

---

## 8. Evidências
- [evidencias/prints-portal.png](file:///c:/Trabalho%20-%20UP%20Estágios/PROJETOS/Inventário%20dos%20Sistemas%20da%20Up%20Estágio/sistemas/portal-de-vagas/evidencias/) — Capturas da página de vagas e do modal de candidatura.

---

## 9. Dúvidas em aberto
- [PEND-001](file:///c:/Trabalho%20-%20UP%20Estágios/PROJETOS/Inventário%20dos%20Sistemas%20da%20Up%20Estágio/01-pendencias.md#PEND-001): O envio de currículos cai direto na planilha ou passa por um banco de dados intermediário na hospedagem?
