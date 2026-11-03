# BANCO DE CURRÍCULOS Up Estágio

## 1. Identificação
- Tipo: AppSheet
- Link / local: Não se sabe (pendente de envio do link do AppSheet)
- Conta Google dona: Não se sabe
- Quem criou / quem mantém: Mantido e utilizado pela equipe da Up Estágio
- Status: em uso

## 2. Para que serve
- Resumo: Aplicativo que gerencia o repositório central de candidatos cadastrados na Up Estágio. Permite consultar dados detalhados dos estudantes (curso, idade, localização, contato), abrir o currículo em anexo salvo no Google Drive, atualizar cadastros e excluir registros.
- Etapas do estágio que atende: captação | triagem | banco de talentos
- Quem usa: equipe interna (RH e recrutadores)
- Frequência de uso: diária

## 3. Como funciona
- Telas / páginas principais (identificadas a partir do menu lateral da evidência):
  1. **Banco de Currículos:** Tabela/Deck principal com a listagem de todos os estudantes cadastrados e barra de pesquisa por nome/palavra-chave.
  2. **Candidatos em Alerta IES:** Visualização com filtro de candidatos com pendências ou avisos ligados à Instituição de Ensino Superior.
  3. **Modelos de Emails:** Biblioteca com templates pré-configurados de comunicação por e-mail com os candidatos.
  4. **Logs:** Registro de histórico de alterações e acessos no aplicativo.
  5. **IA Sheets:** Visualização ou integração (ícone de robô) aparentemente conectada a recursos de inteligência artificial no Google Sheets.
  6. **Alerta de IES:** Gestão e regras dos alertas relacionados às faculdades parceiras.
- Ações e automações:
  - Visualizar detalhes completos do estudante.
  - Abrir anexo de currículo diretamente no Google Drive.
  - Editar dados cadastrais do candidato.
  - Excluir cadastros.
- Regras de negócio importantes:
  - Alerta IES: regras de validação ou restrição de estudantes com determinadas pendências institucionais (detalhes a confirmar).

## 4. Dados
- Bases que lê:
  - Planilha Google Sheets do Banco de Currículos (ID a confirmar).
  - Pasta do Google Drive contendo os PDFs de currículos anexados.
- Bases que escreve:
  - Atualiza, edita e remove registros de candidatos na planilha.
- Principais entidades: Candidato / Estudante, Currículo (PDF), Instituição de Ensino (IES), Modelo de E-mail, Log.
- Campos gerenciados do candidato:
  - Nome completo
  - Curso cursando
  - Idade / Data de nascimento
  - Localização / Bairro / UF
  - Número de telefone / WhatsApp
  - E-mail
  - Link/Arquivo de currículo em anexo (Drive)
- Volume aproximado: Não se sabe (pendente de volume total de linhas na base).

## 5. Integrações
- **Google Drive:** Abertura e visualização dos arquivos PDF de currículos anexados.
- **Formulário de Entrada:** Não se sabe se os candidatos chegam via formulário do site oficial (`upestagios.com.br`), Google Forms ou upload em massa.
- **Sistema Vagas 3.0:** Não se sabe se o Vagas 3.0 consome essa mesma base ou se os dados são duplicados.

## 6. Problemas e limitações
- A confirmar com a equipe durante a análise detalhada.

## 7. Observações para a integração (Projeto Start BSB)
- Base prioritária para o agente de IA de triagem: no projeto Start BSB, o agente de IA consultará diretamente esse banco de talentos para fazer "match" automático com novos requisitos de vagas.
- Preservar a integridade dos links do Google Drive para acesso rápido ao currículo original.

## 8. Evidências
- [evidencias/tela-banco-curriculos-menu.png](file:///c:/Trabalho%20-%20UP%20Estágios/PROJETOS/Inventário%20dos%20Sistemas%20da%20Up%20Estágio/sistemas/banco-de-curriculos/evidencias/tela-banco-curriculos-menu.png) — Captura de tela do aplicativo mostrando a tela principal do Banco de Currículos e o menu com as opções "Candidatos em Alerta IES", "Modelos de Emails" e "IA Sheets".

## 9. Dúvidas em aberto
- [PEND-CURR-01] Como os novos candidatos entram no Banco de Currículos? (Site, Google Forms, Typeform ou manual?)
- [PEND-CURR-02] O que faz a opção "IA Sheets" que aparece no menu do app?
- [PEND-CURR-03] O que caracteriza um "Candidato em Alerta IES"? (ex: faculdade sem convênio, semestre incompatível?)
- [PEND-CURR-04] O Sistema Vagas 3.0 lê essa mesma planilha de currículos ou são bases separadas?
