# Ficha do Sistema: Gerador de Contratos (TCE)

## 1. Identificação
- **Tipo:** Google Apps Script (integrado a Planilha Google)
- **Link / local:** ID do script / Planilha `Controle_Contratos_Formalizacao`
- **Conta Google dona:** `administrativo@upestagios.com.br`
- **Quem criou / quem mantém:** Criado por desenvolvedor freelancer em 2022; mantido com suporte eventual do Elias.
- **Status:** Uso parcial

---

## 2. Para que serve
- **Resumo:** Script acionado por botão em planilha que mescla os dados cadastrais da empresa concedente, do estudante e da instituição de ensino em um modelo de documento Google Docs, gerando o Termo de Compromisso de Estágio (TCE) e o Plano de Atividades em formato PDF.
- **Etapas do estágio que atende:** Formalização e Emissão Contratual.
- **Quem usa:** Equipe administrativa / contratos.
- **Frequência de uso:** 3 a 5 vezes por semana (conforme novos contratos são fechados).

---

## 3. Como funciona
- **Telas / páginas principais:**
  - Aba de Planilha com botão de desenho ("Gerar Contrato").
  - Sidebar simples em HTML com opções de escolher o modelo de contrato (ex: 4h diárias, 6h diárias, aditivo de renovação).
- **Ações e automações:**
  - Função disparada: `gerarTCE()`
  - Copia o arquivo modelo do Google Docs correspondente ao tipo de vaga.
  - Substitui variáveis coringa (`{{NOME_ESTUDANTE}}`, `{{CNPJ_EMPRESA}}`, `{{VALOR_BOLSA}}`, etc.).
  - Salva cópia temporária, converte para PDF (`getAs('application/pdf')`), salva na pasta do Drive do ano corrente e insere o link na planilha.
- **Regras de negócio importantes:**
  - Cálculo automático da data de término padrão (6 meses ou 1 ano a partir do início).
  - Verificação de limite legal de 30 horas semanais e 6 horas diárias (Lei do Estágio 11.788/2008).

---

## 4. Dados
- **Bases que lê:**
  - Planilha Google: Linha selecionada com dados da empresa, estudante e instituição.
  - Google Drive: Arquivos de modelos de contrato (`Modelo_TCE_Padrao_2026.docx` ou `.gdoc`).
- **Bases que escreve:**
  - Google Drive: Pasta `/Contratos_Emitidos_2026/PDFs/`.
  - Planilha: Coluna `Status_Emissao` ("Gerado com Sucesso") e `Link_PDF`.
- **Principais entidades:** Contrato (TCE), Empresa Concedente, Estudante, Instituição de Ensino, Apólice de Seguro.
- **Volume aproximado:** ~40 a 60 novos termos emitidos por mês.

---

## 5. Integrações
- **Google Docs & Drive API:** Geração e armazenamento de arquivos.
- **Gmail:** Função opcional `enviarPorEmail()` para encaminhar minuta aos envolvidos.

---

## 6. Problemas e limitações
- Se o operador esquecer de preencher um campo obrigatório na planilha, o script gera o contrato com campos em branco ou quebra no meio da execução.
- Não possui integração com plataforma de assinatura eletrônica (ex: Clicksign, Docusign, ZapSign) — o PDF gerado precisa ser baixado e enviado manualmente para assinatura.

---

## 7. Observações para a integração (Projeto Start BSB)
- Essencial conectar o gerador de contratos diretamente à base de triagem, eliminando a digitação manual de dados que já foram informados no cadastro.
- Integrar com API de assinatura digital para envio e acompanhamento automático do status de assinatura pelas três partes (empresa, aluno e faculdade).

---

## 8. Evidências
- [dados/codigo-script.gs](file:///c:/Trabalho%20-%20UP%20Estágios/PROJETOS/Inventário dos Sistemas da Up Estágio/sistemas/gerador-contratos-tce/dados/) — Cópia do código-fonte do script Google Apps Script.

---

## 9. Dúvidas em aberto
- [PEND-003](file:///c:/Trabalho%20-%20UP%20Estágios/PROJETOS/Inventário dos Sistemas da Up Estágio/01-pendencias.md#PEND-003): O script utiliza um modelo no Google Docs (`DocumentApp`) ou gera o PDF direto por HTML template?
