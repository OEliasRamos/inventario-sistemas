# Sistema Vagas 3.0

## 1. Identificação
- Tipo: AppSheet
- Link / local: Não se sabe (pendente de envio do link do AppSheet)
- Conta Google dona: Não se sabe
- Quem criou / quem mantém: Mantido e utilizado pela equipe de RH / Atendimento da Up Estágio
- Status: em uso

## 2. Para que serve
- Resumo: Aplicativo central utilizado pelo RH para gerenciar o andamento de todo o processo seletivo de ponta a ponta. Permite registrar o diário de bordo com comentários diários sobre cada processo, acompanhar metas da equipe, gerenciar vagas e monitorar empresas parceiras (incluindo controle de inadimplência).
- Etapas do estágio que atende: triagem | acompanhamento do processo seletivo | gestão de clientes (empresas)
- Quem usa: equipe interna (RH e recrutadores)
- Frequência de uso: diária (contínua)

## 3. Como funciona
- Telas / páginas principais (identificadas a partir do menu lateral da evidência):
  1. **Vagas:** Gestão das oportunidades abertas.
  2. **Contratações:** Registro e status dos candidatos contratados.
  3. **Kanban:** Quadro visual para movimentação dos processos seletivos por etapas.
  4. **Pontuação:** Controle de pontuação (dedução: avaliação de produtividade do RH ou pontuação de vagas/candidatos).
  5. **Metas:** Acompanhamento de metas de contratações/atendimentos da equipe.
  6. **KPIs Kanban:** Indicadores de desempenho e métricas de fluxo do processo seletivo.
  7. **Contatos:** Tabela com contatos de clientes/empresas, cargos (ex.: Diretoria, RH, Financeiro) e telefones.
  8. **Anotações:** Diário de bordo onde o RH registra os comentários do que foi realizado diariamente em cada processo.
  9. **Empresas:** Cadastro detalhado das empresas parceiras e status financeiro/adimplência.
  10. **Mural:** Avisos gerais e comunicação interna.
  11. **Forms:** Formulários vinculados ao aplicativo.
  12. **Gestão de Vagas:** Parametrização e administração do status das vagas.
  13. **Requisições:** Solicitações de abertura ou alteração de vagas.
- Ações e automações:
  - Registro de comentários diários por processo.
  - Sinalização de empresas inadimplentes para a equipe de atendimento.
  - (Outras ações dependem da exportação da documentação do AppSheet).
- Regras de negócio importantes:
  - Acompanhamento de empresas inadimplentes (não se sabe se bloqueia novas vagas ou é apenas alerta visual).

## 4. Dados
- Bases que lê: Não se sabe o ID da planilha do Google Sheets (pendente de confirmação).
- Bases que escreve: Atualiza anotações diárias, contatos, status do Kanban e contratações.
- Principais entidades: Vaga, Processo Seletivo, Empresa, Contato da Empresa, Anotação Diária, Contratação, Meta.
- Volume aproximado: Não se sabe.

## 5. Integrações
- Possível integração com o Banco de Currículos (não se sabe se lê a mesma base ou se o RH pesquisa manualmente).
- Não se sabe se possui bots de e-mail ou WhatsApp ativos.

## 6. Problemas e limitações
- A confirmar com a equipe de RH durante a operação diária.

## 7. Observações para a integração (Projeto Start BSB)
- O aplicativo já possui uma estrutura muito rica de gestão de fluxo (Kanban, KPIs, Metas e Anotações diárias).
- Na plataforma unificada, os agentes de IA podem atuar registrando comentários automáticos a cada interação do candidato (ex.: "Candidato confirmou entrevista via WhatsApp") diretamente no feed do processo.

## 8. Evidências
- [evidencias/tela-contatos-menu.png](file:///c:/Trabalho%20-%20UP%20Estágios/PROJETOS/Inventário%20dos%20Sistemas%20da%20Up%20Estágio/sistemas/sistema-vagas-3/evidencias/tela-contatos-menu.png) — Captura de tela do aplicativo exibindo o menu lateral completo e a visualização da tabela de Contatos.

## 9. Dúvidas em aberto
- [PEND-VAGAS-01] Qual a planilha do Google Sheets que serve como banco de dados do Sistema Vagas 3.0?
- [PEND-VAGAS-02] O controle de empresas inadimplentes bloqueia a criação de novas vagas pelo RH ou serve apenas como um sinalizador visual?
- [PEND-VAGAS-03] A view de "Pontuação" mede o desempenho dos recrutadores ou classifica os candidatos?
